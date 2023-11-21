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
```html
<script>
	// let 키워드는 필요에 따라 값을 재할당할 수 있다.
	let name = "홍길동";
	console.log(name); // 홍길동
	
	name = "김길동";
	console.log(name); // 김길동
</script>
```

3. **const**:
    - **스코프**: 블록 스코프를 가짐. `{}`로 둘러싸인 블록 내에서만 유효함.
    - **호이스팅**: `let`과 마찬가지로 호이스팅이 발생하지만, 선언 전에 접근할 수 없음.
    - **재할당**: 한 번 할당된 후에는 변수의 값을 변경할 수 없음(상수로 사용). 단, 객체나 배열 내부의 속성은 변경할 수 있음.
```html
<script>
	// const 키워드는 값을 재할당할 수 없다.
	const name = "홍길동";
	console.log(name); // 홍길동
	
	name = "김길동"; // 오류 발생
	console.log(name);
</script>
```
### 2.1.2 변수 이름 짓기  
- 자바스크립트에서 변수의 이름을 식별자(identifier)라고 하며, 식별자를 만들 때 사용되는 몇 가지 규칙이 있음.
1. 변수 이름에는 영어 알파벳, 숫자, 밑줄(`_`), `$`를 사용.
2. 변수 이름은 숫자로 시작할 수 없음.
3. 변수 이름은 대소문자를 구분.
4. 변수 이름을 길게 지을 경우에는 밑줄(`_`)이나 `CamelCase`를 사용
```html
<script>
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
</script>
```


---
## 2.2 데이터 형  
### 2.2.1 숫자  
- 자바스크립트에서 숫자 데이터에는 정수(integer)와 부동 소수점 숫자(floating point number)가 사용됨.
```html
<script>
	// 숫자 데이터 사용 예
	let a = 3; // 정수
	let b = 5.7; // 부동 소수점 숫자
	let c = 123e3; // 123000
	let d = 123e-3; // 0.123
	
	document.write(a + "<br />");
	document.write(b + "<br />");
	document.write(c + "<br />");
	document.write(d + "<br />");
</script>
```
### 2.2.2 Bigint  
- 15자리 이상의 정수를 사용하려면 Bigint 형을 사용해야 함.
- 정수 데이터 제일 뒤에 `n`을 붙이면 그 정수는 Bigint 형으로 저장됨.
```html
<script>
	// 일반 정수와 Bigint 데이터 형 사용 예
	let a = 999999999999999; // 15개의 정수
	let b = 9999999999999999; // 16개의 정수
	let c = 9999999999999999n; // Bigint에서는 정수 끝에 n을 붙임
	
	document.write(a + "<br />"); // 999999999999999
	document.write(b + "<br />"); // 10000000000000000 → 값이 정확하게 저장되지 않음
	document.write(c + "<br />"); // 9999999999999999
</script>
```
### 2.2.3 문자열  
- 문자열(string)은 하나 이상의 문자를 표현하는 데 사용됨.
- 문자열에서는 문자들을 큰 따옴표나 작은 따옴표로 감싸야 함.
```html
<script>
	// 문자열 사용 예
	let text1 = "사과";
	let text2 = '오렌지';
	
	document.write(text1 + "<br />");
	document.write(text2);
</script>
```
- 문자열의 `length` 프로퍼티를 이용하면 문자열의 길이(문자의 개수)를 구할 수 있음.
```html
<script>
	// 문자열의 length 프로퍼티 사용 예
	let text1 = "apple";
	let text2 = "사과";
	
	document.write(text1.length + "<br />"); // 5
	document.write(text2.length); // 2
</script>
```
- 큰 따옴표 안에 큰 따옴표를 사용하려면 이스케이프 문자를 사용.
```html
<script>
	// 큰 따옴표 안에 큰 따옴표가 사용된 경우
	let text1 = "내 이름은 "홍길동" 입니다."; // 오류 발생
	document.write(text1 + "<br />");
	
	let text2 = "내 이름은 \"홍길동\" 입니다."; // 이스케이프 문자 사용
	document.write(text2);
</script>
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
```html
<script>
	// 템플릿 문자열 사용 예
	let name = "홍길동";
	let age = 30;
	
	// 문자열 연결 연산자 (+)
	let text1 = "이름 : " + name + ", 나이 : " + age;
	// 템플릿 문자열
	let text2 = `이름 : ${name}, 나이 : ${age}`;
	
	document.write(text1 + "<br />");
	document.write(text2);
</script>
```
### 2.2.5 불  
- 불(boolean) 데이터 형에는 true와 false 값만이 존재함.
```html
<script>
	// 불 데이터 형 사용 예
	let x = 5 > 3; // true
	let y = 5 < 3; // false
	
	document.write(x + "<br />");
	document.write(y);
</script>
```
### 2.2.6 Undefined와 Null  
- 변수가 값을 가지고 있지 않으면 그 값은 undefined가 됨.
```html
<script>
	// Undefined 데이터 형 사용 예
	let x;
	
	document.write(x + "<br />"); // undefined
	document.write(typeof x); // undefined
</script>
```
- Null 데이터 형은 빈 문자열을 의미함.
```html
<script>
	// Null 데이터 형 사용 예
	let x = "";
	
	document.write("값 : " + x + "<br />"); // 빈 문자열(null)이 출력됨
	document.write("데이터 형 : " + typeof x); // string
	</script>
```
### 2.2.7 객체  
- 자바스크립트에서 객체는 {키: 값, 키: 값, 키: 값, ...}의 형태로 사용됨.
```html
<script>
	// 객체(object) 사용 예
	
	// member 객체는 세 쌍의 "키: 값" 요소들로 구성됨
	const member = { id: "kdhong", name: "홍길동", age: 20 };
	
	document.write(member.id + "<br />"); // kdhong
	document.write(member.name + "<br />"); // 홍길동
	document.write(member.age); // 20
</script>
```
### 2.2.8 배열  
- 배열은 다수의 값을 저장할 수 있는 특별한 변수. 객체와 밀접한 관계를 가지고 있음.
- 원소에 접근하려면 인덱스를 이용해야 함. 인덱스는 0부터 시작함.
```html
<script>
	// 배열(array) 사용 예
	const car = ["현대", "기아", "벤츠", "BMW"];
	
	// 인덱스를 이용해 요소에 접근
	// 인덱스는 0부터 시작
	document.write(car[0] + "<br />");
	document.write(car[1] + "<br />");
	document.write(car[2] + "<br />");
	document.write(car[3]);
</script>
```
### 2.2.9 심볼  
- 심볼은 숫자, 문자열, 불과 같은 원시 데이터 형을 의미함.
- 심볼은 유일한 식별자로서 객체의 속상을 추가하는 데 사용됨.
```html
<script>
	// 심볼(symbol) 사용 예
	const member = { name: "홍길동", age: 20 };
	let id = Symbol("id"); // id 심볼 생성
	member[id] = "kdhong"; // 객체 member의 키 id에 문자열 "kdhong"을 저장
	
	document.write(member[id] + "<br />"); // kdhong
	document.write(typeof id + "<br />"); // symbol
	document.write(id === Symbol("id")); // false → 심볼은 생성될 때마다 고유한 값을 가지기 때문
</script>
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
```html
<script>
	// 사칙연산 사용 예
	let x = 10;
	let y = 20;
	let z = x + (y * 5) / 2;
	
	document.write(z);
</script>
```

- 나머지 연산자는 `x`를 `y`로 나눈 나머지 값을 반환함.
```html
<script>
	// 나머지 연산자 사용 예
	let a = 10;
	let b = 20;
	let c = a % 2; // 몫: 5, 나머지: 0
	let d = b % 3; // 몫: 6, 나머지: 2
	let e = 3 % a; // 몫: 0, 나머지: 3
	
	document.write(c + "<br />");
	document.write(d + "<br />");
	document.write(e);
</script>
```

- 거듭제곱 연산자, 증가 연산자, 감소 연산자 사용 예시
```html
<script>
	// 거듭제곱 연산자, 증가/감소 연산자 사용 예
	let a = 3;
	let b = 5;
	let c = a ** 3; // 27
	c++; // 28
	c = c + 3; // 31
	c--; // 30
	c = a + b + c; // 38
	
	document.write(c);
</script>
```
### 2.3.2 문자열 연결 연산자  
- 문자열 연결 연산자는 `+` 기호를 사용함.
```html
<script>
	// 문자열 연결 연산자 사용 예
	let name = "홍길동";
	let age = 30;
	let text1 = "이름 : " + name;
	let text2 = "나이 : " + age;
	
	document.write(text1 + "<br />");
	document.write(text2);
</script>
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

```html
<script>
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
</script>
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

```html
<script>
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
</script>
```
### 2.3.5 논리 연산자  
- 논리 연산자에는 `&&`(AND), `||`(OR), `!`(NOT) 연산자가 있다.

| 논리 연산자 | 연산 | 설명 |
| :------: | :------: | -------- |
| `&&` | `AND` | 두 조건이 모두 `true`면 `true`를 반환 |
| <code>&#124;&#124;</code> | `OR` | 두 조건 중 하나만 `true`가 되어도 `true`를 반환 |
| `!` | `NOT` | 결과가 `true`면 `false`로, `false`면 `true`로 변경하여 반환 |

---

