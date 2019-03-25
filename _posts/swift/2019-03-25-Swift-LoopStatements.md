---
title: Swift - 반복문 (Loop Statements)
layout: post
date: 2019-03-25 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: Swift
category: swift, Loop Statements
author: pino
description:
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

# 흐름 제어 구문

<br>

<hr>

<br>



> 프로그래밍 과정에서 작성하는 소스 코드를 구문(Statement)라고 하고, 프로그램 실행 과정에서 실행 흐름을 능동적으로 제어하기 위한 목적으로 사용되는 구문을 `흐름 제어 구문`이라고 합니다.

<br>
오늘은 __흐름 제어 구문__ 중 __반복문__ 에 대해 포스팅하겠습니다.



구문은 크게 단순 구문과 흐름 제어 구문으로 나누어질수 있는데요

단순하게 식, 값 표현부터 각종 객체의 선언이나 정의, 심지어 변수나 상수 선언, 연산, 앞으로 포스팅 하게 될 함수나 구조체, 클래스, 열거형 등 모두 단순구문에 포함됩니다.



반면 흐름 제어 구문은 성격에 따라 다음과 같이

- 반복문 (Loop Statements)

- 조건문(Conditional Statements)

- 제어 전달문(Control Transfer Statements)

로 나누어집니다.

## 반복문

반복이라는 건 간단하게 말해 __'같은 일을 되풀이함'__ 이라는 사전적 의미를 가지고 있는데요.<br>
만약 'Hello World'라는 단어를 1000번 이상 출력해야 하는데 사람이 하나하나 수작업을 한다면 실수나 오류가 날 확률이 높겠죠?
이 때 사용하는 것이 `반복문`이라는 존재입니다.<br>
프로그래밍으로 주어진 조건에 의해 특정 코드 블록을 반복적으로 실행하는 구문이죠


Swift에서는 크게 두가지의 반복문이 존재합니다.
- 정해진 횟수만큼만 반복하는 __For 반복문__
- 주어진 조건이 false가 될 떄까지 계속해서 구문을 반복 실행하는 __While 반복문__

먼저 For 반복문에 대해 알아보겠습니다.

## For~in 구문

가장 기본적인 For~in 구문은 다음과 같은 형태로 이루어집니다.
```swift
for <루프 상수> in <순회 대상> {

  <실행할 구문>

}
```
<br>

### 루프 상수

루프상수는 구문이 반복될 때마다 순회 대상이 포함하고 있는 개별 아이템들을 차례로 넘겨받아 임의로 저장하고, 실행 블록 내에서 사용할 수 있도록 해주는 역할을 하는데요.
루프 구문이 순회할 때마다 자동으로 재선언되므로 상수임에도 불구하고 let 키워드를 사용하여 직접 선언할 필요가 없습니다.

### 순회 대상

주로 순번을 가지는 집단 자료형이나 범위를 가지는 데이터 등으로 이루어지는데, 순회 대상의 길이나 포함하고 있는 아이템의 개수만큼 구문이 반복 실행됩니다.
순회 대상에 들어갈 수 있는 데이터 타입으로는 `배열(Array)`, `딕셔너리(Dictionary)`, `집합(Set)`, `범위 데이터`, `문자열(String)`이 있습니다.

for ~ in 구문의 가장 기본적인 예를 들면,

```swift
var lang = "swift"

for char in lang.characters {
  print("개별 문자는 \(char)입니다.")
}
// 개별 문자는 s입니다.
// 개별 문자는 w입니다.
// 개별 문자는 i입니다.
// 개별 문자는 f입니다.
// 개별 문자는 t입니다.
```
<br>
for ~ in 구문을 사용할 때 기본적으로는 루프 상수를 선언하여 값을 저장하고 사용할수 있게 해주는데 단순히 순회 대상의 크기만큼 반복하는 것이 목적일 경우 루프상수가 필요하지 않을 수도 있습니다.
이때에는 \_를 사용하여 루프 상수를 생략할 수 있습니다.

```swift
let size = 5
let padChar = "0"
var keyword = "3"

for _ in 1...size {
  keyword = padChar + keyword
}

print("\(keyword)")
```

## While 구문

앞에서 살펴본 for~in 구문과 달리 while구문은 주어진 조건식의 결과가 false가 될 때까지 실행 구문을 계속 반복 수행하는데요.<br>
다시 말해 __'조건을 만족하는 동안은 계속 실행'__ 한다고 생각하시면 될것 같아요.
<br>
같은 반복을 나타내는 두 구문이여서 어디에 사용될지 헷갈릴건데 while 구문을 사용해야 하는 몇가지 경우만을 제외하고는 대다수가 for~in 구문으로 처리합니다.
- 실행 횟수가 명확하지 않을 때
- 직접 실행해보기 전까지는 실행 횟수를 결코 알 수 없을 때
- 실행 횟수를 기반으로 할 수 없는 조건일 때
<br>

while 구문은 다음과 같은 형태로 이루어집니다.
```swift
while <조건식> {

  <실행할 구문>

}
```
<br>
이런 while 구문에서도 주의해야 할 사항이 있는데요!!<br>
그건 바로 조건식에 true값이 들어가서 한없이 반복 실행되는 무한 루프가 만들어질 수도 있습니다.
이 점만 주의하시면 while 구문을 사용하는데 큰 무리가 없을것입니다.

```swift
var n = 2
while n < 1000 {

  n = n * 2

}

print("n = \(n)")
// n = 1024
```

## repeat~while 구문

```swift
repeat {

  <실행할 구문>

}
while <조건식>
```
<br>
swift에만 있는 문법으로 다른 언어에서는 do~while 구문에 해당하는 반복문입니다.
조건식을 먼저 평가하여 실행 블록의 수행 여부를 결정하는 while 구문과는 다르게 repeat~while 구문은 코드 블록을 일단 실행한 다음에 조건식을 평가하여 반복 여부를 결정합니다.
다시 말해 조건식이 false 여도 실행 블록이 최소 한번은 실행이 된다는 것입니다.

다음 예문을 보시면 이해가 빠르게 될것같은데요
```swift
var n = 1024

repeat {

  n = n * 2

}

while n < 1000

print("n = \(n)")
// n = 2048
```
<br>
조건식에서 이미 n은 1000을 넘는 값이지만 repeat 블록이 존재하므로 n = 2048이 출력되게 됩니다.

요약하자면,
<br>
```
✔︎ For~in 구문 : 횟수에 의한 반복

✔︎ while 구문 : 조건에 의한 반복

✔︎ repeat~while : 조건에 의한 반복이지만 조건이 fasle일 경우 최초 1번은 실행
```

<br>
Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
