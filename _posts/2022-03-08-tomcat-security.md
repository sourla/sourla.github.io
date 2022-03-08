---
title: TOMCAT TLS 버전 문제

date: 2022-03-08 11:12:00 +0900

categories: [tomcat]

tags: [tomcat,java]
---

# 페이지 에러

1. 증상
    + 노후화된 서버의 페이지가 https 접속이 되지않음(화면 첨부)


2. 원인
   + 현재 최신 브라우저가 TLS 버전 1.0을 지원하지 않도록 보안패치가 되어 프로토콜 문제가 생김


3. 조치 내용
   + 임시조치로는 http 통신으로 페이지를 먼저 바꿔서 로그인 문제 해결
   + java 1.6 버전에서는 tomcat TLS 버전 설정이 안되서 1.7버전으로 올려서 TLS 설정하여 해결


4. 관련내용 링크
   + [최신 브라우저 TLS 버전 내용](https://cert.crosscert.com/%EA%B3%B5%EC%A7%80%EC%9B%B9-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-tls-1-0-tls-1-1-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C-%EC%A7%80%EC%9B%90-%EC%A4%91%EB%8B%A8-%EC%98%88%EC%A0%95/)



