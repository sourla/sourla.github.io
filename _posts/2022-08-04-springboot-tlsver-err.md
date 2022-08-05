---
title: Springboot TLS 버전 에러

date: 2022-08-04 08:25:00 +0900

categories: [java]

tags: [java,DB]

---

# java TLS 버전 에러

1. 증상
   + 로컬 서버가 뜨지 않는 증상 발생 / Springboot로 구성된
2. 원인
   + 확인 결과 DB 연결에 TLS 버전이 1.0으로 잡혀서 에러가 나는것으로 확인
3. 조치내용
   + JDK 안의 jre\lib\security 경로에서 java.securty 파일에 접근
   + jdk.tls.disabledAlgorithms 값에서 TLS1.0, 1.1에 해당하는 값을 제거
4. 관련내용 링크
   + [해당 내용 참고 사이트](https://lemontia.tistory.com/1037)

