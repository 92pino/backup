---
layout: post
title: 코코아 프레임워크 VS 코코아 터치 프레임워크
date:   2019-03-30 02:00:00 -0701
category: [theory]
tags: [Theory]
comments: true
---

안녕하세요 [Pino](https://92pino.github.io) 입니다.<br>
오늘은 __코코아 프레임워크 vs 코코아 터치 프레임워크__ 에 대해 포스팅하려합니다.<br>

---
<br>

처음 공부를 시작할때 부터 코코아 라는 단어를 많이 들었었는데요<br>
![](https://user-images.githubusercontent.com/45158632/55285079-05a3f180-53bf-11e9-979a-4bb1d1f7a564.jpg){: width="200" height="200"}(이 코코아는 아닌거같은데...)<br>
## 우선 코코아 란 무엇일까요??

<br>
Cocoa란 애플에서 판매하던 하드웨어 매킨토시의 어플리케이션을 개발하기 위해 사용되던 프레임워크가 바로 ```Cocoa Framework```입니다.
애플 제품을 사용하는사람과 ios개발을 하는 사람이라면 누구나 사용하는 ```사파리(Safari)```, ```Xcode```가 대표적인 예시인데요<br>
![](https://user-images.githubusercontent.com/45158632/55285166-16edfd80-53c1-11e9-9fca-2e78a7c63d7e.jpg){: width="500" height="200"}
<br><br>
심지어 제어버튼 마저도 코코아 프레임워크 입니다.<br>우리가 직접 구현해주지 않아도 코코아 프레임워크에서 제공하는 NSWindow라는 객체를 사용하여 윈도우를 생성하면 자동으로 추가되는 기능입니다.


## Cocoa framework의 양대 산맥, Foundation과 AppKit

Apple이 제공하는 Framework의 종류는 매우 많습니다만, 가장 핵심이 되는 Framework는 2가지 입니다.

- Foundation Framework
- AppKit Framework

### Foundation Framework

Foundation은 원시 데이터 타입(String, Int, Double), 컬렉션 타입(Array, Dictionary, Set) 및 운영체제 서비스를 사용해 애플리케이션의 기본적인 기능을 관리하는 프레임워크 입니다.

- Foundation 프레임워크는 데이터 타입, 날짜 및 시간 계산, 필터 및 정렬, 네트워킹 등의 기본 기능을 제공합니다.
- Foundation 프레임워크에서 정의한 클래스, 프로토콜 및 데이터 타입은 iOS뿐만 아니라 macOS, watchOS, tvOS 등 모든 애플 SDK에서 사용됩니다.

### AppKit Framework
Mac OS X에서 Foundation과 함께 Cocoa의 핵심을 이루는 또 하나의 Framework는 Application Kit입니다. 보통 AppKit라고 많이 얘기하는데, 주로 유저 인터페이스에 관련된 기능을 제공하며 Foundation과 마찬가지로 NS로 시작하는 클래스들을 가지고 있습니다.

## 우선 코코아터치 란 무엇일까요??
![](https://user-images.githubusercontent.com/45158632/55285032-f83a3780-53bd-11e9-9d01-2c2d9f281c2b.jpg)<br>
Cocoa Touch라고 불리는 것은 iOS 애플리케이션 개발 환경으로, 애플리케이션의 다양한 기능 구현에 필요한 여러 프레임워크를 포함하는 최상위 레벨의 프레임워크입니다.

- '코코아'라는 단어는 Objective-C 런타임을 기반으로하고, NSObject를 상속받는 모든 클래스 또는 객체를 가리킬 때 사용합니다.
- '코코아' 또는 '코코아 터치'는 iOS 또는 macOS의 전반적인 기능을 활용해 애플리케이션을 제작할 때 사용하는 프레임워크입니다.
- '코코아 터치'는 핵심 프레임워크인 UIKit과 Foundation을 포함합니다.

## Cocoa Touch framework의 양대 산맥, Foundation과 UIKit
### UIKit Framework
UIKit은 iOS 애플리케이션의 사용자 인터페이스를 구현하고 이벤트를 관리하는 프레임워크입니다.

- UIKit 프레임워크는 제스처 처리, 애니메이션, 그림 그리기, 이미지 처리, 텍스트 처리 등 사용자 이벤트 처리를 위한 클래스를 포함합니다.
- 또한 테이블뷰, 슬라이더, 버튼, 텍스트 필드, 얼럿 창 등 애플리케이션의 화면을 구성하는 요소를 포함합니다.
- UIKit 클래스 중 UIResponder에서 파생된 클래스나 사용자 인터페이스에 관련된 클래스는 애플리케이션의 메인 스레드(혹은 메인 디스패치 큐)에서만 사용하세요.
- UIKit은 iOS와 tvOS 플랫폼에서 사용합니다.
