---
title: Swift - 반복문&조건문
layout: post
date: 2018-11-24 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: Swift
category: swift
author: pino
description:
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

# 반복문
<br>
<hr>
<br>
> 주어진 조건에 의해 특정 코드 블럭을 반복적으로 실행할수 있게 해주는 구문

* for ~ in {...} 구문 ☞ 횟수에 의한 반복
* while 반복문 ☞ 조건에 의한 반복


<br><br>
## for ~ in
<br>
<hr>
<br>


일정 횟수만큼 특정 구문을 반복하고자 할 때 사용

```swift
for <루프상수> in <순회대상>{
	<실행할 구문>
}
```

순회 대상으로 사용할 수 있는 데이터 타입에는 다음과 같은 것들이 있습니다.
- 배열(Array)
- 딕셔너리(Dictionary)
- 집합(Set)
- 범위 데이터
- 문자열(String)

```swift
for row in 1...9{
	print("2 X \(row) = \(row * 2)")	// 구구단 2단 출력
}
```

* * *

<br><br><br>
## while
<br>
<hr>
<br>

주어진 조건식의 결과가 false가 될 때까지 실행 구문을 계속 반복 수행

**while구문을 사용해야 하는 경우**
- 실행 횟수가 명확하지 않을 때
- 직접 실행해보기 전까지는 실행 횟수를 결코 알 수 없을 때
- 실행 횟수를 기반으로 할 수 없는 조건일 때

```swift
while <조건식> {
	<실행할 구문>
}
```

* * *

<br><br><br>
## repeat ~ while
<hr>

조건식을 먼저 평가하여 실행 블록의 수행 여부를 결정하는 while과 달리 코드 블록을 우선 실행 한 후 조건식을 평가하여 반복 여부를 결정하여 __실행 블록의 수행을 최소 한 번은 보장__ 하는 반복문

```swift
repeat {
	<실행할 구문>
}
while <조건식>
```

```swift
var n = 1024

repeat {
	n = n * 2
}
while n < 1000

print("n = \(n)")	// 2048
```

<br><br><br>
## 조건문
<hr>
> 프로그램에서 하나 또는 그 이상의 조건값에 따라 특정 구문을 실행하도록 프로그램의 흐름을 분기하는 역할

- if
- guard
- switch

* * *

<br><br><br>
# if
<hr>

```swift
if <조건식> {
	<실행할 구문1>
} else {
	<실행할 구문2>
}
//조건식이 참일 경우 실행할 구문1 실행
//조건식이 거짓일 경우 실행할 구문2 실행
```

```swift
var browser = "Safari"
var browserName : String

if (browser == "IE"){
	browserName = "인터넷 익스플로러"
} else if (browser == "FF"){
	browserName = "파이어폭스"
} else if (browser == "Chrome"){
	browserName = "크롬"
} else if (browser == "Opera"){
	browserName = "오페라"
} else if (browser == "Safari"){
	browserName = "사파리
} else {
	browserName = "알려지지 않은 브라우저"
}

print("사용하고 계신 브라우저는 \(browserName)입니다")
```
<br><br><br>
## guard
<hr>

표현식의 결과가 참인지 거짓인지에 따라 구문 실행 여부를 결정하는 조건문이지만 if 구문과는 다르게 else는 필수이지만, 표현식이 참일 때 실행되는 블록이 없다.
**조기 종료하기 위한 목적으로 사용된다 == return의 역할**
```swift
guard <조건식 또는 표현식> else {
	<조건식 또는 표현식의 결과가 false일 때 실행될 코드>
}
```

```swift
func divide(base: Int){
	guard base != 0 else {
    	print("연산할 수 없습니다.")
        return
    }

    let result = 100 / base
    print(result)
}
```

* * *

<br><br><br>
# #available
<hr>

-- 별도 정리가 필요할듯 하다.

* * *

<br><br><br>
# switch
<hr>
입력 받은 값을 조건식 여부가 아니라 패턴으로 비교하고 그 결과를 바탕으로 실행 블록을 결정
나열된 패턴들을 순서대로 비교하다가 일치하는 첫 번째 패턴의 코드 블록을 실행

```swift
switch <비교 대상> {
	case <비교 패턴1> :
    	<비교 패턴1이 일치했을 때 실행할 구문>
	case <비교 패턴2>, <비교 패턴3> :
    	<비교 패턴2 또는 3이 일치했을 때 실행할 구문>
    default :
    	<어느 비교 패턴과도 일치하지 않았을 때 실행할 구문>
}
```

```swift
let val = 2
switch val {
	case 1 :
    	print("일치한 값은 1입니다")
    case 2 :
    	print("일치한 값은 2입니다")
    case 2 :
		print("일치한 값은 2가 더 있습니다")
    default :
    	print("어느 패턴과도 일치하지 않습니다.")
}
// 첫번째 case2가 일치하므로 실행구문
// 두번째 case2는 일치하지만 이전에 실행구문이 실행되었으므로 실행되지 않은 채로 조건문이 종료됩니다.
```

<br><br><br>
# 제어 전달문
<hr>

제어 전달문은 코드의 한 부분에서 다른 부분으로 제어 흐름을 전달하여 코드가 실행되는 순서를 변경해주는 구문입니다.
- break
- continue
- fallthrough
- return

* * *

<br><br><br>
# break
<hr>

switch 구문에서의 실행 흐름이나 반복 실행 중인 루프를 조건식의 결과에 상관 없이 즉각적으로 종료하는데 사용된다.
```swift
for row in 0...5 {
	if row > 2 {
    	break
    }

    print("\(row) was executed!")
}
// 0 was executed!
// 1 was executed!
// 2 was executed!
```

***

<br><br><br>
# continue
<hr>

continue구문 아래에 있는 실행 구문들을 건너뛰고 다음 반복을 시작하는 역할
```swift
for row in 0...5 {
	if row < 2 {
    	continue
    }

    print("executed data is \(row)")
}
// executed data is 2
// executed data is 3
// executed data is 4
// executed data is 5
```
