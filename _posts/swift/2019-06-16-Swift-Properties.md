---
title: Swift - 저장 프로퍼티 - Stored Properties
layout: post
date: 2019-06-16 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: Swift
category: swift
author: pino
description:
---


안녕하세요 [Pino](https://92pino.github.io) 입니다.<br>
오늘은 프로퍼티 종류 중 __저장 프로퍼티(Stored Properties)__ 에 대해 포스팅하려합니다.<br>

---

저장프로퍼티를 공부하기 이전에 프로퍼티가 무엇인지 간단하게 짚어보고 가겠습니다~

## Properties

__프로퍼티는 클래스(Class), 구조체(Struct), 열거형(enum) 등에 관련된 값을 뜻합니다.__

프로퍼티에는 크게 3가지 종류로 나뉘어집니다.

- Stored Properties (저장 프로퍼티)
    - 인스턴스의 변수 또는 상수를 의미하고, 구조체와 클래스엠서만 사용할 수 있습니다.
- Computed Properties (연산 프로퍼티)
    - 값을 저장하는 것이 아닌 특정 연산을 실행한 결과값을 의미하며 __구조체, 클래스, 열거형__ 에 사용할 수 있습니다.
- Type Properties (타입 프로퍼티)
    - 저장 프로퍼티와 연산 프로퍼티와는 다르게 특정 타입에 사용되는 프로퍼티입니다.

### Stored Properties

저장 프로퍼티는 간단하게 클래스 또는 구조체의 인스턴스와 연관된 값을 저장한다는 단순한 개념의 프로퍼티입니다.

var 키워드를 사용하면 __변수 저장 프로퍼티__ 가 될수 있고, let 키워드를 사용하면 __상수 저장 프로퍼티__ 가 될 수도 있습니다.

또한 저장 프로퍼티를 선언할 때 프로퍼티 "기본값"을 지정할 수 있고 또 이 값을 수정할 수도 있습니다.

간단한 예제를 보면서 저장 프로퍼티에 대해 더 알아보겠습니다.

```swift
// 구조체
struct Pizza {
    var pizzaCount: Int
    let pizzaName: String
}

var currentCount = Pizza(pizzaCount: 10, pizzaName: "페퍼로니")


// 클래스
class PizzaInfo {
    var count: Int
    let pizzaName: String
    
    init(pizzaName: String, count: Int) {
        self.pizzaName = pizzaName
        self.count = count
    }
}

let totalPizzaInfo: pizzaInfo = pizzaInfo(pizzaName: "페퍼로니", count: 10)
```

먼저 구조체 코드를 봐볼까요?

Pizza라는 구조체 내부에 currentCount라는 변수 저장 프로퍼티와 pizzaName이라는 상수 저장 프로퍼티가 생성되어있고, 초기값은 비어있네요<br>
그리고 pizzaCount에 값을 주기 위해 currentCount라는 Pizza의 인스턴스가 생성되어 있고 pizzaCount에는 10이 들어가있습니다<br>
(구조체는 기본적으로 저장 프로퍼티를 매개변수로 갖는 이니셜라이저가 있습니다)

pizzaCount라는 저장 프로퍼티는 변수 저장 프로퍼티로 선언되어 있어서 언제든지 값을 변경 할 수 있는 반면 pizzaName은 "상수"로 선된되어 있기 때문에 값을 변경하게 된다면 에러메시지가 발생하게 됩니다.

여기서 만약 var로 선언되어 있는 currentCount를 let으로 변경한 후 pizzaCount의 값을 수정하게 된다면 어떻게 될까요?

![구조체 변수를 상수로 변경시 에러](https://user-images.githubusercontent.com/45158632/59562834-59dc7a80-906c-11e9-968f-92d6bf9994ca.png)

구조체를 이해하신분들은 단번에 눈치채셨을겁니다<br>
구조체가 value 타입이기 때문에 에러 메시지가 발생하게 됩니다. - 참고([Swift - 값타입과 참조타입](https://92pino.github.io/theory/2018/12/01/swift-%EA%B0%92%ED%83%80%EC%9E%85%EA%B3%BC-%EC%B0%B8%EC%A1%B0%ED%83%80%EC%9E%85/))


다음은 클래스 코드를 보도록 하겠습니다.

Pizza구조체와 동일하게 변수 저장 프로퍼티, 상수 저장 프로퍼티가 하나씩 보이네요~<br>
그리고 구조체와는 다르게 init 초기화 함수가 들어가있는데요<br>
클래스는 구조체와는 다르게 옵셔널이 아니라면 프로퍼티의 기본값을 지정해주거나 사용자 이니셜라이저를 통해 반드시 초기화를 해주어야합니다.<br>
(클래스 저장프로퍼티를 사용할때 init을 빼먹지말고 꼭 사용해야합니다!)



Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
