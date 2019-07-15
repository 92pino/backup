---
title: Naver Tech Concert 리뷰
layout: post
date: 2019-07-12 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: [swift, Naver Tech Concert, 네이버 테크 콘서트, iOS]
category: Conference
author: pino
description: 네이버 ios 컨퍼런스 리뷰
---

# Naver Tech Contert 리뷰

![네이버 사옥](https://user-images.githubusercontent.com/45158632/61229272-db562400-a762-11e9-94df-b95b0f9ee2e6.jpeg)

저번에 [wwdc19 톺아보기](https://92pino.github.io/conference/2019/07/07/wwdc19)에 이어 이번엔 네이버에서 주최한 네이버 테크 콘서트에 참여하였습니다. 주제는 모바일 개발분야의 기술과 경험, 개발 문화 등을 공유 하기 위한 컨퍼런스였는데요 대학생 대상으로 주최된 행사여서 맘 편하게 갔는데 왠걸?? iOS 단톡방에 계신분들도 많이 참여한것 같았었습니다. 그래서 구석에서 학원 사람들과 쭈굴하면서 듣긴했지만 대부분의 내용이 앞으로 실무를 할 사람들이나 실무를 하고 계신분들도 도움이 많이 될 내용이 많아서 공유해보고자 리뷰를 남기려합니다

![기념품](https://user-images.githubusercontent.com/45158632/61229273-db562400-a762-11e9-89f9-54dfa028bb2d.jpeg)

## 네이버 지도 밑그림을 그리는 SDK개발자가 하는 일 - 손원영님
[네이버 지도 밑그림을 그리는 SDK개발자가 하는 일](https://www.slideshare.net/NaverEngineering/techcon-2019-mobile-ios1-sdk)

첫번째로 손원영님의 ```네이버 지도 밑그림을 그리는 SDK개발자가 하는 일``` 이라는 주제로 테크 콘서트가 시작이 되었습니다.


![첫번째 세션](https://user-images.githubusercontent.com/45158632/61229921-00976200-a764-11e9-9632-f9cfaf6f04a1.PNG)

지도 API를 이것저것 써보긴 했지만 아직까지 네이버 지도 API는 사용해보지 못해서 네이버 지도 발표세션은 흥미로웠던 세션중 하나였다. 지도 API에 대한 설명이 나올줄 알고 한껏 기대하고있었는데 막상 발표하신 내용은 세션 타이틀 그대로 SDK개발자가 하는 일에 대해 발표를 하셔서 조금 아쉽긴했다(현재 네이버 지도 API가 예전 버전이라 아직 사용하기엔 너무 어려운듯ㅠㅠ) 그래도 API와는 관련 없이 좋은 내용이 많이 나왔었는데 그 중 하나가 기존에 사용하던 레스터 방식에서 벡터 방식으로 바꾸면서 데이터 사용량은 줄고, 업데이트 속도와 성능은 향상시켰다는 내용인데 발표 내용만으로는 속도도 올라가고 벡터방식으로 바뀌면서 보기가 쉬우니까 사용자들이 좋아할거라 생각했는데 막상 뚜껑을 열어보니 예전 디자인을 좋아하는 사용자들이 꽤나 있다는 말을 듣고 사용자들의 피드백이 많이 중요하단걸 알게되었다.<br>
물론 발표하신 내용에도 지도에 관련한 신박?한 내용들이 많아서 다음번 지도를 사용할땐 네이버 지도 API도 사용해봐야겠다는 생각도 들었다.

## 들숨에 협업 날숨에 클린코드 - 박보영님
[들숨에 협업 날숨에 클린코드](https://www.slideshare.net/NaverEngineering/techcon-2019-mobile-ios2)

제일 기대가 많이 됐던 박보영님의 세션 ```들숨에 협업 날숨에 클린코드```

네이버 테크 콘서트를 가기 이전부터 이분의 세션을 많이 기대했었다!! 비전공자이시지만 ```레이니스트``` 에 들어가신 대단하신 분!<br>
그런분이 발표하시는 클린코드와 협업.. 기대를 안할수가 없었다

간단하게 아이스브래이킹으로 각자 코드 스타일을 투표하는것으로 시작을 하셨는데 같이 왔던 학원 사람들과도 투표 얘기를 해보니 우리 학원 강사님이 가르쳐 주셨던 코드로 대부분 투표를 하셨다고 하더라.. 나만 다른거로 투표해서 뭐지.. 했는데 박보영님의 회사에서 정해놓은 코드가 내가 투표한 코드와 같다는걸보고 다행?이다라는 생각이 들었다.(코드 스타일은 개개인이 다른거니까ㅋㅋ)<br>

그리고나서 발표를 진행하시는데 그중에 제일 와닿았던 내용들은 SwiftLint와 뱅크샐러드 MVC탈출기 두가지 발표였다.

### SwiftLint

SwiftLink는 각자의 다른 코딩 스타일을 하나의 스타일로 바꿔주는? 라이브러리라고 보면 될것 같은데 사용법 또한 간단합니다.
사용법에 대해서는 자세히 설명이 없으니 ```SwiftLint``` 깃허브 주소와 한글 문서로 된 깃허브 주소를 남기도록 하겠습니다!

SwiftLint Github : [SwiftLint](https://github.com/realm/SwiftLint)
SwiftLint 한글 문서 : [SwiftLint 한글](https://github.com/realm/SwiftLint/blob/master/README_KR.md)

그리고 혹시나 도움이 될만한 주소 [realm SwiftLint](https://academy.realm.io/kr/posts/slug-jp-simard-swiftlint/), [Zedd님 blog](https://zeddios.tistory.com/447)

### MVC 탈출기

아직 MVC도 어려운데 그 어려운 MVC를 탈출하라니ㅠㅠ 예전부터 MVC패턴이 불편해서 다른 MVVM이나 MVP패턴이 생기고 다른 패턴을 사용하다가 결국 돌아오는건 MVC라고 들었었는데 여기서는 MVC -> MVVM에 대한 설명을 해주시면서 직접 작업하셨던 github 주소를 공유해주시고 그 코드를 이용해서 발표를 해주셨는데 1번 듣고는 잘 모르니 다시 발표내용도 보고 파일도 보면서 직접 만들어보면 더 도움이 될것같다!<br>

참고자료 : [BringMyOwnBeer](https://github.com/fimuxd/BringMyOwnBeer-)

## 쉽고 재미있는 iOS 디버깅 - 안정민님
[쉽고 재미있는 iOS 디버깅](https://www.slideshare.net/NaverEngineering/techcon-2019-mobile-ios3i-os-debug)

민소네라는 닉네임으로 원래 블로그도 자주 들어가봤던 분이 발표를 하러 오셨습니다. 이번 발표에서는 xcode에서 디버깅 할 때 유용한 명령어들을 알려주셨는데 po라는 명령어밖에 사용할줄 모르고 po도 잘 사용을 못했어서그런지 난이도가 굉장히 높았던 발표 세션이였다. 무슨 명령어는 어떻게 사용되고 하나하나 설명을 해주시는데 확실히 깊게 공부하셨구나를 많이 느낄수 있었던 세션이면서도 안정민님 정도까지는 아니여도 비슷하게라도 되보자 하면서 채찍질을 더 해야겠다고 느꼈다 (내용이 많이 짧네요..ㅠ 다음에 더 공부해서 채워넣도록 하겠습니다ㅠㅠ)

lldb에 대해서는 다음 사이트를 참고하면 도움이 많이 될것같다.

lldb 참고 : [LLDB Homepage](https://lldb.llvm.org)

## ARKit, CoreML, Turi Create 삼형제 - 노수진님, 김희재님
[ARKit, CoreML, Turi Create 삼형제](https://www.slideshare.net/NaverEngineering/techcon-2019-mobile-ios42arkit-coreml-turi-create)

노수진님과 김희재님이 합작해서 만드신 ARKit 앱을 보여주시면서 만드신 앱에 대한 설명과 앱 구현하는 과정에 대한 설명을 해주셨었다.<br>
얼굴이 나와있는 사진을 찍거나 선택한 후 지폐 유형(천원, 오천원, 만원, 오만원권)을 선택하게되면 두개의 사진이 이질감 없이 합성되는 앱인데 요즘 핫한 기술들인 ARKit과 coreML을 이용하여 만들었다고 한다.
ARKit의 경우 학원 초반 발표시간때 학원 동료가 발표를 한거보고 신기한 기능이다!!! 해서 몇번 찾아보기도 하고 샘플 코드를 가져와서 테스트를 해보기도 했을정도로 관심이 있는 기술이였는데 원래 생각했던 프로젝트를 ARKit을 이용해서 해봐도 괜찮을 것 같단 생각이 들었다.

## 사용자 경험을 높이는 애니메이션 만들기 - 김기범님
[사용자 경험을 높이는 애니메이션 만들기](https://www.slideshare.net/NaverEngineering/techcon-2019-mobile-ios5-155527315)

지금까지 들었던 세션들 중 발표를 가장 잘하셨다고 생각이 들 정도로 내용 정리고 깔끔하고 막힘없이 술술 얘기해주셨던 섹션이다.<br>
보통 애니메이션은 화려해보이고 멋있어보이기 위해서 많이 사용했던 나로서는 굉장히 신박한 주제였는데 이 분의 경우 애니메이션의 기능을
- 중요한 컨텐츠 강조 ex) 메일나 알람이 왔을 경우 우측 상단에 뱃지가 활성화, 통화중일 떄 상단 네비게이션바 깜빡임
    - 컨텐츠 상에 중요한 변화가 생겼을때 발동됨
    - 한번 재생되면 멈추지 않고 쭉 재생
    - Fire-and-forget
- 컨텐츠의 맥락 유지 ex) 앱스토어의 메인 화면에서 상세 페이지로 넘어갔을떄, 달력에서 디테일 날짜로 넘어갔을 때
    - 트랜지션 효과
    - 주로 페이지간의 이동에서 많이 사용
    - Fire-and-forget 방식이 대부분
    - 사용자 제스처에 따라 점진적으로 재생되기도 함
    - 한번에 쭉 재생되는 경우가 대부분
    - 사용자 제스처에 따라 점진적으로 재생되기도 함
    - UIGestureRecognizer와 연동되기도 함
- 유저 입력에 대한 컨텐츠 반응
    - 사용자 제스처에 따라 점진적으로 재생됨
    - 제스처의 시작, 변화, 종료에 대한 애니메이션을 각각 정의해야함
    - UIGestureRecognizer 활용하기
으로 구분지어서 말씀해주셨다.

이어서 어떻게 애니메이션을 구현할지, 애니메이션의 구현이 어려운 이유, 간단한 애니메이션 이론을 차례로 설명해주면서 애니메이션 적용 예시와 예시 사이트를 보여주면서 애니메이션의 3요소
```Trigger```, ```Target```, ```Time``` 가 언제 필요한지 하나하나 보여주셨었는데 이뻐보이고 화려하면 됐지 했던 내 자신을 다시 한번 돌아보는 시간이 되었습니다.

커스텀한 애니메이션 커브값을 구현해보고 싶을때 [cuvic-bezier](https://cubic-bezier.com)을 이용해서 직접 그래프를 조정해 원하는 애니메이션을 만들어보고 구현해보면 좋을것같습니다.

그리고 마지막으로 좋은 개발자에 대한 개인적인 생각을 말씀해주셨는데요

> 좋은 iOS개발자는 마지막 디테일까지 신경씁니다.

이 문구를 항상 생각하면서 마지막 디테일 하나하나 구현해 나가는 개발자가 되겠습니다!!!

다음 Let us go 컨퍼런스때까지 더 좋은 개발자가 되서 더 많은 내용 정리해서 보여드리겠습니다. :]

<br>
Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
