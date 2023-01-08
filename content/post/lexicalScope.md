---
title: "LexicalScope"
date: 2023-01-08T14:45:43+09:00
draft: false
---


### Lexcial Scope 란 ?

`lexical Scope` 는 함수와 변수의 Scope를 `선언된 위치`를 기준으로 정합니다.
반대의 개념으로 `Dynamic Scope` 가 있습니다, `Dynamic Scope`는 `호출된 시점을 기준`으로 사용합니다.

```javascript

var x = 1;

function a() {
	console.log(x);
}

function b() {
	var x = 10;
	a();
}

b();
```

위 코드의 결과 값은 `1` 이 출력 되고 있을 겁니다. 그 이유는 뭘까요 ?
함수. a는 변수 x가 선언된 시점의 전역 Scope를 가리키고 있습니다. 그래서 함수 b에서 a를 호출했어도, 1이 출력이 되는 것입니다.

그럼 아래코드는 어떻게 출력 되고 있을까요 ?

```javascript
var x = 1;

function a() {
	var x = 2;
	function b() {
		console.log(x)
	}
	
	b();
}

a();
```

**Javascript**는 선언된 위치를 기준으로 정해 집니다, 선언된 위치를 기준으로 생각해보면 
함수 b는 a의 안에 선언되어있기 때문에 변수 x는 2임을 알 수 있다. 따라서 2가 출력 되고 있을 것입니다.
하지면 여기서 정확한 동작을 이해하기 위해서는 `자신의 scope -> 자신을 포함하는 외부 함수 scope(함수 a) -> 전역 scope` 순으로 변수를 찾고 있는거을 기억해야합니다.

 a 함수가 b 함수의 변수에 접근 할 수 있는 이유는 `Scope Chain` 때문입니다. a 함수가 호출되면 우선 내부에서 변수를 찾습니다. a 함수의 내부에 뱌변수가 없으므로 Scope Chain 으로 연결 된 b 함수의 변수를 찾습니다. 만약 b 함수에도 변수가 없으면, 변수를 찾을 때 까지 최종적으로 전역 Scope 까지 찾은 후 없을 경우 에러를 발생합니다.
 
 ---
 - **Javascript**는 **Lexical Scope**를 사용하며, 이는 runtime에 동적으로 Scope를 정하지 않고, Complie 시점에 변수나 함수가 선언된 위치를 기준으로 Scope이 정해집니다.
 - 함수 내부에 선언된 함수는, 자신을 포함하는 외부 함수와 전역 Scope에 대한 Scope Chain 이 있다,

