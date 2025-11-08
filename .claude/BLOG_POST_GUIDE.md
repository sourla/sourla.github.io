# 블로그 포스트 작성 가이드

이 문서는 Claude Code를 사용하여 블로그 게시물을 쉽게 작성하는 방법을 설명합니다.

## 슬래시 커맨드 사용법

### `/write-post` 명령어

블로그 게시물을 자동으로 작성, 커밋, 푸시하는 명령어입니다.

#### 사용 방법

```
/write-post
```

명령어를 실행한 후, Claude가 다음 정보를 요청합니다:
- 제목
- 카테고리
- 태그
- 본문 내용

#### 예시 1: 대화형으로 작성

```
사용자: /write-post

Claude: 블로그 게시물을 작성하겠습니다. 다음 정보를 알려주세요:
- 제목:
- 카테고리:
- 태그:
- 본문:

사용자:
제목: IntelliJ 단축키 모음
카테고리: intellij
태그: intellij, ide, tips
본문:
# IntelliJ 필수 단축키

## 편집
- Ctrl + Space: 자동완성
- Ctrl + /: 주석 처리

...
```

#### 예시 2: 완성된 내용 제공

```
사용자: 이 내용으로 블로그 포스트 작성해줘

제목: Kotlin Null Safety
카테고리: kotlin
태그: kotlin, null-safety

# Kotlin의 Null Safety

Kotlin은 NullPointerException을 방지하기 위한 강력한 기능을 제공합니다.

## Nullable 타입
...
```

## 파일 형식

### Front Matter (필수)

모든 블로그 게시물은 YAML Front Matter로 시작해야 합니다:

```yaml
---
title: 게시물 제목
date: 2025-11-08 10:00:00 +0900
categories: [카테고리명]
tags: [태그1, 태그2, 태그3]
---
```

### 선택적 Front Matter 필드

```yaml
---
title: 게시물 제목
date: 2025-11-08 10:00:00 +0900
categories: [카테고리명]
tags: [태그1, 태그2]
image:
  path: /assets/img/post-image.jpg
  alt: 이미지 설명
author: author_id
pin: true  # 상단 고정
---
```

## 파일명 규칙

파일은 `_posts/YYYY-MM-DD-title.md` 형식으로 저장됩니다:

```
_posts/2025-11-08-kotlin-null-safety.md
_posts/2025-11-08-intellij-shortcuts.md
```

**주의사항:**
- 파일명은 영문 소문자, 숫자, 하이픈(-)만 사용
- 한글 파일명은 사용하지 않음
- 날짜는 YYYY-MM-DD 형식 준수

## 기존 게시물 분석

프로젝트의 기존 게시물 예시:

### 카테고리별 분류
- `[javascript]`: JavaScript 관련
- `[java]`: Java 관련
- `[intellij]`: IntelliJ IDEA 관련
- `[tomcat]`: Tomcat 서버 관련
- `[뻘글]`: 일상, 잡담

### 태그 예시
`[javascript, callback, closure]`, `[java, textscanner]`, `[intellij, debug]`

## Git 워크플로우

1. **자동 브랜치**: `claude/analyze-git-blog-code-011CUvGjmEd2uuAV6jnuqDZJ`
2. **커밋 메시지**: `Add blog post: {제목}`
3. **푸시**: 자동으로 origin에 푸시
4. **Pull Request**: 푸시 후 PR 링크 제공

## 수동 작업 (슬래시 커맨드를 사용하지 않는 경우)

### 1. 파일 생성

```bash
touch _posts/2025-11-08-my-post.md
```

### 2. 내용 작성

```markdown
---
title: 내 게시물
date: 2025-11-08 10:00:00 +0900
categories: [카테고리]
tags: [태그1, 태그2]
---

# 제목

내용...
```

### 3. Git 작업

```bash
git add _posts/2025-11-08-my-post.md
git commit -m "Add blog post: 내 게시물"
git push -u origin claude/analyze-git-blog-code-011CUvGjmEd2uuAV6jnuqDZJ
```

## 마크다운 작성 팁

### 코드 블록

```javascript
console.log("Hello, World!");
```

### 이미지

```markdown
![이미지 설명](https://user-images.githubusercontent.com/...png)
```

### 링크

```markdown
[링크 텍스트](https://example.com)
```

### 목록

```markdown
- 항목 1
- 항목 2
  - 하위 항목
```

## 문제 해결

### Q: 푸시가 403 에러로 실패해요
A: main 브랜치가 아닌 claude 브랜치를 사용하고 있는지 확인하세요.

### Q: 게시물이 표시되지 않아요
A: Front Matter 형식이 올바른지, 날짜가 미래가 아닌지 확인하세요.

### Q: 이미지가 깨져요
A: 이미지 URL이 올바른지, GitHub에 업로드된 이미지인지 확인하세요.

## 참고 자료

- [Jekyll 문서](https://jekyllrb.com/docs/)
- [Chirpy 테마 문서](https://github.com/cotes2020/jekyll-theme-chirpy)
- [Markdown 가이드](https://www.markdownguide.org/)
