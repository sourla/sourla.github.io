---
title: 첫 포스팅, 마크다운 문법

date: 2022-01-25 23:57:00 +0900

categories: [Markdown]

tags: [Markdown]

---

## 생각보다 쓰는게 어렵네
- 하루에 한번 내용 정리하기
- 내 intelij 파일 이름 변경은 ALT SHIFT F6


# 자주 쓸거같은 MD문법 정리

### 1.헤더
``` Markdown
``#으로 제목을 넣을 수 있고, #의 개수를 늘리면 하위 제목이 된다.
또는 텍스트 아랫줄에 = 또는 -를 여러 개 붙이는 방법도 있다.

# This is H1

## This is H2

### This is H3

#### This is H4

##### This is H5
```


## 2.리스트
   순서가 있는 리스트는 숫자로 넘버링한다.
   불렛 포인트는 * , - , + 중 아무거나 써도 상관 없다.
   들여쓰기로 하위 목록을 만들 수 있다.

```Markdown
1. 첫 번째
2. 두 번째
3. 세 번째


* 1단계
  * 2단계
    * 3단계


* 1단계
  - 2단계
    + 3단계
      + 4단계
```

## 3.구분선
* 또는 -을 세 개 이상 쓰면 구분선을 넣을 수 있다.
```Markdown
***
---
```

## 4.텍스트 강조
   이탤릭체: * 또는 _ 한 개로 텍스트 양쪽을 감싼다.
   굵은 글씨: * 또는 _ 두 개로 텍스트 양쪽을 감싼다.
   취소선: ~ 두 개로 텍스트 양쪽을 감싼다.

```Markdown
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~
```
---
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

~~cancelline~~

## 5.link
[] 안에 링크를 걸 텍스트, () 안에 url 주소를 넣는다.
주소 옆 따옴표에는 링크에 커서를 올렸을 때 보일 설명을 넣을 수 있다.
```
[Google](https://google.com, "google link")
```
