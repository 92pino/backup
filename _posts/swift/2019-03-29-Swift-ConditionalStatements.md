---
title: Swift - 조건문 (Conditional Statements)
layout: post
date: 2019-03-29 00:00
image: /assets/images/markdown.jpg
headerImage: false
tag: Swift
category: swift, Conditional Statements
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

안녕하세요 [Pino](https://92pino.github.io) 입니다.<br>
오늘은 __흐름 제어 구문__ 중 __조건문__ 에 대해 포스팅하려합니다.

## 조건문

우선 조건문이란 이름 그대로 __"조건"__ 을 따지는 제어문인데요.<br>특정한 조건 아래서만 코드가 실행되게 하는 구문을 말합니다.
예를 들어 아이디와 비밀번호를 정확하게 입력했을 때 로그인이 가능하게 하는 상황에서 사용되겠네요.


이 조건문은 다른 언어에서와 마찬가지로 반복문과 함께 가장 기본적이라 볼수 있어요

Swift에서는 ```if```, ```guard```, ```switch```가 가장 대표적입니다.

### if 구문

if문은 ```if (조건식) { 실행내용 }```으로 구성되는데요. 조건이 참일 경우에만 내용이 실행됩니다.

```swift
var userId: String = "pino"

if userId == "pino" {
  print("아이디가 일치합니다!!")
} else {
  print("아이디가 틀렸어요ㅠㅠ")
}
```
<br>

userId라는 변수에 String 타입의 값 "pino"를 담고 조건식에서 userId와 조건식이 일치할 경우 "아이디가 일치합니다!!"라는 내용이 실행이 될거고, 일치하지 않으면 "아이디가 틀렸어요ㅠㅠ"라는 문구가 출력이 될것입니다.

여기에 만약 유저의 아이디를 받고 유저의 비밀번호까지 체크하려면 어떤 조건식을 써야하는지 알아볼까요?

```swift
var userId: String = "pino"
var userPw: Int = 1234

if userId == "pino" {
  if userPw == 1234 {
    print("아이디와 비밀번호가 모두 일치합니다!")
  } else {
    print("아이디는 맞는데 비밀번호가 틀렸네요ㅠㅠ")
  }
} else {
  print("아이디가 틀렸어요ㅠㅠ")
}
```
<br>
userId가 참일 경우 userPw가 맞는지 체크하러 가는 조건을 추가해주면 간단하게 사용자의 아이디와 패스워드가 일치하는지 체크할수 있겠죠?<br>
위 if문에서는 ```userId = "pino", userPw = 1234```가 모두 일치하므로 "아이디와 비밀번호가 모두 일치합니다"라는 문구가 출력이 되겠네요~

### guard 구문

다른 언어를 많이 안다뤄봤지만 ```guard```구문은 Swift에만 있는 독특한 문법인것 같아요.<br>
if문과 동일하게 조건식의 결과가 참인지 거짓인지에 따라 구문의 실행 여부가 결정이 되는데 guard문 같은 경우 참일 때 실행되는 코드 블록이 없습니다.<br>
주로 guard문 뒤에 오는 코드들이 실행 되기 전에 심각한 오류가 있는지 확인을 하고 오류가 있을 경우 코드 진행을 막아주는 역할을 하고있어요.<br>

```swift
// userId를 옵셔널 값으로 처리해 nil이 나올수 있는 상황을 만들어줬습니다.
var userId: String?
var userPw: Int = 1234

func checkIdPw() {
    // userId가 nil이 아닐 경우는 guard문 뒤에 코드 진행
    // userId가 nil일 경우 guard문 내부 코드 진행
    guard userId != nil else {
        print("아이디를 입력해주세요.")
        return
    }

    if userId == "pino" {
        if userPw == 1234 {
            print("아이디와 비밀번호가 모두 일치합니다!")
        } else {
            print("아이디는 맞는데 비밀번호가 틀렸네요ㅠㅠ")
        }
    } else {
        print("아이디가 틀렸어요ㅠㅠ")
    }

}
checkIdPw()
```
<br>

코드를 보면 userId에 nil값이 들어오면서 로그인을 할수 없는 오류 상황이 되니까 guard문에서 아이디를 입력하라는 메시지 출력과 동시에 함수를 막아버렸네요.<br>

코드만 봐서는 guard와 if문의 차이가 크게 없어 보이는데요<br>


guard문은 본래 실행 흐름을 종료하기 위한 목적으로 사용되는 구문이라 if문과 다르게 코드를 중첩해서 사용하지 않아도 되고 중첩 코드가 없으니 전체 코드가 더 깔끔하고 단순해지게 만들어주는 역할을 해요

### switch 구문

switch문은 경우에 따라 if문보다 더 적합한 때가 있습니다.

바로 몇 가지 선택지가 주어지고, 그에 대한 선택을 할 때죠.

("1. 프로그램 실행, 2. 대기, 3. 종료"처럼 선택지가 몇 가지 있다면 말이죠. )


<br>


게임으로 예를 들어볼까요?

다들 롤이라는 게임은 아시죠??

롤에는 5가지 라인이 있는데 플레이어마다 각 라인을 맡아 게임을 하게되는데요

5가지 라인 중 한 라인을 선택해서 플레이하게 되는 상황이 switch case문이라고 보면 될것 같습니다.

```swift
var goToLine = "AdCarry"

switch goToLine {
case "Top":
    print("저는 탑 라이너니까 탑으로 가겠습니다.")
case "Jungle":
    print("저는 정글 라이너니까 정글로 가겠습니다.")
case "Middle":
    print("저는 미드 라이너니까 미드로 가겠습니다.")
case "AdCarry":
    print("저는 원딜이니까 봇으로 가겠습니다.")
case "Support":
    print("저는 서포터니까 봇으로 가겠습니다.")
default:
    print("저는 트롤이에요~~")
}

// "저는 원딜이니까 봇으로 가겠습니다."
```
<br>
코드를 보시면 Top, Jungle, Middle 이라는 선택지는 제가 가고 싶은 라인이 아니기에 지나쳤고 AdCarry 라인이 나오자 선택을 하고 Support라인은 관심을 안가졌네요? (그렇다고 트롤을 하시면 안되요..!!!)

이처럼 제가 선택한 조건과 나열된 조건이 일치할때까지 비교를 계속 하고 일치를 할 경우 선택을 하고 게임을 진행하는게 switch 구문이라고 할 수 있습니다.

만약 Top이라는 선택지를 선택했다면 case "Top"에서 선택이 되고 다른 라인들은 관심을 안가졌겠죠?

조건이 만족해도 다른 조건들을 한번씩 툭툭 건드려보는 다른 언어들과는 다르게 스위프트는 조건이 일치하는 순간 다음 조건들은 실행되지 않은 채로 조건문이 종료가 됩니다.

---
<br>
지금까지 조건문 3가지에 대해서 다뤄봤는데요

조건문은 제가 생각하기에 기초 프로그래밍에서 제일 중요한부분입니다<br>
조건문은 서로다른 환경에서 여러가지를 동시에 처리가 가능하게 해주기 때문이죠

그렇기에 조금더 많은 노력을 드려야 한다고 생각하는데요

자주 쓰이는 문법이니 여러 상황에서 사용할 수 있게 다양한 방법으로 코드 짜는 연습을 해봐야할거같네요

그럼 다음 포스팅때 뵙겠습니다~😀






<br>
Thanks for your reading, this article is provided by [Pino](https://github.com/92pino) If reproduced,
please indicate the source：
Pino（[https://github.com/92pino](https://github.com/92pino)）
