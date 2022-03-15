---
title: jekyll-theme-chirpy jquery 에러

date: 2022-03-15 17:59:00 +0900

categories: [gitblog]

tags: [gitblog, jekyll-theme-chirpy]
---

# 깃 블로그 jquery 에러가 나기 시작헀다

1. 언제부터인가 jquery 에러가 나서 내 블로그 에러가 나기 시작했다.
  + 처음 gitblog 만들 당시에는 검색도 잘 됬던걸로 기억을 하는데 검색화면이 이상한걸로 봐서 뭔가 바뀐거 같다.
  + 확인을 해보니 jekyll-theme-chirpy 버전이 올라가서 생기는 문제로 보인다
  + chipry-starter 로 만든 다른 사이트 확인 결과, gemfile에 version이 다른것으로 확인되었다.
  아마도 version이 올라가서 include 파일 등 gh-page에 빌드하는 옵션이 달라져서 오류가 나는듯하다.
  + 잘 되는곳 gemfile 복붙하니 잘 된다.





