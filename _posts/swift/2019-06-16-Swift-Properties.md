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

### Lazy Properties (지연 저장 프로퍼티)
지연 저장 프로퍼티는 값이 호출되기 전까지는 계산되지 않는 프로퍼티입니다.

야곰님의 책에서 보면 클래스 인스턴스의 저장 프로퍼티로 다른 클래스 인스턴스나 구조체 인스턴스를 할당해야 할 때 초기화하면서 저장 프로퍼티로 쓰이는 인스턴스를 한번에 생성하면서 모든 저장 프로퍼티를 사용할 필요가 없을 때 지연 저장 프로퍼티를 사용한다고 하는데요

공식 홈페이지 lazy properties 코드를 보면서 다시 한번 이해해보도록 하겠습니다 :]

```swift
class DataImporter {
    // DataImporter는 외부에서 데이터를 가져오는 클래스로 초기화 하는데 매우 많은 시간이 소요된다고 가정합니다.
    var filename = "data.txt"
    // 외부 파일명은 "data.txt"
}

class DataManager {
    lazy var importer = DataImporter()
    var data = [String]()
}

let manager = DataManager() // DataManager의 인스턴스를 생성 (이미 초기화가 되어있어서 init이 필요없음)
manager.data.append("Some data") // DataManager의 data 배열에 "Some data"를 append시킨다.
manager.data.append("Some more data") // DataManager의 data 배열에 "Some more data"를 또 append시킨다.
// 하지만 DataImporter 인스턴스는 이 시점에 생성돼 있지 않습니다.
```

```manager```에 데이터를 아무리 많이 넣어도 실제도 ```DataImporter```라는 import 프로퍼티가 생성이 되지 않고 있네요<br>
바로 importer라는 DataImporter의 인스턴스가 __lazy__ 로 선언이 되어있기 때문인데요<br>
lazy로 선언을 하지 않았다면 바로바로 importer가 생성이 되었겠지만 ```manager.importer.filename```이 호출되기 전까지는 생성되지 않습니다~

한번 값이 생성되는지 봐볼까요?
```swift
print(manager.importer.filename)    // "data.txt"
```

다른 코드를 봐보도록 하겠습니다. (예제는 많은게 좋으니까요~)<br>
이번엔 야곰님 책의 예제인데요

```swift
struct CoordinatePoint {
    var x: Int = 0  // 저장 프로퍼티
    var y: Int = 0  // 저장 프로퍼티
}
// 초기화를
class Position {
    lazy var point: CoordinatePoint = CoordinatePoint()
    let name: String

    init(name: String) {
        self.name = name
    }
}

let pinoPosition: Position = Position(name: "pino")
```

여기까지는 point 프로퍼티의 CoordinatePoint가 생성이 되지 않는데요


```swift
print(pinoPosition.point)   // x: 0, y: 0
```

point 프로퍼티로 처음 접근할 때 point 프로퍼티의 CoordinatePoint가 생성이 됩니다.

지연 저장 프로퍼티를 잘 사용하면 불필요한 성능저하나 공간 낭비를 줄일 수 있다고 하는데요<br>
다시 한번 개념을 정리해 보자면

1. 지연 저장 프로퍼티로 선언하기 위해서는 프로퍼티 선언 앞에 ```lazy``` 키워드를 선언해 주어야 하고, 꼭 __var__ 변수 선언을 해야 합니다!<br>
(상수로 선언할 경우 인스턴스가 완전히 생성되기 전에 초기화해야하기 때문에 값을 할당하는 지연 저장 프로퍼티와는 맞지 않기 때문이죠)
2. 지연 저장 프로퍼티는 주로 복잡한 클래스나 구조체를 구현할 때 많이 사용
3. 외부요인에 의해 초기화가 완료될때가지 값을 알 수 없는 프로퍼티의 값을 초기화 할때 유용
4. 지연 저장 프로퍼티를 잘 사용하면 불필요한 성능저하나 공간 낭비를 줄일 수 있습니다.

> 다중 스레드 환경에서 지연 저장 프로퍼티에 동시다발적으로 접근할 때에는 한번만 초기화 된다는 보장이 없습니다. 생성되지 않은 지연저장 프로퍼티에 많은 스레드가 비슷한 시점에 접근한다면, 여러번 초기화 될 수 있습니다.


먼저 저장 프로퍼티에 대해 알아보았는데요. 지연 저장 프로퍼티가 확 와닿지는 않지만 사용법을 알았으니 더 연습해보면서 개념 이해를 해야겠어요.

다음번에는 [연산 프로퍼티]()에 대해 포스팅을 하겠습니다. :)

## 참고
- swift 공식 문서 - [The Swift Programming Language](https://docs.swift.org/swift-book/LanguageGuide/Properties.html)
- zedd님 - [Stored Properties](https://zeddios.tistory.com/243)
- 야곰님 - 스위프트 프로그래밍

Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
