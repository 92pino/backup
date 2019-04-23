---
title: Swift - 함수(Function)
layout: post
date: 2019-03-24 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: Swift
category: swift, function
author: pino
description:
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

# 함수
<br>
<hr>
<br>

> 함수 대부분은 작업의 가장 작은 단위이자 하나의 작은 프로그램이기도 합니다.<br>
> "하나의 프로그램은 하나의 큰 함수다"라는 말이 있듯이, 함수는 프로그램을 이루는 주된 요소 중 하나입니다.

오늘은 이러한 함수에 대해서 포스팅 해보도록 하겠습니다.

함수는 상황이나 위치에 따라 다른 용어로 부르기도 하는데

- __구조체+__, __클래스__, __열거형__ 등 특정 타입에 연관되어 사용하는 함수인 ```메서드```
- 모듈 전체에서 전역적으로 사용할 수 있는 ```일반 함수```

로 구분되어 있습니다.<br>
즉, 함수가 위치하거나 사용되는 범위 등에 따라 호칭만 달라질 뿐, 함수라는 것 자체에는 변함이 없다는 뜻입니다.


## 이런 함수는 어떻게 선언하고 어떻게 호출을 할까요?

함수의 기본형태는 다음과 같습니다.
```swift
func 함수명 (매개변수...) -> 반환 타입 {

  실행 구문
  return 반환값

}
```
<br>
하나씩 살펴보면
- 먼저 함수를 정의하는 키워드 func 작성
- 그 뒤에 함수명을 지정해준 후 매개변수는 소괄호()로 감싸줍니다
- 반환값이 있을 경우 -> 표시 후 어떤 타입이 반환될 것인지 명시해줍니다. (없을경우에는 생략 가능)
- 그 후 실행구문을 작성하고 반환값이 있을 경우 `return 반환값` 을 작성해 줍니다.

## 매개변수

매개변수란 함수를 정의할 때 외부로부터 받아들이는 전달 값의 이름을 의미하는데요<br>
스위프트의 함수는 매개변수를 어떻게 정의하냐에 따라서도 모습이 크게 달라질수 있습니다!<br>
어떻게 달라지는지 한번 알아볼까요?

__✔︎ 매개변수가 없는 함수와 매개변수가 여러 개인 함수__

함수에 매개변수가 필요 없다면 매개변수 위치를 공란으로 비워두면 됩니다.

```swift
func helloPino() -> String {
  return "Hello, Pino!!"
}

print(helloPino())
// Hello, Pino!! 출력
```
<br>
매개변수가 여러개 필요한 함수를 정의할 때는 ,로 매개변수를 구분하는데<br>이 매개변수는 ```매개변수명: 매개변수 타입```으로 작성합니다.

```swift
func sayHello(myName: String, yourName: String) -> String {
  return "안녕하세요 \(yourName)! 반갑습니다!! 저는 \(Pino)입니다."
}

print(sayHello(myName: "Pino", yourName: "여러분"))
// 안녕하세요 여러분! 반갑습니다!! 저는 Pino입니다.
```
<br>
__✔︎ 매개변수 이름과 전달인자 레이블__

위 함수를 보면 myName과 yourName이라는 매개변수 이름을 사용해서 함수를 호출했는데요<br>
이 매개변수 외에도 ```전달인자 레이블```이라고 하는 친구를 별도로 지정해서 함수 외부에서 매개변수의 역할을 좀 더 명확하게 표현하고자 할 때 사용 가능합니다.

```swift
func welcome(from myName: String, _ name: String) -> String {
  return "어서오세요 \(name)님! \(myName)의 블로그에 오신것을 환영합니다!"
}

print(welcome(from: "Pino", "방문자"))
// 어서오세요 방문자님! Pino의 블로그에 오신것을 환영합니다!
```
<br>
welcome의 호출 값을 보시면 매개변수만 있을 때와는 다르게 호출된다는게 보이실거에요
매개변수는 함수 내부에서만 사용 가능하고 전달인자 레이블은 함수 외부에서 사용할수 있습니다.<br>
그리고 만약 전달인자 레이블을 사용하고 싶지 않다면 `_` 를 사용하여 생략이 가능합니다.

<br>
__✔︎ 매개변수 기본값__

외부에서 호출할수 있는 매개변수는 기본값을 지정하는것이 가능합니다.

```swift
func movieTime(_ movieName: String, time: Int = 3) -> String {
  return "\(movieName)는(은) \(time)시에 시작합니다."
}

print(movieTime("캡틴마블"))
// 캡틴마블는(은) 3시에 시작합니다.

// 기본 값은 변경이 가능합니다.
print(movieTime("캡틴마블", time: 5))
// 캡틴마블는(은) 5시에 시작합니다.
```

<br>
__✔︎ 가변 매개변수와 입출력 매개변수__

매개변수가 몇개가 들어올지 처음부터 알면 참 좋겠지만..<br> 코드를 쓰다보면 가변 매개변수가 몇개 들어와야될지 난감한 상황이 있는데<br>
이때 사용하는게 ```가변 매개변수```입니다. 가변 매개변수는 타입 뒤 ...를 사용하여 작성할수 있습니다.<br>
이 가변 매개변수는 0개 이상의 값을 받아올 수 있으며, 인자 값은 배열처럼 사용할수 있습니다.

```swift
func whatIeat(me: String, foods names: String...) -> String {
  var result: String = ""

  for food in names {
    result += "\(food)도 먹고 "
  }

  return "\(me)는 \(result)싶다"
}

print(whatIeat(me: "Pino", foods: "Steak", "Macaroon", "Americano"))
// Pino는 Steak도 먹고 Macaroon도 먹고 Americano도 먹고싶다
```

<br>
함수로 전달한 파라미터의 값을 함수 안에서 변경했을 때 변경된 값을 함수 밖에서 다시 참조하기 위해 스위프트에서는 ```inout``` 키워드를 사용합니다.<br>
그리고 함수를 호출할 때 전달하는 변수 앞에 &를 붙여 사용합니다.<br><br>
inout 키워드는 함수에 변수를 전달하고 다시 그 변수를 참조할 수 있도록 하는데요.<br>
코드를 보면 이해하기가 더 쉬울겁니다.

```swift
func midnightSnack(food: inout String) {
  print("\(food) 먹고싶다..")
  food = "피자"
}

var food2 = "족발"
midnightSnack(food: &food2)

// 족발 먹고싶다...
```

<br>
함수의 전달인자로 값을 전달할 때는 보통 Call By Value(값 복사)가 일어나 전달을 하게되는데<br>
값에 의한 호출(Call by Value)와 참조에 의한 호출(Call by Reference)는 추후에<br>
클래스와 구조체 포스팅 할때 따로 정리해서 포스팅 해놓겠습니다.

## 반환 타입

위에 이미 몇번 코드상으로 언급은 했지만 다시 한번 반환 타입에 대해 간단히 언급하고 넘어가려 합니다.<br>
함수는 특정 연산을 실행후 결과값을 반환하는데요<br>
`() -> 타입`을 통해 반환값이 있는 함수를 만들수도 있고,<br>
 반대로 결과값을 반환하지 않는 함수에서는<br>
`() -> Void`를 사용해 반환값이 없음을 표시하거나 -> Void를 생략하고 ()만 사용해서 함수를 나타냅니다.

```swift
func studySwift() -> String {
  return "swift 공부를 합시다."
}

print(studySwift())
// swift 공부를 합시다.

func writePosting(who myName: String, what study: String) {
  print("\(myName)는 블로그에 \(study) 포스팅을 하고있습니다.")
}

writePosting(who: "Pino", what: "Swift")
// Pino는 블로그에 Swift 포스팅을 하고있습니다.

func end() -> Void {
  print("반환타입 끝!")
}

end()
// 반환타입 끝!
```

<br>
Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
