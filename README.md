## 목차
### [1장. 자바스크립트 시작하기](#1장-자바스크립트-시작하기-1)
### [2장. 데이터 형과 연산자](#2장-데이터-형과-연산자-1)
### [3장. 제어문](#3장-제어문-1)
### [4장. 함수](#4장-함수-1)
### [5장. 객체](#5장-객체-1)
### [6장. 숫자](#6장-숫자-1)
### [7장. 문자열](#7장-문자열-1)
### [8장. 정규 표현식](#8장-정규-표현식-1)
### [9장. 배열](#9장-배열-1)
### [10장. 내장 객체](#10장-내장-객체-1)
### [11장. 문서 객체 모델(DOM)](#11장-문서-객체-모델dom-1)
### [12장. 이벤트](#12장-이벤트-1)
### [13장. 브라우저 객체 모델(BOM)](#13장-브라우저-객체-모델bom-1)

---

## 1장. 자바스크립트 시작하기
## 1.1 자바스크립트와 개발 도구  
- 자바스크립트는 사용자 컴퓨터 측(클라이언트 단)에서 웹 페이지를 동적으로 만드는 데 사용됨.
- HTML은 자동차 부품, CSS는 자동차의 외관, 자바스크립트는 자동차를 움직이는 엔진.
- 자바스크립트는 웹 페이지에서 일어나는 모든 동작을 제어하는 데 사용됨.
### 1.1.1 웹과 자바스크립트  
- 자바스크립트로 작성한 프로그램을 스크립트(Script)라고 부름.
- 스크립트는 웹 페이지의 HTML 문서 안에 들어가 있으며, 브라우저가 웹 페이지를 불러올 때 자동으로 실행됨.
- 스크립트는 컴파일 과정을 거치지 않음.
- 자바스크립트로 작성된 코드는 브라우저에 탑재된 자바스크립트 엔진에서 바로 실행됨.
- 현재는 자바스크립트 기반의 Node.js라는 런타임 환경이 등장하여 웹 서버 쪽에서도 자바스크립트를 사용할 수 있게 됨.
---
## 1.2 비주얼 스튜디오 코드 설치  
---
## 1.3 자바스크립트 코드 작성과 실행  
- 자바스크립트 코드는 ``<script></script>`` 사이에 들어감.
- innerHTML 속성을 이용하여 브라우저 화면에 `"안녕하세요"`를 출력하는 예제
```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
	</head>
	<body>
		<p id="show"></p>
		<script>
			document.getElementById("show").innerHTML = "안녕하세요";
		</script>
	</body>
</html>
```
---
## 1.4 데이터 출력  
### 1.4.1 innerHTML로 출력하기
- 브라우저 안에 있는 HTML 요소에 데이터 출력.
```html
<body>
	<p id="show"></p>
	<script>
		document.getElementById("show").innerHTML = 10 + 20;
	</script>
</body>
```
### 1.4.2 document_write()로 출력하기  
- 브라우저에 간단한 데이터 출력.
- 실제 프로그램에서는 잘 사용되지 않음.
```html
<body>
	<script>
		document.write(10 + 20);
	</script>
</body>
```
### 1.4.3 alert()로 알림창에 출력하기  
- 알림창에 데이터 출력.
```html
<body>
	<script>
		alert(10 + 20);
	</script>
</body>
```
### 1.4.4 console.log()로 콘솔에 출력하기  
- 브라우저 콘솔에 데이터 출력.
- 개발자 도구에서 확인.
```html
<body>
	<script>
		console.log(10 + 20);
	</script>
</body>
```
---
## 1.5 주석문  
- `/* */` : 여러 줄의 주석을 다는 데 사용.
- `//` : 한줄의 주석을 다는 데 사용.
```html
<body>
	<script>
		/* 이것은 여러 줄의
		주석을 다는 데 사용합니다. */
		// 이것은 한줄의 주석을 다는 데 사용합니다.
		console.log(10 + 20);
		// console.log(100);
	</script>
</body>
```
---
## 2장. 데이터 형과 연산자
## 2.1 변수란?  
- 변수는 숫자나 문자와 같은 데이터를 저장하는 박스와 같은 것임.
- 좀 더 정확히 말하면 데이터가 컴퓨터 메모리에 저장되는 주소를 가리킴.
### 2.1.1 변수 선언  
- `var`, `let`, `const` 키워드로 변수를 선언할 수 있다.
1. **var**:
    - **스코프**: 함수 스코프를 가짐. 함수 내에서 선언된 경우 해당 함수 내에서 유효함.
    - **호이스팅**: 선언된 위치와 상관없이 함수의 최상단으로 호이스팅됨.
    - **재할당**: 변수의 값을 재할당할 수 있음.

2. **let**:
    - **스코프**: 블록 스코프를 가짐. `{}`로 둘러싸인 블록 내에서만 유효함.
    - **호이스팅**: 호이스팅이 발생하지만, 선언 전에 접근할 수 없음. (일시적 사각지대(Temporal Dead Zone) 참조).
    - **재할당**: 변수의 값을 재할당할 수 있음.
```js
// let 키워드는 필요에 따라 값을 재할당할 수 있다.
let name = "홍길동";
console.log(name); // 홍길동

name = "김길동";
console.log(name); // 김길동
```

3. **const**:
    - **스코프**: 블록 스코프를 가짐. `{}`로 둘러싸인 블록 내에서만 유효함.
    - **호이스팅**: `let`과 마찬가지로 호이스팅이 발생하지만, 선언 전에 접근할 수 없음.
    - **재할당**: 한 번 할당된 후에는 변수의 값을 변경할 수 없음(상수로 사용). 단, 객체나 배열 내부의 속성은 변경할 수 있음.
```js
// const 키워드는 값을 재할당할 수 없다.
const name = "홍길동";
console.log(name); // 홍길동

name = "김길동"; // 오류 발생
console.log(name);
```
### 2.1.2 변수 이름 짓기  
- 자바스크립트에서 변수의 이름을 식별자(identifier)라고 하며, 식별자를 만들 때 사용되는 몇 가지 규칙이 있음.
1. 변수 이름에는 영어 알파벳, 숫자, 밑줄(`_`), `$`를 사용.
2. 변수 이름은 숫자로 시작할 수 없음.
3. 변수 이름은 대소문자를 구분.
4. 변수 이름을 길게 지을 경우에는 밑줄(`_`)이나 `CamelCase`를 사용
```js
// 아래는 모두 유효한 변수 이름이다.
let a = 5;
let font1 = "돋움";
let _price = 30000;
let max_width = 600;
let maxWidth = 800;

document.write(a + "<br />");
document.write(font1 + "<br />");
document.write(_price + "<br />");
document.write(max_width + "<br />");
document.write(maxWidth + "<br />");
```


---
## 2.2 데이터 형  
### 2.2.1 숫자  
- 자바스크립트에서 숫자 데이터에는 정수(integer)와 부동 소수점 숫자(floating point number)가 사용됨.
```js
// 숫자 데이터 사용 예
let a = 3; // 정수
let b = 5.7; // 부동 소수점 숫자
let c = 123e3; // 123000
let d = 123e-3; // 0.123

document.write(a + "<br />");
document.write(b + "<br />");
document.write(c + "<br />");
document.write(d + "<br />");
```
### 2.2.2 Bigint  
- 15자리 이상의 정수를 사용하려면 Bigint 형을 사용해야 함.
- 정수 데이터 제일 뒤에 `n`을 붙이면 그 정수는 Bigint 형으로 저장됨.
```js
// 일반 정수와 Bigint 데이터 형 사용 예
let a = 999999999999999; // 15개의 정수
let b = 9999999999999999; // 16개의 정수
let c = 9999999999999999n; // Bigint에서는 정수 끝에 n을 붙임

document.write(a + "<br />"); // 999999999999999
document.write(b + "<br />"); // 10000000000000000 → 값이 정확하게 저장되지 않음
document.write(c + "<br />"); // 9999999999999999
```
### 2.2.3 문자열  
- 문자열(string)은 하나 이상의 문자를 표현하는 데 사용됨.
- 문자열에서는 문자들을 큰 따옴표나 작은 따옴표로 감싸야 함.
```js
// 문자열 사용 예
let text1 = "사과";
let text2 = '오렌지';

document.write(text1 + "<br />");
document.write(text2);
```
- 문자열의 `length` 프로퍼티를 이용하면 문자열의 길이(문자의 개수)를 구할 수 있음.
```js
// 문자열의 length 프로퍼티 사용 예
let text1 = "apple";
let text2 = "사과";

document.write(text1.length + "<br />"); // 5
document.write(text2.length); // 2
```
- 큰 따옴표 안에 큰 따옴표를 사용하려면 이스케이프 문자를 사용.
```js
// 큰 따옴표 안에 큰 따옴표가 사용된 경우
let text1 = "내 이름은 "홍길동" 입니다."; // 오류 발생
document.write(text1 + "<br />");

let text2 = "내 이름은 \"홍길동\" 입니다."; // 이스케이프 문자 사용
document.write(text2);
```
- 이스케이프 문자

| 코드 | 결과 | 설명 |
| :------: | :------: | -------- |
| `\'` | `'` | 작은 따옴표 |
| `\"` | `"` | 큰 따옴표 |
| `\\` | `\` | 역슬래쉬 |
| `\n` | `줄바꿈` | 새로운 줄에서 시작 |
| `\t` | `탭` | 탭 키를 누른 효과 |

### 2.2.4 템플릿 문자열  
- 템플릿 문자열에서는 문자열 안에 직접 변수 값을 넣을 수 있음.
```js
// 템플릿 문자열 사용 예
let name = "홍길동";
let age = 30;

// 문자열 연결 연산자 (+)
let text1 = "이름 : " + name + ", 나이 : " + age;
// 템플릿 문자열
let text2 = `이름 : ${name}, 나이 : ${age}`;

document.write(text1 + "<br />");
document.write(text2);
```
### 2.2.5 불  
- 불(boolean) 데이터 형에는 true와 false 값만이 존재함.
```js
// 불 데이터 형 사용 예
let x = 5 > 3; // true
let y = 5 < 3; // false

document.write(x + "<br />");
document.write(y);
```
### 2.2.6 Undefined와 Null  
- 변수가 값을 가지고 있지 않으면 그 값은 undefined가 됨.
```js
// Undefined 데이터 형 사용 예
let x;

document.write(x + "<br />"); // undefined
document.write(typeof x); // undefined
```
- Null 데이터 형은 빈 문자열을 의미함.
```js
// Null 데이터 형 사용 예
let x = "";

document.write("값 : " + x + "<br />"); // 빈 문자열(null)이 출력됨
document.write("데이터 형 : " + typeof x); // string
```
### 2.2.7 객체  
- 자바스크립트에서 객체는 {키: 값, 키: 값, 키: 값, ...}의 형태로 사용됨.
```js
// 객체(object) 사용 예

// member 객체는 세 쌍의 "키: 값" 요소들로 구성됨
const member = { id: "kdhong", name: "홍길동", age: 20 };

document.write(member.id + "<br />"); // kdhong
document.write(member.name + "<br />"); // 홍길동
document.write(member.age); // 20
```
### 2.2.8 배열  
- 배열은 다수의 값을 저장할 수 있는 특별한 변수. 객체와 밀접한 관계를 가지고 있음.
- 원소에 접근하려면 인덱스를 이용해야 함. 인덱스는 0부터 시작함.
```js
// 배열(array) 사용 예
const car = ["현대", "기아", "벤츠", "BMW"];

// 인덱스를 이용해 요소에 접근
// 인덱스는 0부터 시작
document.write(car[0] + "<br />");
document.write(car[1] + "<br />");
document.write(car[2] + "<br />");
document.write(car[3]);
```
### 2.2.9 심볼  
- 심볼은 숫자, 문자열, 불과 같은 원시 데이터 형을 의미함.
- 심볼은 유일한 식별자로서 객체의 속상을 추가하는 데 사용됨.
```js
// 심볼(symbol) 사용 예
const member = { name: "홍길동", age: 20 };
let id = Symbol("id"); // id 심볼 생성
member[id] = "kdhong"; // 객체 member의 키 id에 문자열 "kdhong"을 저장

document.write(member[id] + "<br />"); // kdhong
document.write(typeof id + "<br />"); // symbol
document.write(id === Symbol("id")); // false → 심볼은 생성될 때마다 고유한 값을 가지기 때문
```

---
## 2.3 연산자  
### 2.3.1 산술 연산자  
- 산술 연산자의 종류

| 산술 연산자 | 설명 |
| :------: | :------: |
| `+` | 덧셈 |
| `-` | 뺄셈 |
| `*` | 곱셈 |
| `/` | 나눗셈 |
| `%` | 나머지 |
| `**` | 거듭제곱 |
| `++` | 1 증가 |
| `--` | 1 감소 |

- 일반 사칙연산과 마찬가지로, 자바스크립트에서도 곱셈(`*`)과 나눗셈(`/`)이 먼저 계산됨.
```js
// 사칙연산 사용 예
let x = 10;
let y = 20;
let z = x + (y * 5) / 2;

document.write(z);
```

- 나머지 연산자는 `x`를 `y`로 나눈 나머지 값을 반환함.
```js
// 나머지 연산자 사용 예
let a = 10;
let b = 20;
let c = a % 2; // 몫: 5, 나머지: 0
let d = b % 3; // 몫: 6, 나머지: 2
let e = 3 % a; // 몫: 0, 나머지: 3

document.write(c + "<br />");
document.write(d + "<br />");
document.write(e);
```

- 거듭제곱 연산자, 증가 연산자, 감소 연산자 사용 예시
```js
// 거듭제곱 연산자, 증가/감소 연산자 사용 예
let a = 3;
let b = 5;
let c = a ** 3; // 27
c++; // 28
c = c + 3; // 31
c--; // 30
c = a + b + c; // 38

document.write(c);
```
### 2.3.2 문자열 연결 연산자  
- 문자열 연결 연산자는 `+` 기호를 사용함.
```js
// 문자열 연결 연산자 사용 예
let name = "홍길동";
let age = 30;
let text1 = "이름 : " + name;
let text2 = "나이 : " + age;

document.write(text1 + "<br />");
document.write(text2);
```
### 2.3.3 할당 연산자  
- 할당 연산자는 데이터나 변수 값을 변수에 저장(메모리 공간에 할당)하는 역할을 수행함.

| 할당 연산자 | 예 | 동일한 표현 | 설명 |
| :------: | :------: | :------: | -------- |
| `=` | `x = 2` | - | 2를 변수 x에 할당 |
| `+=` | `x += 2` | x = x + 2 | 현재 x 값에 2를 더해서 얻은 값을 다시 x에 할당 |
| `-=` | `x -= 2` | x = x - 2 | 현재 x 값에 2를 빼서 얻은 값을 다시 x에 할당 |
| `*=` | `x *= 2` | x = x * 2 | 현재 x 값에 2를 곱해서 얻은 값을 다시 x에 할당 |
| `/=` | `x /= 2` | x = x / 2 | 현재 x 값에 2를 나누어서 얻은 값을 다시 x에 할당 |
| `%=` | `x %= 2` | x = x % 2 | 현재 x 값에 2를 나눈 나머지를 다시 x에 할당 |

```js
// 할당 연산자 사용 예
let a = 10;
let b = 20;
let c = 30;
let d = 40;
let e = 50;
let f = "안녕";

a += 3; // 13, a = a + 3
b -= 8; // 12, b = b - 8
c *= 2; // 60, c = c * 2
d /= 10; // 4, d = d / 10
e %= 6; // 2, e = e % 6
f += "하세요"; // "안녕하세요", f = f + "하세요"

document.write(a + "<br />");
document.write(b + "<br />");
document.write(c + "<br />");
document.write(d + "<br />");
document.write(e + "<br />");
document.write(f);
```
### 2.3.4 비교 연산자  
- 비교 연산자는 두 변수(데이터)의 값을 서로 비교하는 데 사용됨.

| 비교 연산자 | 의미 | 예 | 결과 | 설명 |
| :------: | :------: | :------: | :------: | -------- |
| `==` | 같다 | 3 == 3 | `true` | "3은 3과 같다", true |
|  | | "3" == 3 | `true` | "3"은 문자열, 3은 정수, 데이터 형이 달라도 true |
| `===` | 값과 데이터 형이 같다 | 3 === 3 | `true` | "3은 3과 값과 데이터 형이 같다", true |
|  | | "3" === 3 | `false` | 데이터 형이 다르므로 false |
| `!=` | 다르다 | 3 != 3 | `false` | "3은 3과 다르다", false |
|  | | "3" != 3 | `false` | "3"과 3의 데이터 형을 고려하지 않으므로 false |
| `!==` | 값과 데이터 형이 다르다 | 3 !== 3 | `false` | "3은 3과 다르다", false |
|  | | "3" !== 3 | `true` | "3"과 3은 데이터 타입이 다름, true |
| `>` | 크다 | 5 > 3 | `true` | "5는 3보다 크다", true |
| `<` | 작다 | 5 < 3 | `false` | "5는 3보다 작다", false |
| `>=` | 크거나 같다 | 5 >= 5 | `true` | "5는 3보다 크거나 같다", true |
| `<=` | 작거나 같다 | 5 <= 5 | `true` | "5는 5보다 작거나 같다", true |

```js
// 비교 연산자 사용 예
var a = 3;
var b = "3";
var c = 5;
var d = 3;

document.write((a == b) + "<br />"); // 3 == "3", true
document.write((a === b) + "<br />"); // 3 === "3", false
document.write((a != b) + "<br />"); // 3 != "3", false
document.write((a !== b) + "<br />"); // 3 !== "3", true
document.write((a > c) + "<br />"); // 3 > 5, false
document.write((a < c) + "<br />"); // 3 < 5, true
document.write((a >= c) + "<br />"); // 3 >= 5, false
document.write(a <= d); // 3 <= 3, true
```
### 2.3.5 논리 연산자  
- 논리 연산자에는 `&&`(AND), `||`(OR), `!`(NOT) 연산자가 있다.

| 논리 연산자 | 연산 | 설명 |
| :------: | :------: | -------- |
| `&&` | `AND` | 두 조건이 모두 `true`면 `true`를 반환 |
| <code>&#124;&#124;</code> | `OR` | 두 조건 중 하나만 `true`가 되어도 `true`를 반환 |
| `!` | `NOT` | 결과가 `true`면 `false`로, `false`면 `true`로 변경하여 반환 |

---

## 3장. 제어문
## 3.1 If 문  
### 3.1.1 if~ 구문  
- `if~` 구문은 조건식이 참이면 중괄호(`{}`) 안에 있는 내용을 실행함.
```js
// if~문 사용 예
let x = 10000;
let age = 70;

if (age >= 65) {
x = 0;
}

// age가 65 이상이므로 x는 0이 됨
document.write("입장료 : " + x + "원");
```
### 3.1.2 if~ else~ 구문  
- `if~ else~` 구문은 두 가지 조건 중 어느 곳에 해당되는지 판별할 때 사용됨.
```js
// if~ else~ 구문 사용 예
let num = 8;

if (num % 2 === 0) {
	document.write(num + "은(는) 짝수입니다.");
} else {
	document.write(num + "은(는) 홀수입니다.");
}
```
### 3.1.3 if~ else if~ else~ 구문  
- `if~ else if~ else` 구문은 조건이 세 가지 이상일 경우에 사용됨.
```js
// if~ else if~ else~ 구문 사용 예
let score = 85;

if (score >= 90) {
grade = "A";
} else if (score >= 80) {
grade = "B";
} else if (score >= 70) {
grade = "C";
} else if (score >= 60) {
grade = "D";
} else {
grade = "F";
}

document.write("점수 : " + score + ", 학점 : " + grade);
```

---
## 3.2 Switch 문  
- Switch 문은 if 문과 거의 같은 방식으로 동작함.
- switch 괄호 안에 있는 변수의 값에 따라 해당 case에 있는 문장이 실행됨.
- 그 외 나머지 경우에는 default에 있는 문장이 실행됨.
```js
// switch 문 사용 예
let num1 = 10;
let num2 = 20;
let operator = "/";

switch (operator) {
	case "+":
		result = num1 + num2;
		alert(num1 + "+" + num2 + "=" + result);
		break;
	
	case "-":
		result = num1 - num2;
		alert(num1 + "-" + num2 + "=" + result);
		break;
	
	case "*":
		result = num1 * num2;
		alert(num1 + "*" + num2 + "=" + result);
		break;
	
	case "/":
		result = num1 / num2;
		alert(num1 + "/" + num2 + "=" + result);
		break;
	
	default:
		alert("입력 오류!");
		break;
}
```

---
## 3.3 For 문  
### 3.3.1 For 문의 기본 구조  
- `for`의 조건식이 참인 동안 문장들을 반복 실행함.
```js
// for문의 사용 형식
for (① 초기값; ②조건식; ④ 증감식;) {
	③ 실행할 코드;
}
// for문의 진행 순서: ① → ② → ③ → ④ → ② → ③ → ④ ...
```

```js
// for 문 사용 예
let sum = 0;

for (let i = 1; i <= 10; i++) {
	sum += i;
}

document.write("합계 : " + sum);
```
### 3.3.2 For In 문  
- `for in` 문은 객체의 요소를 반복해서 읽어올 때 사용됨.
```js
// for in문의 사용 형식
for (변수 in 객체) {
	실행할 코드;
}
```

```js
const member = { id: "kdhong", name: "홍길동", age: 30 };

// 객체의 요소 수만큼 반복 루프가 진행됨.
// x는 member 객체의 키 이름을 가지므로, member 객체의 요소들은 member[x]로 접근 가능.
for (let x in member) {
	document.write(member[x] + "<br />");
}
```
### 3.3.3 For Of 문  
- `for of` 문은 배열이나 문자열 같이 반복 가능한 데이터 형에 있는 요소를 읽어올 때 사용됨.
```js
// for in문의 사용 형식
for (변수 of 배열) {
	실행할 코드;
}
```

```js
const scores = [88, 75, 95, 78, 90];

// 배열의 요소 수만큼 반복 루프가 진행됨.
// score는 scores의 원소를 값으로 가짐.
for (let score of scores) {
	document.write(score + "<br />");
}
```
### 3.3.4 이중 For 문  
- `이중 for` 문은 `for` 문 안에 `for` 문이 들어가 있는 형태임.
```js
// 이중 for 문의 사용 형식
for (초기값; 조건식; 증감식;) {
	for (초기값; 조건식; 증감식;) {
		...
	}
}
```

```js
// 이중 for문 사용 예
let result;

for (let i = 2; i <= 9; i++) {
	for (let j = 1; j <= 9; j++) {
		result = i * j;
		document.write(i + "x" + j + "=" + result + " ");
	}
	document.write("<br />");
}
```
---
## 3.4 While 문  
- `While` 문은 `For` 문과 마찬가지로 특정 코드를 반복해서 실행할 때 사용됨.
### 3.4.1 While 문의 기본 구조  
```js
① 초기식;

while (② 조건식) {
	③ 실행할 코드;
	④ 증감식;
}
// while문의 진행 순서: ① → ② → ③ → ④ → ② → ③ → ④ ...
```

```js
// while문 사용 예
let i = 1;

while (i <= 5) {
	document.write("안녕<br />");
	i++;
}
```
### 3.4.2 Do While 문  
- `Do While` 문은 `While` 문과 달리 조건식이 가장 마지막에 위치함.
- `Do While` 문에서는 `do` 다음에 있는 문장이 최소 한번은 실행됨.
- 첫 번재 실행 이후 `while`의 조건식이 참인 동안 루프 안에 있는 문장을 반복 실행함.
```js
do {
	실행할 코드;
} while (조건식;)
```

```js
// do while문 사용 예
let x = -10;

do {
	document.write("안녕!"); // 이 문장은 무조건 실행됨.
} while (x > 0); // 조건식을 만족하지 못하므로, "안녕!"이 브라우저에 한번만  출력됨.
```
---
## 3.5 Break/Continue 문  
### 3.5.1 Break 문  
- `Break` 문은 루프를 빠져나가고자 할 때 사용함.
```js
// break문 사용 예
for (let i = 1; i <= 10; i++) {
	if (i == 4) {
		break;
	}
	document.write(i + "<br />");
}
```
### 3.5.2 Continue 문  
 - `Continue` 문은 루프에서 실행되는 문장을 건너뛰고 싶을 때 사용함.
```js
// continue문 사용 예
for (let i = 1; i <= 10; i++) {
	if (i == 4) {
		continue;
	}
	
	// 1, 2, 3, 5, 6, 7, 8, 9, 10
	document.write(i + "<br />");
}
```

---


## 4장. 함수
## 4.1 함수란?  
- 프로그래밍 언어에서 함수란 `어떤 역할을 수행하는 것` 임.
- 함수를 사용하는 가장 큰 이유는 재사용이 가능하다는 것임.
### 4.1.1 함수 정의와 호출  
```js
// 함수 정의와 호출 예

// 함수 정의
function hello() {
	document.write("안녕하세요. <br />");
}

hello(); // 함수 호출
hello(); // 함수 호출
hello(); // 함수 호출
```
### 4.1.2 매개변수와 반환 값  
- 함수는 매개변수를 통해 변수나 데이터 값을 전달 받을 수 있음.
```js
// 함수의 매개변수와 반환 값 사용 예

// r은 매개변수(parameter)
function circleArea(r) {
	let result = r * r * 3.14;
	return result; // 함수 값의 반환
}

let area = circleArea(8); // 8을 인자로 전달하고, 반환 값을 area 변수에 저장
document.write("원의 넓이 : " + area);
```

---
## 4.2 익명 함수  
### 4.2.1 익명 함수란?  
- `익명 함수`란 말 그대로 함수 이름이 없는 함수를 의미함.
- 미리 함수 이름을 정하지 않고 필요에 의해 함수를 만들 때 사용함.
```js
// 익명 함수 사용 예

// 매개변수 두 개를 곱한 값을 반환하는 함수(익명 함수)를 변수 mul에 저장
const mul = function (a, b) {
	return a * b;
};

let result = mul(5, 8); // 호출을 할 때는 변수 mul이 함수 명으로 사용됨
document.write("결과 : " + result);
```
### 4.2.2 자기호출 익명 함수  
- `자기호출 익명 함수`는 함수 정의와 호출이 동시에 일어나, 바로 실행이 되는 함수임.
```js
// 익명 함수를 괄호로 감싼 형태로 사용됨
( function() {
	...
} ) ();
```

```js
// 자기호출 익명 함수 사용 예

// 익명 함수를 변수에 저장하거나 호출하지 않아도, 자기 자신을 호출하여 바로 실행됨
(function () {
	document.write("안녕하세요! <br />");
})();
```
### 4.2.3 화살표 함수  
- `화살표 함수`는 `익명 함수`를 축약해서 표현하는 형태임.
- `익명 함수`에서 사용되는 키워드 `function`, `return`, `{}` 대신 `=>` 기호를 사용함.
```js
// 화살표 함수 사용 예

const z = (x, y) => x + y;
document.write(z(10, 20)); // 화살표 함수도 일반 함수처럼 호출함
```
### 4.2.4 호이스팅  
- 자바스크립트는 기본적으로 변수나 함수 정의부를 프로그램 제일 앞으로 끌어올리는데, 이를 `호이스팅(hoisting)`이라고 함.
- `호이스팅`이란 우리 말로 "끌어올리기"라는 의미임.
- C, 자바 등의 프로그래밍 언어에서 아래와 같은 프로그램은 오류를 발생시키지만 (함수 호출 이전에 함수가 정의되어야 하므로), 자바스크립트에서는 `호이스팅` 기능으로 정상적으로 동작함.
```js
// 함수 호출이 함수 정의보다 먼저 일어난 경우의 예

let x;
x = mulFunc(10, 20); // 함수 호출
document.write(x);

// 함수 정의
function mulFunc(a, b) {
	return a * b;
}
```

- `익명 함수`의 경우에는 반드시 함수 호출 이전에 `익명 함수`를 선언하여 사용해야 함.
- `익명 함수`는 일반적인 함수와는 달리, 함수를 변수에 저장해서 사용하는 형태이기 때문.
```js
// 익명 함수에서는 호이스팅이 적용되지 않는 경우의 예

let x;
x = mulFunc(10, 20); // 함수 호출
document.write(x);

// 함수 정의
const mulFunc = function (a, b) {
	return a * b;
};
```

- `호이스팅` 기능은 변수 키워드(`var`, `let`, `const`)에 따라 달라지고, 데이터 형에 따라 동작하지 않기도 함.
- 따라서, 프로그래밍을 할 때는 함수 정의를 먼저 하는 것을 권고함.
- 변수, 객체, 클래스 등을 사용할 때에도 선언이나 정의를 먼저 한 다음 사용하는 것이 좋은 습관임.
---
## 4.3 함수의 매개변수  
### 4.3.1 매개변수의 기본 값  
- 자바스크립트 함수에서는 인수와 매개변수의 개수가 일치하지 않아도 오류가 발생하지 않음.
- 그러나, 함수 호출에서 전달되는 인수의 개수와 함수 정의에서 사용되는 매개변수의 개수가 다른 경우에는, 매개변수의 `기본 값(default value)`을 설정하여 사용해야 함.
```js
// 매개변수의 기본 값 사용 예
function addFunc(a, b = 5) {
	return a + b;
}

document.write(addFunc(10)); // 10 + 5 결과를 반환
```
### 4.3.2 나머지 매개변수  
- 자바스크립트에서는 함수 정의 시 매개변수의 개수를 미리 정하지 않고 무한대로 설정할 수 있음.
- 이 때 사용되는 매개변수를 `나머지 매개변수(rest parameter)`라고 하며, `...` 기호를 사용함.
```js
// 나머지 매개변수 사용 예

function sumScores(...scores) {
	let sum = 0;
	for (let score of scores) {
		sum += score;
	}
	
	return sum;
}

let sum = sumScores(70, 80, 90, 100);
document.write("합계 : " + sum);
```
### 4.3.3 Arguments 객체  
- 자바스크립트 함수는 `arguments` 객체를 내장하고 있으며, 이 객체는 함수 호출 시 전달되는 인수들을 배열 형태로 저장하고 있음.
- `arguments` 객체를 이용하여 함수 호출 시 여러 개의 인수를 함수에 전달할 수 있음.
```js
// arguments 객체 사용 예

function maxScores() {
	let max = -Infinity;
	for (let i = 0; i < arguments.length; i++) {
		if (arguments[i] > max) {
			max = arguments[i];
		}
	}

	return max;
}

let max_score = maxScores(87, 79, 93, 75, 68, 90, 88);
document.write("최고 점수 : " + max_score);
```

---
## 4.4 자바스크립트 스코프  
- `스코프(scope)`는 변수에 접근할 수 있는 유효 범위를 의미함.
### 4.4.1 전역 스코프  
- 프로그램 내 전체 영역에서 사용 가능함. `전역 스코프`에서 사용되는 변수를 `전역 변수`라고 함.
```js
// 전역 변수 사용 예

let x = 10;
function func() {
	document.write("함수 내부에서 사용 : " + x + "<br />");
}

func();
document.write("함수 외부에서 사용 : " + x);
```
### 4.4.2 함수 스코프  
- 함수 내에서만 사용 가능함. `함수 스코프`에서 사용되는 변수를 `지역 변수`라고 함.
```js
// 지역 변수 사용 예

function func() {
	let x = 10;
	document.write("함수 내부에서 사용 : " + x + "<br />");
}

func();
document.write("함수 외부에서 사용 : " + x); // 오류 발생
```
### 4.4.3 블록 스코프  
- 블록(`{}`) 내에서 사용 가능함. 특정 블록(`{}`) 내에서 `let`이나 `const`로 선언한 변수는 블록 외부에서 사용할 수 없음.
```js
// 블록 스코프에 사용된 변수

function func() {
	if (true) {
		let x = 10; // 변수는 if문 내, 블록 내부에서 선언됨
								// 이러한 변수는 블록 내부, 블록 스코프에서만 사용 가능함
	}
	document.write("함수 내부에서 사용 : " + x + "<br />"); // 오류 발생
}

func();
```
---
## 4.5 클로저  
- 전역 변수는 어디서나 값이 변경될 수 있기 때문에 보안에 취약하고 오류를 발생시킬 가능성을 가지고 있음.
- `클로저(closure)`는 전역 변수가 아닌 변수를, 전역 변수와 같은 방식으로 동작하지만 함부로 그 값을 변경할 수 없도록 변수를 "사유화"하는 방법을 제공함.
### 4.5.1 클로저란?  
- `클로저`는 함수가 자신이 생성될 때의 환경을 '기억'하고, 이 환경에 있는 변수에 접근할 수 있게 하는 자바스크립트의 특성임.
- 아래 예제에서, `increase()` 함수 호출 후 실행이 종료되어도 함수 내에서 사용된 지역 변수 `counter`가 내부의 익명 함수에서 사용되고 있기 때문에 그 값을 계속 유지하고 있음.
```html
<body>
<!-- 클로저를 이용한 카운터 -->

<button onclick="incCounter()">+</button>
<p id="show">0</p>
<script>
	// ① 자기호출 익명 함수 선언
	// increase라는 상수에 자기호출 익명 함수를 할당
	// 이 함수는 바로 실행되며, 내부에서 counter라는 변수를 0으로 초기화
	// 이 함수는 내부 함수를 반환함. 이 내부 함수는 counter 값을 1 증가시키고, 증가된 값을 반환함

	// ③ increase() 함수는 counter를 1 증가시키고 그 값을 반환함
	const increase = (function () {
		let counter = 0;

		return function () {
			counter += 1;
			return counter;
		};
	})();

	// ② 버튼을 클릭하면 incCounter()가 호출되면서, increase() 함수가 호출됨
	function incCounter() {
		document.getElementById("show").innerHTML = increase();
	}
</script>
</body>
```

---
## 4.6 예외 처리  
### 4.6.1 try~ catch 문  
- `try~ chath` 문은 오류가 있음직한 코드 블록에 대해 테스트를 시도하며, 오류를 처리하는 데 사용됨.
- `try` 블록에서 오류가 발생하면 `catch` 블록 내부의 코드를 실행함.
```js
// try~ catch 문 사용 예

try {
	// 테스트할 코드
	alerttttt("안녕하세요."); // 오류 발생
	document.write("test!");
} catch (e) {
	// 오류 처리 코드
	document.write(e.message);
}
```
### 4.6.2 try~ catch~ finally 문  
- `try~ catch~ finally` 문에서 `finally`는 `try~` 블록의 결과와 상관없이 무조건 실행됨.
```js
// try~ catch~ finally 문 사용 예

function simpleTryCatchExample() {
	try {
		// 시도할 코드
		console.log("try 블록 내부의 코드 실행 중...");

		// 예외를 강제로 발생시킴
		throw new Error("예제 예외 발생!");

		// 예외가 발생하면 이 부분은 실행되지 않음
		console.log("예외 발생 후 이 코드는 실행되지 않음.");
	} catch (error) {
		// 예외 처리
		console.log("catch 블록: 예외가 포착됨 -", error.message);
	} finally {
		// 항상 실행되는 코드
		console.log("finally 블록: 이 코드는 항상 실행됩니다.");
	}
}

// 함수 호출
simpleTryCatchExample();
```

---
