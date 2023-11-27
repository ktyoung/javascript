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

## 5장. 객체
## 5.1 객체 생성  
- 객체는 `프로퍼티(property)`와 `메서드(method)`의 집합임.
- 객체의 `프로퍼티`는 `변수`와 같은 개념이고, `메서드`는 `함수`와 거의 동일한 것임.
- 즉, 특정 객체에 소속된 변수와 함수를 그 객체의 `프로퍼티`와 `메서드`라 부름.
- 숫자(Number), 문자열(String), 함수(Function), 배열(Array), 날짜(Date) 등 모든 것이 객체임.
```js
// 객체의 생성과 프로퍼티 읽기

// 객체 member 생성 (키: 값 형태)
const member = {
	id: "kdhong",
	name: "홍길동",
	age: 30,
};

// . 연산자로 member의 프로퍼티 읽기
let text = member.id + " " + member.name + " " + member.age;
document.write(text);
```

---
## 5.2 프로퍼티  
### 5.2.1 For In 문으로 프로퍼티 읽기  
- `For In` 문으로 객체에 존재하는 프로퍼티의 키와 값을 쉽게 반복적으로 읽어올 수 있음.
```js
// For In 문으로 객체의 프로퍼티 읽기

const member = {
	id: "kdhong",
	name: "홍길동",
	age: 30,
};

let text = "";

// x는 프로퍼티의 키 이름(id, name, age)을 가짐
for (x in member) {
	text += member[x] + "<br />";
}
document.write(text);
```
### 5.2.2 프로퍼티 추가하기  
```js
// 객체에 프로퍼티 추가하기

const member = {
	id: "kdhong",
	name: "홍길동",
	age: 30,
};

// member 객체에 email 프로퍼티 추가
member.email = "kdhong@korea.com";

let text = "";

for (x in member) {
	text += "키 : " + x + ", 값 : " + member[x] + "<br />";
}
document.write(text);
```
### 5.2.3 프로퍼티 삭제하기  
- 특정 프로퍼티를 삭제하는 데에는 `delete` 키워드를 이용함.
```js
// 객체에 프로퍼티 삭제하기

const member = {
	id: "kdhong",
	name: "홍길동",
	age: 30,
};

// member 객체의 id 프로퍼티 삭제
delete member.id;

let text = "";

for (x in member) {
	text += "키 : " + x + ", 값 : " + member[x] + "<br />";
}
document.write(text);
```
### 5.2.4 중첩 객체  
- `중첩된 객체(nested object)`는 객체 안에 객체를 포함함.
```js
// 중첩된 객체의 예

const obj1 = {
	id: "kdhong",
	name: "홍길동",
	
	// hobby 프로퍼티는 값으로 객체를 가진다
	hobby: {
		hobby1: "게임",
		hobby2: "탁구",
		hobby3: "기타",
	},
};

let text = "";

// 중첩 객체에 접근하기
text += obj1.hobby.hobby1 + "<br />";
text += obj1.hobby.hobby2 + "<br />";
text += obj1.hobby.hobby3;

document.write(text);
```

---
## 5.3 메서드  
### 5.3.1 메서드란?  
- `메서드` 란 객체에 소속된 함수를 말함.
- `프로퍼티`는 객체의 상태를 의미하고, `메서드`는 객체의 동작을 정의한다고 할 수 있음.
```js
// 객체의 메서드 사용 예

const cat = {
	name: "로키",
	species: "랙돌",
	color: "흰색",
	age: 3,

	// 메서드 intro()를 정의함
	// this는 현재 이 메서드가 소속된 객체(cat)을 가리킴
	intro: function () {
		return "나의 이름은 " + this.name + "입니다.";
	},
};

// cat 객체의 intro() 메서드 호출
document.write(cat.intro());
```
### 5.3.2 메서드 추가하기  
```js
// 객체에 메서드 추가하기

const cat = {
	name: "로키",
	species: "랙돌",
	color: "흰색",
	age: 3,
};

// cat 객체에 getAge() 메서드 추가
cat.getAge = function () {
	return "나이는 " + this.age + "살 입니다.";
};

// cat 객체의 getAge() 메서드 호출
document.write(cat.getAge());
```
### 5.3.3 내장 메서드  
- 자바스크립트에는 자체적으로 만들어둔 `내장 객체(built-in object)`가 있고, 이 `내장 객체`들은 `내장 메서드(built-in method)`를 제공함.
- 많이 사용되는 `내장 객체`에는 `Number` 객체, `String` 객체, `Array` 객체, `Date` 객체, `Math` 객체 등이 있음.
```js
// Number 객체의 toFiexd() 메서드 사용 예
// toFixed() 메서드는 소수점 이하 부분을 반올림한 값을 반환한다

let x = 12.46245;

// toFixed(1)은 소수점 둘째 자리에서 반올림을 한, 소수점 첫째 자리까지의 값을 구한다
document.write(x.toFixed(1) + "<br />");

// toFixed(3)은 소수점 넷째 자리에서 반올림을 한, 소수점 셋째 자리까지의 값을 구한다
document.write(x.toFixed(3));
```

```js
// String 객체의 toUpperCase() 메서드 사용 예
// toUpperCase() 메서드는 영문 소문자를 영문 대문자로 변경할 때 사용한다

let str = "hello, world!";

document.write(str.toUpperCase());
```
---
## 5.4 생성자 함수  
### 5.4.1 생성자 함수란?  
- `생성자 함수(constructor function)`는 일반 함수와 기능적인 차이는 없음.
- 그러나, 일반 함수와는 달리 `생성자 함수`는 `new` 연산자와 함께 객체를 생성하기 위해 사용됨.
- `생성자 함수`를 정의할 때에는 일반 함수와 구분하기 위해 첫 글자를 영문 대문자로 시작함.
```js
// 생성자 함수의 객체 생성 예

// 생성자 함수 Member()는 세 개의 매개변수를 가지고 있으며,
// 이들은 new 연산자를 이용하여 생성자 함수 호출 시 인수를 전달받는 데 사용된다
function Member(id, name, age) {
	this.id = id;
	this.name = name;
	this.age = age;
}

// new 연산자를 이용해 생성자 함수 Member()를 호출하여 mem1, mem2, mem3 객체 생성
const mem1 = new Member("kdhong", "홍길동", 25);
const mem2 = new Member("kdkang", "강길동", 39);
const mem3 = new Member("kdchoi", "최길동", 43);

let text = "";

// 객체의 프로퍼티에 접근
text += mem1.name + "<br />";
text += mem2.name + "<br />";
text += mem3.name;

document.write(text);
```
### 5.4.2 생성자 함수의 메서드  
```js
// 생성자 함수에서 메서드 사용 예

function Member(id, name, age) {
	this.id = id;
	this.name = name;
	this.age = age;
	
	// 생성자 함수 Member()의 getName() 메서드 정의
	this.getName = function () {
		// this.name은 생성자 함수로 생성되는 객체 자신의 프로퍼티 name을 의미한다
		return "나의 이름은 " + this.name + "입니다.";
	};
}

const mem1 = new Member("kdhong", "홍길동", 25);

let text = "";
text += mem1.getName();

document.write(text);
```

---
## 5.5 프로토타입  
- C++, 자바와 같은 클래스 기반의 객체지향 프로그래밍 언어와 달리, 자바스크립트는 `프로토타입(prototype)`을 기반으로 객체지향 프로그래밍을 할 수 있음.
- 자바스크립트에서는 클래스 없이도 `프로토타입`을 이용하여 객체를 생성할 수 있음.
- 모든 자바스크립트 객체는 `프로토타입`으로부터 프로퍼티와 메서드를 상속 받음.
- `프로토타입`을 이용하면 생성자 함수에 의해 생성된 모든 객체들에 새로운 프로퍼티와 메서드를 추가할 수 있음.
```js
// 생성자 함수 생성 후 메서드 추가 (잘못된 방법)

function Member(id, name, age) {
	this.id = id;
	this.name = name;
	this.age = age;
}

// 이미 생성된 생성자 함수 Member()에는 새로운 프로퍼티를 추가할 수 없다
Member.company = "현대";

const mem1 = new Member("kdhong", "홍길동", 25);

let text = "";
text += mem1.name + "<br />";
text += mem1.company; // undefined

document.write(text);
```

- `프로토타입`을 이용하여 기존의 생성자 함수에 프로퍼티와 메서드를 추가하는 예
- `Member` 객체는 `Member.prototype`으로부터 프로퍼티와 메스드를 상속 받음.
```js
// 프로토타입을 이용한 프로퍼티와 메서드 추가

function Member(id, name, age) {
	this.id = id;
	this.name = name;
	this.age = age;
}

// 생성자 함수 Member()에 "현대"를 값으로 하는 새로운 프로퍼티 company 추가
Member.prototype.company = "현대";
// 생성자 함수 Member()에 새로운 메서드 getId() 추가
Member.prototype.getId = function () {
	return "아이디는 " + this.id + "입니다.";
};

const mem1 = new Member("kdhong", "홍길동", 25);

let text = "";
text += mem1.company + "<br />";
text += mem1.getId();

document.write(text);
```

---
## 5.6 클래스  
- `클래스(class)`는 객체를 생성하기 위한 틀(템플릿)임.
- 자바스크립트에서 `클래스`는 함수와 유사한 구조를 가지며 `클래스`는 특별한 함수라고 볼 수 있음.
### 5.6.1 클래스 기본 구조  
```js
// 자바스크립트 클래스 사용 예

class Member {
	// 생성자 constructor()는 new 연산자에 의해 자동으로 호출되며,
	// 객체의 기본 상태를 설정하는 데 사용된다
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}

	// 클래스 메서드 getAge()는 나이를 반환한다
	getAge() {
		return "나이는 " + this.age + "살 입니다.";
	}
}

// new 연산자를 이용하여 mem1 객체를 생성한다
// 이 때, 생성자 constructor()가 자동 호출되어 mem1의 name과 age 프로퍼티는 "홍길동", 30으로 설정된다
const mem1 = new Member("홍길동", 30);

let text = "";

// mem1 객체에 접근할 때는 일반 객체에서와 같이 . 연산자가 사용된다
text += mem1.name + "<br />";
text += mem1.getAge();

document.write(text);
```

### 5.6.2 클래스 상속  
- `클래스 상속`은 다른 클래스에 있는 프로퍼티와 메서드를 상속받아 사용하는 것을 말함.
- 부모 클래스가 가지고 있는 자원과 기능을 확장하여 사용할 수 있음.
- 클래스 상속에는 `extends` 키워드를 사용함.
```js
// 클래스 상속

// 클래스 Member 정의
class Member {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
	getName() {
		return "나의 이름은 " + this.name + "입니다.";
	}
}

// 클래스 Student는 클래스 Member를 상속 받는다
// 클래스 Student에서도 클래스 Member의 프로퍼티와 메서드를 사용할 수 있게 된다
class Student extends Member {
	constructor(name, age, school) {
		super(name, age); // 부모 클래스(Member)의 생성자(constructor) 호출
		this.school = school;
	}
	intro() {
		return this.getName() + " " + this.school + " 학생입니다.";
	}
}

// new 연산자를 이용하여 클래스 Student로부터 객체 stud1 생성
// 객체 stud1에서는 클래스 Student와 클래스 Member의 자원을 사용할 수 있다
const stud1 = new Student("홍길동", 20, "길동대학교");

// 클래스 Student의 intro() 메서드 호출
document.write(stud1.intro());
```
### 5.6.3 정적 메서드  
- `정적 메서드(static method)`는 클래스 자체에서 정의되며, 객체를 통해 호출하는 것이 아니라 클래스에서 호출하여 사용하는 메서드임.
- `정적 메서드`는 클래스의 별도 인스턴스를 만들지 않고도, 클래스 이름만으로 바로 사용할 수 있는 간편한 도구 같은 기능을 제공
- 예를 들어, `Math.random()` 같은 경우가 이에 해당하는데, `Math`는 클래스이고 `random`은 그 안의 정적 메서드임.
```js
// 클래스의 정적 메서드

class Member {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
	getName() {
		return "나의 이름은 " + this.name + "입니다.";
	}

	// 클래스에서 정적 메서드를 사용할 때에는 static 키워드를 붙인다
	// 정적 메서드는 객체에 소속된 것이 아닌 클래스 자체에 속하는 메서드이다
	static getCountry() {
		return "한국인입니다.";
	}
}

const mem1 = new Member("홍길동", 30);

let text = "";
text += mem1.getName() + "<br />";
// 정적 메서드를 호출할 때는 클래스 이름 옆에 . 연산자를 사용한다
text += Member.getCountry() + "<br />";
// text += mem1.getCountry() + "<br />"; // 오류 발생

document.write(text);
```

---

## 6장. 숫자
## 6.1 자바스크립트의 숫자  
- 자바스크립트에서 모든 숫자는 64비트의 부동 소수점으로 저장됨.
- 자바스크립트에서 컴퓨터 메모리에 부동 소수점으로 저장된 숫자는 정수와 소수점이 있는 숫자 두 가지 형태로 사용됨.
- 매우 큰 수와 매우 작은 수를 표현할 때는 지수가 사용됨.
### 6.1.1 숫자와 문자열 연산  
- `3`과 `"3"`은 전혀 다른 데이터인데, `3`은 숫자이고 `"3"`은 문자열이기 때문임.
- 숫자 `3`이 메모리에 저장될 때에는 2진수로 변환되어 저장되며, 문자열 `"3"`은 UTF-16 형태로 저장됨.
```js
// 숫자와 문자열 간의 덧셈과 곱셈 연산

let a = 3;
let b = 5;
let c = "3";
let d = "5";

// 숫자와 숫자의 덧셈
document.write(a + b + "<br />"); // 3 + 5 = 8

// 문자열과 문자열의 덧셈 → 연결 연산자
document.write(c + d + "<br />"); // "3" + "5" = "35"

// 숫자와 문자열의 덧셈 → 어느 한 쪽이 문자열인 경우, 나머지 한 쪽이 문자열로 자동 변환
document.write(a + d + "<br />"); // 3 + "5" = "35"

// 문자열과 문자열의 곱셈 → 문자열이 숫자로 변환
document.write(c * d); // 3 * 5 = 15
```
### 6.1.2 NaN 데이터 형  
- `NaN`은 'Not a Number'의 약어이며, 숫자와 문자열 간에 사칙 연산(덧셈 제외)을 하면 서로 연산을 할 수 없기 때문에 `NaN`의 결과가 나오게 됨.
```js
// 숫자와 문자열 간의 나눗셈 연산

let a = 10;
let b = "lion";
let c = "2";

// 숫자와 문자열의 나눗셈
document.write(a / b + "<br />"); // NaN
document.write(isNaN(a / b) + "<br />"); // true

// 문자열이 숫자로 변환
document.write(a / c + "<br />"); // 10 / 2 = 5
document.write(isNaN(a / c)); // false
```
### 6.1.3 진수 변환  
- Number 객체의 `toString()` 메서드를 이용하면 숫자를 다른 진수로 변환할 수 있음.
```js
// 진수 변환 예

let x = 91;

document.write(x.toString(16) + "<br />"); // 5b (16진수로 변환)
document.write(x.toString(10) + "<br />"); // 91 (10진수로 변환)
document.write(x.toString(2)); // 1011011 (2진수로 변환)
```
### 6.1.4 무한대  
- 자바스크립트에서는 무한대 수를 표현하기 위해 `Infinity`와 `-Infinity` 프로퍼티를 사용함.
- 이는 각각 `양의 무한대`와 `음의 무한대`를 나타내며, 표현할 수 있는 수보다 더 큰 수를 계산해야 하는 경우 `Infinity`를 반환함.
```js
// 거듭 제곱 계속 연산으로 발생한 무한대

let x = 10;

while (x != Infinity) {
	x = Math.pow(x, 2);
	document.write(x + "<br />");
}
```

---
## 6.2 Number 메서드  
### 6.2.1 toString() 메서드  
- `toString()` 메서드는 진수를 변환할 때 사용되지만, 매개변수를 사용하지 않고 그대로 사용하면 숫자를 문자열로 변환할 수 있음.
```js
// toString() 메서드로 숫자를 문자열로 변환

let x = 10;

document.write(x + "<br />"); // 10
document.write(x.toString() + "<br />"); // "10"
document.write(typeof x + "<br />"); // number
document.write(typeof x.toString()); // string
```
### 6.2.2 toFixed() 메서드  
- `toFixed()` 메서드는 소수점 자릿수를 구하는 데 사용됨.
- 예를 들어 `toFixed(2)`는 소수점 둘째 자리까지 구하며, 셋째 자리에서 반올림이 일어남.
```js
// toFixed() 메서드로 부동 소수점 자릿수 구하기

let x = 20.3648;

document.write(x.toFixed(0) + "<br />"); // 20, 정수 부분을 구하기
document.write(x.toFixed(1) + "<br />"); // 20.4, 첫째 자리까지 구하기
document.write(x.toFixed(2) + "<br />"); // 20.36, 둘째 자리까지 구하기
document.write(x.toFixed(3)); // 20.365, 셋째 자리까지 구하기
```
### 6.2.3 toPrecision() 메서드  
- `toPrecision()` 메서드는 `toFixed()` 메서드와 마찬가지로 부동 소수점 자릿수를 구하는 데 사용됨.
- `toPrecision()` 메서드는 표시되는 전체 숫자의 개수를 이용하여 자릿수를 구함.
```js
// toPrecision() 메서드로 부동 소수점 자릿수 구하기

let x = 123.348765;

document.write(x.toPrecision() + "<br />"); // 123.348765
document.write(x.toPrecision(3) + "<br />"); // 123
document.write(x.toPrecision(4) + "<br />"); // 123.3
document.write(x.toPrecision(5) + "<br />"); // 123.35
document.write(x.toPrecision(6)); // 123.349
```
### 6.2.4 toExponential() 메서드  
- `toExponential()` 메서드는 지수 표기로 반올림된 문자열을 반환함.
- 매개변수는 표현되는 소수점 자릿수를 의미하며, 소수점 이하 숫자를 몇 자리까지 표시할 지 설정할 수 있음.
```js
// toExponential() 메서드 사용 예

let x = 1235.36764508;

document.write(x.toExponential() + "<br />"); // 1.23536764508e+3
document.write(x.toExponential(2) + "<br />"); // 1.24e+3
document.write(x.toExponential(3) + "<br />"); // 1.235e+3
document.write(x.toExponential(6)); // 1.235368e+3
```

---
## 6.3 변수의 숫자 변환  
### 6.3.1 Number() 메서드  
- `Number()` 메서드는 변수 또는 데이터 값을 숫자로 변환함.
```js
// 전역 메서드 Number()로 숫자 변환하기

let a = "10";
let b = "10.123";
let c = "   10";
let d = "apple";

document.write(Number(a) + "<br />"); // 10
document.write(Number(b) + "<br />"); // 10.123
document.write(Number(c) + "<br />"); // 10
document.write(Number(d)); // NaN
```
### 6.3.2 parseInt() 메서드  
- `parseInt()` 메서드는 변수나 데이터를 정수로 변환하는 데 사용됨.
```js
// 전역 메서드 parseInt()로 정수 변환

let a = "10";
let b = "10.123";
let c = "   10";
let d = "apple";

document.write(parseInt(a) + "<br />"); // 10
document.write(parseInt(b) + "<br />"); // 10
document.write(parseInt(c) + "<br />"); // 10
document.write(parseInt(d)); // NaN
```
### 6.3.3 parseFloat() 메서드  
- `parseFloat()` 메서드는 문자열을 부동 소수점 숫자로 변환하는 데 사용됨.
```js
// 전역 메서드 parseFloat()로 부동 소수점 숫자 변환

let a = "10";
let b = "10.123";
let c = "   10";
let d = "apple";

document.write(parseFloat(a) + "<br />"); // 10
document.write(parseFloat(b) + "<br />"); // 10.123
document.write(parseFloat(c) + "<br />"); // 10
document.write(parseFloat(d)); // NaN
```

---
## 6.4 Number 프로퍼티  
### 6.4.1 MAX_VALUE, MIN_VALUE 프로퍼티  
- `MAX_VALUE`와 `MIN_VALUE` 프로퍼티는 자바스크립트로 표현 가능한 가장 큰 수와 작은 수를 나타냄.
```js
// MAX_VALUE와 MIN_VALUE 값 확인하기

let x = Number.MAX_VALUE;
let y = Number.MIN_VALUE;

document.write(x + "<br />"); // 1.7976931348623157e+308
document.write(y); // 5e-324
```
### 6.4.2 MAX_SAFE_INTEGER, MIN_SAFE_INTEGER 프로퍼티  
- `MAX_SAFE_INTEGER`와 `MIN_SAFE_INTEGER` 프로퍼티는 안전하게 표현 가능한 최대 정수와 최소 정수를 의미함.
- `MAX_SAFE_INTEGER`는 2<sup>53</sup> - 1 값을 가지며, `MIN_SAFE_INTEGER`는 -(2<sup>53</sup> - 1) 값을 가짐.
```js
// MAX_VALUE와 MIN_VALUE 값 확인하기

let x = Number.MAX_SAFE_INTEGER;
let y = Number.MIN_SAFE_INTEGER;

document.write(x + "<br />"); // 9007199254740991
document.write(y); // -9007199254740991
```

---

## 7장. 문자열
## 7.1 문자열이란?  
### 7.1.1 특정 문자에 접근하기  
- 문자열에서 인덱스를 이용하여 문자를 읽을 수 있음.
- 인덱스는 0부터 시작함.
```js
// 문자열에서 특정 문자 읽기

let str1 = "안녕하세요";

document.write(str1[0] + "<br />"); // 안
document.write(str1[2] + "<br />"); // 하
document.write(str1[4]); // 요
```
### 7.1.2 문자 반복 처리하기  
- `For` 문을 이용하여 문자열의 각 문자를 반복해서 읽어올 수 있음.
```js
// 문자열의 각 문자 For 문으로 읽어오기

let str1 = "안녕하세요";

for (let i = 0; i < str1.length; i++) {
	document.write(str1[i] + "<br />");
}
```

---
## 7.2 문자열 추출  
### 7.2.1 slice() 메서드  
- `slice()` 메서드는 문자 시작 위치와 끝 위치를 기준으로 문자열을 추출함.
- `slice(start, end)` 인덱스 `start`부터 인덱스 `end - 1`까지의 문자열을 추출함.
```js
// slice() 메서드로 문자열 추출하기

let str1 = "가는 말이 고와야 오는 말이 곱다.";

document.write(str1.slice(3, 8) + "<br />"); // 말이 고와 → 인덱스 3부터 7까지 추출
document.write(str1.slice(3) + "<br />"); // 말이 고와야 오는 말이 곱다. → 인덱스 3부터 끝까지 추출
document.write(str1.slice(-5)); // 이 곱다. → 끝에서 5개를 추출
```
### 7.2.2 substr() 메서드  
- `substr()` 메서드는 시작 위치와 추출하는 개수를 지정함.
- `substr(start, length)` 인덱스 `start`부터 `length` 개수의 문자열을 추출함.
```js
// substr() 메서드로 문자열 추출하기

let str1 = "고래 싸움에 새우 등 터진다.";

document.write(str1.substr(5, 3) + "<br />"); // 에 새 → 인덱스 5부터 3개의 문자열 추출
document.write(str1.substr(7) + "<br />"); // 새우 등 터진다. → 인덱스 7부터 끝까지 추출
document.write(str1.substr(-3)); // 진다. → 끝에서 3개를 추출
```

---
## 7.3 문자열 변환  
### 7.3.1 toUpperCase() 메서드  
- `toUpperCase()` 메서드는 영문 소문자를 대문자로 변경한 문자열을 반환함.
```js
// toUpperCase() 메서드로 영문 대문자 변경하기

let str1 = "Javascript";

document.write(str1.toUpperCase()); // JAVASCRIPT
document.write(str1); // Javascript → 기존 값은 변경되지 않음
```
### 7.3.2 toLowerCase() 메서드  
- `toLowerCase()` 메서드는 영문 대문자를 소문자로 변경한 문자열을 반환함.
```js
// toLowerCase() 메서드로 영문 소문자 변경하기

let str1 = "I Am A Student.";

document.write(str1.toLowerCase()); // i am a student.
document.write(str1); // I Am A Student. → 기존 값은 변경되지 않음
```
### 7.3.3 replace() 메서드  
- `replace()` 메서드는 문자열에서 특정 문자열을 찾아 다른 문자열로 치환함.
- 첫 번째로 매치되는 문자열만 변경되고, 그 다음 매치되는 문자열은 변경되지 않음.
```js
// replace() 메서드로 문자열 치환하기

let str1 = "My friend or a friend of mine?";

document.write(str1.replace("friend", "student")); // My student or a friend of mine? → 첫 번째 문자열만 변경됨
document.write(str1); // My friend or a friend of mine? → 기존 값은 변경되지 않음
```
### 7.3.4 replaceAll() 메서드  
- `replaceAll()` 메서드는 문자열에서 특정 문자열을 찾아 매치된 모든 문자열을 다른 문자열로 치환함.
```js
// replaceAll() 메서드로 문자열 치환하기

let str1 = "Apple apple apple apple";

document.write(str1.replaceAll("apple", "orange")); // Apple orange orange orange
document.write(str1); // Apple apple apple apple → 기존 값은 변경되지 않음
```
### 7.3.5 concat() 메서드  
- `concat()` 메서드는 두 개 이상의 문자열을 서로 병합하는 데 사용됨.
- 기존의 문자열을 변경하지 않고 문자열들을 연결한 새로운 문자열을 반환함.
```js
// concat() 메서드로 문자열 연결하기

let str1 = "토끼";
let str2 = "거북이";

document.write(str1.concat(str2) + "<br />"); // 토끼거북이
document.write(str1.concat("와 " + str2) + "<br />"); // 토끼와 거북이
document.write(str1); // 토끼 → 기존 값은 변경되지 않음
```
### 7.3.6 split() 메서드  
- `split()` 메서드는 특정 문자열을 기준으로 문자열을 분리하여 배열 형태로 반환함.
```js
// split() 메서드로 휴대폰 번호 분리하기

let phone = "010-1234-5678";

document.write(phone.split("-")); // 010,1234,5678
```

```js
// split() 메서드로 호출 후 For 문 이용하기

let str1 = "We are the world";
let arr = str1.split(" ");

for (let i = 0; i < arr.length; i++) {
	document.write(arr[i] + "<br />");
}
```

---
## 7.4 공백 삭제와 문자열 패딩  
### 7.4.1 trim() 메서드  
- `trim()` 메서드는 문자열 양 끝에 있는 공백을 삭제하는 데 사용됨.
```js
// trim() 메서드로 문자열 양쪽 끝 공백 삭제하기

let str1 = "     javascript string       ";

document.write(str1.trim() + "<br />"); // javascript string
document.write(str1.length + "<br />"); // 29
document.write(str1.trim().length); // 17
```
### 7.4.2 trimStart() 메서드  
- `trimStart()` 메서드는 문자열 앞쪽에 있는 공백만 삭제함.
```js
// trimStart() 메서드로 문자열 앞 공백 삭제하기

let str1 = "     javascript string       ";

document.write(str1.trimStart() + "<br />"); // javascript string
document.write(str1.length + "<br />"); // 29
document.write(str1.trimStart().length); // 24
```
### 7.4.3 trimEnd() 메서드  
- `trimEnd()` 메서드는 문자열 뒤쪽에 있는 공백만 삭제함.
```js
// trimEnd() 메서드로 문자열 뒤 공백 삭제하기

let str1 = "     javascript string       ";

document.write(str1.trimEnd() + "<br />"); // javascript string
document.write(str1.length + "<br />"); // 29
document.write(str1.trimEnd().length); // 22
```
### 7.4.4 padStart() 메서드  
- `padStart()` 메서드는 문자열 앞 쪽에 특정 문자열을 채우는 데 사용됨.
- `padStart(targetLength, padString)` 전체 자릿수가 `targetLength`가 되도록 문자열 앞에 `padString`을 채움.
```js
// padStart() 메서드로 앞 쪽 문자열 채우기

let str1 = "268";

document.write(str1 + "<br />"); // 268
document.write(str1.padStart(5, "0") + "<br />"); // 00268
document.write(str1.padStart(6, "#")); // ###268
```
### 7.4.5 padEnd() 메서드  
- `padEnd()` 메서드는 문자열 앞 쪽에 특정 문자열을 채우는 데 사용됨.
- `padEnd(targetLength, padString)` 전체 자릿수가 `targetLength`가 되도록 문자열 뒤에 `padString`을 채움.
```js
// padEnd() 메서드로 뒤에 문자열 채우기

let str1 = "35";

document.write(str1 + "<br />"); // 35
document.write(str1.padEnd(5, "0") + "<br />"); // 35000
document.write(str1.padEnd(6, "x")); // 35xxxx
```

---
## 7.5 문자열 검색  
### 7.5.1 indexOf() 메서드  
- `indexOf()` 메서드는 문자열에서 특정 문자열이 처음 발생하는 위치를 반환하고, 특정 문자열이 존재하지 않으면 -1을 반환함.
- `indexOf(searchString, position)` 검색을 시작하는 위치 `position`부터 검색을 시작하여 `searchString`이 처음 발생하는 위치를 반환함.

```js
// indexOf() 메서드 사용 예

let str1 = "하늘의 별 따기. 하늘이 무너져도 솟아날 구멍이 있다.";

document.write(str1.indexOf("하늘") + "<br />"); // 0
document.write(str1.indexOf("하늘", 4) + "<br />"); // 10
document.write(str1.indexOf("땅")); // -1
```
### 7.5.2 lastIndexOf() 메서드  
- `lastIndexOf()` 메서드는 문자열에서 특정 문자열이 마지막으로 발생하는 위치를 반환하고, 특정 문자열이 존재하지 않으면 -1을 반환함.
```js
// lastIndexOf() 메서드 사용 예

let str1 = "공든 탑이 무너지랴. 공자 앞에서 문자 쓴다.";

document.write(str1.lastIndexOf("공") + "<br />"); // 12
document.write(str1.lastIndexOf("공", 0) + "<br />"); // 0
document.write(str1.indexOf("곰")); // -1
```
### 7.5.3 search() 메서드  
- `search()` 메서드는 `indexOf()` 메서드와 같이 특정 문자열이 처음 발생하는 위치를 반환함.
- `search()` 메서드는 문자열 검색 뿐만 아니라, 정규 표현식도 검색에 이용 가능함.
```js
// search() 메서드 사용 예

let str1 = "No pain no gain. No pain no gain.";

document.write(str1.search("pain") + "<br />"); // 3 → pain이 처음 발생하는 위치
document.write(str1.search("No") + "<br />"); // 0 → No가 처음 발생하는 위치
document.write(str1.search("no") + "<br />"); // 8 → no가 처음 발생하는 위치
document.write(str1.search(/no/i) + "<br />"); // 0 → no(대소문자 구분 X)가 처음 발생하는 위치
document.write(str1.search("yes")); // -1 → 존재하지 않는 문자열이므로 -1을 반환
```
### 7.5.4 match() 메서드  
- `match()` 메서드는 문자열 내에 정규 표현식으로 표현된 특정 문자열이 존재하는지 검사하여 그 결과를 배열 형태로 반환함.
```js
// match() 메서드 사용 예

let str1 = "I am A student. I am from Korea.";

// gi 옵션은 대소문자를 구분하지 않는 모든 매치를 의미함
document.write(str1.match(/a/gi)); // a,A,a,a
```
### 7.5.5 includes() 메서드  
- `includes()` 메서드는 문자열 내에 특정 문자열이 존재하는지 검색하여 그 문자열이 존재하면 `true`, 그렇지 않으면 `false`를 반환함.
```js
 // includes() 메서드 사용 예

let str1 = "강물도 오래 흐르면 바위에 구멍을 뚫는다.";

document.write(str1.includes("바위") + "<br />"); // true
document.write(str1.includes("사과")); // false
```

---

