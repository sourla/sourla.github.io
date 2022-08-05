---
title: ajax async invalid access 에러

date: 2022-08-05 13:29:00 +0900

categories: [javascript]

tags: [javascript, browser]

---

# ajax async invalid access 에러

1. 증상
   + ajax async invalid access 에러로 인해 broswer 상 ajax가 호출이 안되는 증상 확인
2. 원인
   + async false (동기)를 설정하니 브라우저 보안정책에서 해당 에러를 내는걸로 추정
3. 조치 내용
   + 임시조치만 진행함
   + 80 port를 다른 포트로 교체하거나, async 옵션을 true (비동기) 처리를 하니 동작하는거 확인 완료
4. 관련내용 링크
   + [w3 보안정책 관련으로 추정하고있는 블로그](https://rosalife.tistory.com/12)
   + [스택오버플로우 글](https://stackoverflow.com/questions/28680897/jquery-ajax-async-false-causes-a-strange-warning)
