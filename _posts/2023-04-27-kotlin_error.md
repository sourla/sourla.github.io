---
title: Spring java 프로젝트이지만 kotlin으로 실행된 문제

date: 2023-04-27 20:30:00 +0900

categories: [java]

tags: [java,spring]

---


# Spring java 프로젝트이지만 kotlin으로 실행된 문제


1. 증상
  + 이상하게 특정 PC, 특정 브런치에서 java이지만 kotlin jvm으로 실행되어 kotlin이 없다는 에러가 intellij에 계속 나는 증상이 있었다.

2. 원인
  + intellij 내장된 코틀린이 버전이 너무 낮아서, java와 kotlin 문법을 헷갈려 java  프로젝트이지만 코틀린으로 실행하는 버그가 아닐까 추측한다.


3. 조치 내용
  + 처리 내용은 intellij kotlin compile 버전을 1.3에서 1.4로 올려서 해결하였다.


4. 당시 오류 내용(자꾸 자바 프로젝트가 코틀린으로 실행되서 maven에 코틀린 라이브러리 추가하고 그랬지만 컴파일러 옵션을 변경하니 한방에 해결되어 다행이었다.)
```
   Information:Kotlin: kotlinc-jvm 1.3.61 (JRE 1.8.0_65-b17)
   Information:2023-04-27 오후 1:46 - Build completed with 2 errors and 2 warnings in 10 s 677 ms
   Error:Kotlin: Module was compiled with an incompatible version of Kotlin. The binary version of its metadata is 1.6.0, expected version is 1.1.16.
   Error:Kotlin: Module was compiled with an incompatible version of Kotlin. The binary version of its metadata is 1.5.1, expected version is 1.1.16.
   Warning:Kotlin: Runtime JAR files in the classpath should have the same version. These files were found in the classpath:
```


