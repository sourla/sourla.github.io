---
title: javascript로 OCR 하기

date: 2022-02-03 14:54:00 +0900

categories: [javascript]

tags: [javascript]
---

# javascript OCR

1. javascript로 OCR하기 필요한 내용
  + tesseract 를 사용하여 OCR을 진행함
  + 캡쳐 기능으로 부분 OCR을 하기 위해 하기 script 추가
  + 2배 확대 등을 하기 위한 canvas 기능 및 javascript library 추가
  + 그냥 쓰려고 해봤는데 텍스트 인식률이 생각보다 안나와서 확대하여 사용하기 위함

```html
<script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/es6-promise@4/dist/es6-promise.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/es6-promise@4/dist/es6-promise.auto.min.js"></script>
```

2. 하기 코드는 텍스트 OCR을 적용한 실제 코드이며 실제로 특정 부위만 캡처를 하기 위하여 수정한 코드.
  + 캡쳐 영역을 컨트롤 하기 위한 mousedown, mouseup, mousemove 코드
  + 캡쳐된 이미지를 canvas로 한번 생성, canvas를 생성하여 2배 확대
  + 2배 확대된 이미지를 Tesseract로 텍스트 인식하도록 수정

```javascript
    function captureTxt(obj) {
                //캡쳐 기능 활성화
                var height = window.innerHeight;
                var width = $(document).width();
                var $mask = $('<div id="screenshot_mask"></div>').css('border-width', '0 0 ' + height + 'px 0');
                var $focus = $('<div id="screenshot_focus"></div>');
                $('body').append($mask); //dimmed 추가
                $('body').append($focus); //마우스 커서에 따라 캡쳐 영역을 만들 div
                var selectArea = false;
                $('body')
                    .one('mousedown', function (e) {
                        //캡쳐 영역 선택 시작
                        e.preventDefault();
                        selectArea = true;
                        startX = e.clientX;
                        startY = e.clientY;
                    })
                    .one('mouseup', function (e) {
                        //캡쳐 시작
                        selectArea = false;
                        $('body').off('mousemove', mousemove); //이벤트 삭제
                        $('#screenshot_focus').remove(); //마우스 포커스 삭제
                        $('#screenshot_mask').remove(); //딤 삭제
                        var x = e.clientX;
                        var y = e.clientY;
                        var top = Math.min(y, startY);
                        var left = Math.min(x, startX);
                        var width = Math.max(x, startX) - left;
                        var height = Math.max(y, startY) - top;
                        html2canvas(document.querySelector("#beforeImages"), {
                        	useCORS:true,
                        	width:window.screen.availWidth,
                        	height:window.screen.availHeight,
                        	//windowWidth:document.body.scrollWidth,
                        	//windowHeight:document.body.scrollHeight,
                        	x:0,
                        	y:window.pageYOffset
                        	}).then(function (canvas) {
                            //전체 화면 캡쳐
                            var img = canvas.getContext('2d').getImageData(left-230, top-100, width, height); //선택 영역만큼 crop
                            var c = document.createElement('canvas');
                            c.width = width*2;
                            c.height = height*2;
                            c.getContext('2d').putImageData(img, 0, 0);

                            var d = document.createElement('canvas');
                            d.width = width*2;
                            d.height = height*2;
                            d.getContext('2d').scale(1.2,1.2);
                            d.getContext('2d').drawImage(c, 0, 0);


                            //$(document.body).append(d);
                            Tesseract.recognize(
                        			d.toDataURL('image/jpeg'),
                        	  'kor+eng'
                        	).then(({ data: { text } }) => {
                        	  //console.log(text);
                        	  	var index = $("button[name='btnScantxt']").index(obj);
								$("#textArea textArea[name='sentence']").eq(index).val(text);
								$("#textArea textArea[name='sentence']").eq(index).change()

                        	})
                        });
                    })
                    .on('mousemove', mousemove); //캡쳐 영역 크기 변경
                function mousemove(e) {
                    var x = e.clientX;
                    var y = e.clientY;
                    $focus.css('left', x); //마우스 커서 따라 좌표 포커스 이동
                    $focus.css('top', y);
                    if (selectArea) {
                        //캡쳐 영역 선택 그림
                        var top = Math.min(y, startY);
                        var right = width - Math.max(x, startX);
                        var bottom = height - Math.max(y, startY);
                        var left = Math.min(x, startX);
                        $mask.css('border-width', [top + 'px', right + 'px', bottom + 'px', left + 'px'].join(' '));
                    }
                }
            }

```



