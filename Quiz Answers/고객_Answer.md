### Quiz (Mission)

1. 다음 소스 코드의 결과를 예측하고, 그 이유를 설명하라.

```js
greet('Shihu');
function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  age = '21';
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  return `Nice to meet you, ${name}!`;
}
```

> 호출된 함수는 실행될까?
> > 왜 그렇게 생각하는가? </br>
> > (자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)


> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>
> > 왜 그렇게 생각하는가? </br>
> > (선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)
#### 해설 및 풀이

해설 및 답 입력

```
호출된 함수는 실행이됩니다. 
그 이유는 변수선언 뿐만아니라 var, let, const, function, function*, class 키워드를 사용해서 선언하는 모든 식별자(변수,함수,클래스 등)는 호이스팅이 되기 때문이다. 
자바스크립트 엔진은 런타임이전에 위와 같은 것들은 먼저 실행시킨다.  따라서 함수가 어디서 정의되고 어디서 호출되는지는 상관이 없다. 정의되고 나서 호출해도되고 정의되기전에 호출해도된다.
그리고 그 안에 console.log가 실행이되는데  변수 age가 "21"을 할당받기 전에는 자바스크립트 엔진에 의해 undefined라는 값이 암묵적으로 할당되어 초기화되고 console.log 다음에 할당되어서
정상적으로 출력이된다.


다시한번 쉽게 설명하기전에 이 부분을 이해하면 더 쉽다. 

1. 함수 선언문
Function add(x,y){
	return x+y
}

2. 함수 표현식 (함수명 생략)
Var add = function(x,y) {
Return x+y
}


함수 선언문은, 런타임 이전에 이미 일반변수와 같이 선언되어 ‘호이스팅’되고
함수 표현식은, 런타임 이전에 undefined 로 변수를 초기화 시키고, 런타임 시 해당 함수가 할당 된다. 

이를 바탕으로 순서를 정리하자면

1. 자바스크립트 엔진은 런타임 전에 변수 age를  호이스팅하여 undefined라는 값으로 할당되어 초기화 할 뿐만아니라 function 키워드로 선언된 greet함수도 호이스팅 시킨다. 
2. 첫 번째줄 greet함수는 이미 자바스크립트 엔진에 의해서 호이스팅이 되어있기 때문에 정상작동한다.
3. 하지만 그 안에 age 변수는 21이 할당되기 전에 console.log가 이루어졌기에 undefined가 출력이되는것이다
4. Age = 21 로 변수 할당이 새롭게 되었기에 그 다음 console.log는  21이 출력이 된다. 




```
