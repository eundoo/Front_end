# ECMA Script

Ecma International(정보와 통신 시스템을 위한 국제적 표준화 기구)이 ECMA-262 기술 규격에 따라 정의하고 있는 표준화된 스크립트 프로그래밍 언어

넷스케이프 내비게이터 (넷스케이프 회사가 개발한 웹 브라우저)
- 초기 인터넷 사용사들의 폭발적 반응을 얻어 약 90%의 시장점유율을 차지했지만 
	1995년 마이크로 소프트가 인터넷 익스플로러를 개발하고 widows운영체제에 포함시켜 무료로 배포하면서 넷스케이프 내비게이터의 시장점유율이 급격하게 떨어짐

> 넷스케이프 출신의 일부 개발자들이 별도로 모질라 재단을 설립, 2002년 ‘파이어폭스’ 웹 브라우저를 출시

## 표준화하다
---
키보드 제조업체는 키보드 디자인으로 qwert레이아웃을 표준으로 따라 만들어진다. 
	이처럼 Ecma-262는 키보드의 레이아웃 대신에 스크립트 언어에 대한 표준을 정의한 규칙이라고 할 수 있다.

## 표준화가 필요한 이유
---
기본적으로 표준화가 필요한 이유는 하나로 통합되지 못하고 제각각 다르기 때문에 규칙과 질서가 필요함이 대두됨

어떤 웹브라우저(인터넷 익스플로러, 파이어폭스, 크롬...)를 들어가도 똑같은 화면이 보여져야 되는데 웹브라우저마다, 또 버전에 따라 지원이 다르기 때문에 각기 다 다르게 보여짐. 그래서 표준화가 필요함.

## EcmaScript 이름에서 오는 혼동
---
- EcmaScript는 순수 자바스크립트 그 자체 -> 해를 거듭하면서 버전이 업그레이드되고 			여러가지 기능이 추가되면서 좀 더 자바스크립트를 OOP관점의 코딩스타일이
	될 수 있도록 변해옴

- ‘JavaScipt라는 이름에 상표가 붙어 있었기 때문에 (Ecma international에서 주최하므로) 	EcmaScript를 선택했고 EcmaScript와 JavaScript라는 용어는 서로 바꾸어 사용 할 수 있다.

- 둘 다 뒤에 Script라는 키워드가 붙음. 하지만 자바스크립트는 언어이고, Ecma-script는 		규격, 표준이다. 
	JScript , TypeScript, JavaScript 등 을 방언 이라고 불리우는것 같다. 

- '언어'라는 것을 보면 글자가 만들어 진 후에 규칙이 생기니까 
	JavaScript가 먼저 생기고 Ecmascript가 그 후에 생겼다.

Ecma international > Ecma-262 >(Ecma-262에서 정의된 것들 중 하나의 사양인)EcmaScript
Ecma-262는 Ecma 인터네셔설에 의해 제정된 하나의 기술 규격의 이름(범용 목적의 스크립트 언어에 대한 명세를 담고 있다.)  
EcmaScript는 스크립트 언어가 준수해야 하는 규칙, 세부사항 및 지침을 제공

> 비교를 해서 좀 더 쉽게 설명하자면???
Ex) 국어 -> 표준어이다. / 국립국어원에서 관리 / 표준어는 국립국어원에서 제정한 여러가지 규칙들(발음, 맞춤법, 등) 일정한 원리를 따르고 있다.
Ex) Ecma-262 -> 표준이다.  / Ecma인터네셔널에서 관리 / EcmaScript는 맞춤법과 같은 규칙들….이라고 생각하면됨
국어를 어떤 규격과 규칙에 의해서 만들라 라는 것이 있지만 보이지 않는 것 처럼 -> Ecma-262

===>결국 이 Ecma-262를 가장 잘 반영하여 만들어 진게 JavaScript….

## JavaScript 짧게
---
Javascript의 역사 (Mocha -> Live Script -> JavaScript)
너무나도 동적인 웹을 좀 더 역동적으로 만들기 위한 방법이 필요함이 대두 -> Mocha 사상탄생

> ES => EcmaScript 버전별 차이점

	10개의 판이 출판

	1판1997년 초판

	2판 1998년 ISO/IEC 16262 국제 표준과 완전히 동일한 규격을 적용하기 위한 변경.
	
	3판 1999년 강력한 정규 표현식, 향상된 문자열 처리, 새로운 제어문 , try/catch 예외 처리, 엄격한 오류 정의, 수치형 출력의 포매팅 등.

	4판 4번째 판은 언어에 얽힌 정치적 차이로 인해 버려졌다. 이 판을 작업 가운데 일부는 5번째 판을 이루는 기본이 되고 다른 일부는 ECMA스크립트의 기본을 이루고 있다.

	5판 2009년 배열에 forEach, map, filter, reduce, some, every와 같은 메소드 지원
		Object에 대한 getter / setter 지원
		자바스크립트 strict 모드 지원 (더 깐깐한? 문법 검사를 한다.)
		JSON 지원 ( 과거에는 XML을 사용하다가, json이 뜨면서 지원하게 됨 )

	5.1판 2011년 ECMA스크립트 표준의 제 5.1판은 ISO/IEC 16262:2011 국제 표준 제3판과 함께 한다.

	6판 2015년(ES2015) 6판에는 클래스와 모듈 같은 복잡한 응용 프로그램을 작성하기 위한 새로운 문법이 추가되었다. 
		하지만 이러한 문법의 의미는 5판의 strict mode와 같은 방법으로 정의된다. 이 판은 "ECMAScript Harmony" 혹은 "ES6 Harmony" 등으로 불리기도 한다.
		let, const 키워드 추가
		arrow 문법 지원
		iterator / generator 추가
		module import / export 추가
		Promise 도입
	7판 2016년(ES2015) 제곱연산자 추가, Array.prototype.includes
		async — await

	8판 2017년(ES2016) 함수 표현식의 인자에서 trailing commas 허용, Object values/entries 메소드, async/await 등.

	9판 2018년(ES2018) Promise.finally, Async iteration, object rest/spread property 등.

	10판 2019년(ES2019) Object.fromEntries, flat, flatMap, Symbol.description, optional catch 등.