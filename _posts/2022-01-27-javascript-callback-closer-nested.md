---
title: Javascript 중첩함수 , 콜백 함수 , 클로저 함수

date: 2022-01-27 17:16:00 +0900

categories: [카테고리]

tags: [태그]
---

# Javascript 중첩함수 ,  클로저 함수 , 콜백 함수

## 중첩 함수
  + 외부에 있는 기능을 외부 기능이라고 합니다. 내부에 중첩된 함수를 내부 함수라고 합니다. 각 함수는 다른 인수를 받아들일 수 있습니다.

```Javascript
function a(x) {    // Outer function
  function b(y) { // inner function
    return x - y;
  }
  return b;
}

console.log(a(5)(4))

출력 결과
1
```
  + 위의 예에서 a()는 외부 함수이고 b()는 내부 함수입니다. 반환된 최종 결과는 두 함수의 인수를 사용합니다
  + 외부에서 b를 호출하는것은 불가능하고 a 내부에서만 사용될 것을 명식적으로 나타냅니다.

## 클로저 함수
  + 자바스크립트의 함수안에서 선언한 변수는 종료되면 파괴되지만, 사라지지않게 하는 방법이 있다.
  + 클로저는 자신을 포함하고 있는 외부함수의 인자, 지역변수 등을 외부함수가 종료된 이후에도 사용할수 있다. 이러한 변수를 자유변수라고 한다.
  + 클로저가 생성될때 범위 내의 지역변수들을 자유변수로 만드는 것을 캡쳐라고 한다.

```Javascript
function outer (){
	var name = 'dolarge';
  	return function () {
		console.log(name);
    }
}

var inner = outer();
inner(); // 'dolarge'

출력 결과
'dolarge'
```
  ### 클로저를 통한 은닉화

  + 클로저를 사용하여 외부에서 변수에 직접 접근하는 것을 제한할 수 있다. 직접 접근하여 수정이 가능하지 않다.


```javascript
function factory_movie(title){
    return {
        get_title : function (){
            return title;
        },
        set_title : function(_title){
            title = _title
        }
    }
}
ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');

alert(ghost.get_title());
alert(matrix.get_title());

ghost.set_title('공각기동대');

alert(ghost.get_title());
alert(matrix.get_title())

```

## callback함수
  + javascript에서는 callback 함수는 다른 함수의 매개변수로 함수를 전달하고, 어떠한 이벤트가 발생한 후 매개변수로 전달한 함수가 다시 호출되는 것을 의미합니다.

### callback함수 예시
```javascript

function first(a,b,callback){
	let v=a*b;
	callback(v);
}

first(1,2,function(v){
	console.log(v);		//2
})



```

### callback을 쓰는 이유

+ 콜백을 받아야 하는 상황에 callback 함수를 사용하지 않는다면 콜백 함수의 과정이 끝나기 전에 다음 프로세스가 진행이 되어 예상하지 못한 상황이 발생할 수 있음
+ 실무에서 콜백함수는 이벤트 리스너, 타이머 실행, ajax, jquery animation 기능에서 주로 사용한다.




