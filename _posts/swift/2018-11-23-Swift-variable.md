---
title: Swift - 변수
layout: post
date: 2018-11-23
tag: Swift
comments: true
category: swift
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

# 변수와 상수
<br>
<hr>
<br>
> 변수와 상수는 값을 저장할 수있다는 공통점이 있지만, 상수는 한 번 저장된 값을 다른 값으로 변경할 수 없는 반면 변수는 필요에 따라 저장된 값을 몇 번이라도 다른 값으로 변경할 수 있다. 그래서 변수는 프로그램의 실행에 따라 변하는 값을 저장하고, 상수에는 변하지 않을 값을 저장한다.

```swift
변수를 선언할 때 : var + 변수명: 변수타입
ex) var year: Int = 1999
    var message: String = "Hello, Pino!"

상수를 선언할 때 : let + 변수명: 변수타입
ex) let birthYear: Int = 1992
birthYear = 1995 (상수여서 변경 불가 -> 컴파일 오류 생김)
```

## 변수와 상수의 이름 정하기
<br>
- 알파벳과 한글 자음 및 모음, 아라비아 숫자를 사용할 수 있으며, 특수 기호나 한자, 이미지용 바이너리 코드까지 사용 가능하다.

``` swift
// 영어 및 숫자, 언더바로 정의
var str:String = "문자열"
var initInt34: Int = 37
var init_Int:Int = 100
var ㅁaB수34☺️🛴❖:String = "이것저것"
```

- 연산자와 혼동할 수 있는[+, -, \*, /] 및 공백은 변수, 상수명에 사용할 수 없다.(\_는 사용 가능)

``` swift
// 연산자와 공백은 변수나 상수명에 들어갈 수 없음.
var abc+t = "abc plus t"    // 연산자는 불가능
var abc t = "abc space t"   // 공백은 불가능

// _는 사용 가능
var abc_t = "abc underbar t"
```

- 스위프트에서 예약어나 키워드로 등록되어 있는 단어는 변수나 상수명에 사용할 수 없다.(대소문자를 바꾸어 사용은 가능)

``` swift
var class = 1       // 클래스 정의를 위한 키워드
var enum = 2        // 열거형 정의를 위한 키워드
var struct = 3      // 구조체 정의를 위한 키워드
var extension = 4   // 확장을 위한 키워드
var protocol = 5    // 프로토콜 정의를 위한 키워드
var as = 6          // 타입 캐스팅을 위한 키워드

// 단어의 일부를 대문자로 변경 후 사용 가능
var Class = 1
var Enum = 2
var Struct = 3
var Extension = 4
var Protocol = 5
var As = 6
```

- 변수, 상수명의 첫 번째 자리에 숫자가 올 수 없다.

```swift
var 1abc = 123
var 2bcd = 345

// 첫번째를 제외하고는 숫자가 들어갈 수 있다.
var a1b2c3 = 123456
```

<br><br><br>
## 자료형
<br>

스위프트 언어에는다른 언어들에서 존재하는 대부분의 자료형이 존재합니다. 다만 우리가 익숙하게 배우는 C, C++, 그리고 JAVA(자바)와는 다르게 자료형의 첫 번째 철자를 대문자로 표현하고 있습니다. Int, Float, Double, Character, String, Array, Dictionary 등 첫 번째 스펠링을 대문자로 사용하고 있으며, 그 선언 방법이 앞에서 언급했던 언어들과는 조금 다릅니다. 그럼 예를 통해 살펴보도록 하겠습니다.

```swift
let int: Int = 0
let float: Float = 0.0
let double: Double = 0.0
let char: Character = "c"
let string: String = "String"
let success = true || false
let array1: Array<Int> = [ 1, 2, 3, 4, 5 ]
let array2: [Int] = [ 1, 2, 3, 4, 5 ]
let dictionary1: Dictionary<String, Int> = [ "string1" : 1, "string2" : 2 ]
let dictionary2: [String : Int] = [ "string1" : 1, "string2" : 2 ]
```

| 자료형 | 저장할 수 있는 값의 범위 | 크기 |
| :---: | :---: | :---: |
| Int8 | 127 ~ -128 | 8bit |
| Int16 | 32,767 ~ -32,768 | 16bit |
| Int32 | 2,147,483,647 ~ -2,147,483,648 | 32bit |
| Int64 | 9,223,372,036,854,775,807 ~ -9,223,372,036,854,775,808 | 64bit |

<br><br><br>
## 타입 추론과 타입 어노테이션
<br>
swift는 데이터 타입에 매우 엄격하다. 서로 다른 데이터 타입끼리의 데이터 교환은 허용되지 않으며 캐스팅하여 형 변환을 해야 한다. 변수나 상수를 선언할 때 데이터 타입을 명시하지 않으면 알아서 컴파일러가 할당된 값을 기준으로 데이터 타입을 결정한다.

```swift
var year : Int = 1992
var name : String = "Pino"
var firstChr : Character = "P"
var distance : Double = 78.8
var pi : Float = 78.8
var flag : Bool = true
```

**타입 추론 VS 타입 어노테이션**
<br>
타입 어노테이션을 써야 할 경우는 아래 두 가지이다. 아래에 설명하는 상황 외에는 타입을 명시해주지 않아도 상관없지만 명시를 해도 오류는 없다.

- 선언과 초기화를 분리할 경우<br>- 타입 추론은 초기화시 해당 값에 대한 타입이 정해지기 때문에 선언과 초기화를 분리하면 꼭 타입 어노테이션을 명시해야 한다.

    ```swift
    //선언 + 타입 어노테이션
    var year : Int
    // 초기화
    year = 1999
    ```

- 타입 추론으로 얻어지는 타입이 아닌, 다른 타입을 직접 지정할 필요가 있을 때
<strong style="display:block; font-size:20px; margin-top:5px;">Int 대신 Float, Double 타입</strong>
 ```swift
    var num1 = 4
    var num2 : Float = 4
    print(num1) // 4
    print(num2) // 4.0
 ```
<strong style="font-size:20px">String 대신 Character 타입</strong>
 ```swift
    var value1 = "String" // String
    var value2 = "S"      // Character? String?
    print(value1) // String
    print(value2) // S
    value2 = "String2"    // value2 타입은 String
    print(value2) // String
 ```
 문자열이 아닌 문자 S를 담으려고 value2를 선언했지만
value2는 String 타입이 되었다.
Character 타입으로 선언하려면 타입을 명시해야 한다.

    <strong style="font-size:20px">Double 대신 Float 타입</strong>
    Double와 Float는 값 오차가 차이가 있기 때문에
    더 정확한 값을 필요로 한다면 Double로 타입을 명시해야 한다.

##  타입이 다른 변수끼리의 결합
<br>
<hr>
<br>

```swift
var stmt = "Pino의 키는"	// String
var height = 178		  // Int

//height Int를 String으로 타입 변환
var stmtHeight = stmt + String(height)
//Pino의 키는 178
```

## 문자열 템플릿 내부 계산
<br>
<hr>
<br>

```swift
// 상수와 변수 정의
let apple = 3
let banana = 2
let orange = 4

// 문자열 템플릿을 사용한 문자열 결합
let desc = "과일은 총 \(apple + banana + orange)개입니다."
print(desc) // 과일은 총 9개입니다.
```
