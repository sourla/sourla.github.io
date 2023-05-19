---
title: 로또 자동사기

date: 2023-05-19 12:37:00 +0900

categories: [ github ]

tags: [ github , python]

---

# github을 통해서 로또 자동으로 구매하기

### [Github Actions으로 로또 자동 구매하기 (지속적 로또)](https://velog.io/@king/githubactions-lotto)
+ (소스와 구성이 궁금하다면 상위 링크 참고)


+ velog 글을 보다가 흥미가 가는 글이 있어 해당 부분을 보며 로또 자동 구매를 만들었는데, 조금 개선을 하려고한다.

1. 해당 소스에서는 python 소스안에 id,pw 가 들어있는데 좀 더 스마트하게 해보고 싶어 github action의 사용 시 민감정보를 어떻게 관리하는가 에 대해 포커싱을 두고 확인한 결과
secret이라는 기능이 있는것을 확인하였다.
![lotto1.png](/assets/postingImages/lotto1.png)

2. 상위 캡쳐의 부분을 넣고 github action의 python으로 실행할 때 이런식으로 넣어준다면 소스에 노출되지도 않고, action에도 나오지 않는 것을 확인하였다. (옵션이 생각보다 좋네)
![lotto2.png](/assets/postingImages/lotto2.png)


3. 물론 python에서도 매개변수를 받을 수 있도록 수정해줘야한다.
![lotto3.png](/assets/postingImages/lotto3.png)

### (이렇게 개선을 완료하여 복권 구매를 자동으로 해봤으며, 참고한 소스는 상위 링크 참고)

## 복권 당첨되기를



