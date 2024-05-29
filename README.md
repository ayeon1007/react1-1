# react1-1

# 202230234 조아연


## 5월 29일 강의 내용 정리
html에서는 textarea의 children으로 텍스트가 들어가는 형태
```js
<textarea>
 안녕하세요 여기에 이렇게 텍스트가 들어갑니다
</textarea>
```
* 리엑트에서는 state를 통해 태그의 value라는 attribute를 변경하여 텍스트를 표시

select 태그도 textarea와 동일
```js
<select>
    <option value="apple">사과</option>
    <option value="banana">바나나</option>
    <option value="grape">포도</option>
    <option value="watermelon">수박</option>
```
file input 태그는 그 값이 읽기 전용이기 때문에 리엑트에선 비제어 컴포넌트가 된다
```js
<input type="file" />
```
제어 컴포넌트에 value prop을 정해진 값으로 넣으면 코드를 수정하지 않는 한 입력값을 바꿀 수 없다   
만약 value prop은 넣되, 자유롭게 입력할 수 있게 만들고 싶다면 undefined이나 null을 넣기
```js
ReactDOM.render(<input value="hi" />, rootNode);

setTimeOut(function() {
    ReactDOM.render(<input value={null} />, rootNode);
}, 1000);
```

## 5월 22일 강의 내용 정리
리스트 키란 무엇인가?
* 리스트는 자바스크립트의 변수나 객체를 하나의 변수로 묶여놓은 배열과 같은 것
* 키는 각 객체와 아이텐을 구분할 수 있는 고유한 값 의미
* 리액트 에서는 배열의 키를 사용하는 반복되는 엘리먼트를 쉽게 렌더링 할 수 있다.

* 리스트에서의 키는 "리스트에서 아이템을 구별하기 위한 고유한 문자열"
* 이 키는 리스트에서 어떤 아이템이 변경, 추가 또는 제거 되었는지 구분하기 위해 사용

폼이란 무엇인가?
* 폼은 일반적으로 사용자부터 입력을 받기 위한 양식에서 많이 사용됨
```js
<form>
<lable>
이름 : 
<input type = "text" name = "name" />
</lable>
<button type="submit">제출</button>
</form>
```
* 제어 컴포넌트는 사용자가 입력한 값에 접근하고 제어할 수 있도록 해주는 컴포넌트


## 5월 8일 강의 내용 정리
이벤트 핸들러 추가하는 방법은?
* 버튼을 클릭하면 이벤트 핸들러 함수인 handleClick()함수를 호출하도록 되어 있다.

함수형에서 이벤트 핸들러를 정의하는 방법
* 함수형에서는 this를 사용하지 않고 onClick에서 바로 handleClick을 넘기면 됨

Arguments 전달하기
* 함수를 정의할 때는 파라미터(parameter) 혹은 매개변수 함수를 사용할 땐 Arguments 혹은 인수라고 부름
* 이벤트 핸들러에 매개변수를 전달해야하는 경우도 있음

조건부 랜더링이란?
* props로 전달 받은 issloggdln아 true이면 <UseGreeting/>을, false면 <FuestGreeting/>을 return함
* 이와 같은 렌더링을 조건부 랜더링이라 함


## 5월 1일 강의 내용 정리
훅의 두 가지 규칙
* 첫 번째 규칙은 무조건 최상의 레벨에서만 호출되어야 한다는 것. 반복문이나 조건문 또는 중첩된 함수들 안에서 훅을 호출하면 안 됨. 이 규칙에 따라서 훅은 컴포넌트가 렌더링 될 때마다 같은 순서로 호출되어야 한다.
* 두 번째 규칙은 함수형 컴포넌트에서만 훅을 호출해야 한다는 점. 따라서 일반 자바스크립트 함수에서 훅을 호출하면 안 된다. 훅은 함수형 컴포넌트 훅은 직접 만든 커스텀 컴포넌트 안에서만 호출할 수 있다.
* 필요하다면 직접 훅을 만들어 쓸 수도 있다. 이것을 커스텀 훅이라 부른다

```js
* userstatus 코드 예시
import { useState, useEffect } from "react";

export default function UserStatus (props) {
    const isOnline, useUserStatus(props.user.id)
    if(isOnline===null) {
        return'대기 중...'
    }
    return isOnline ? '온라인' : '오프라인'
}
```
* 한 가지 주의할 점은 일반 컴포넌트와 마찬가지로 다른 훅을 호출하는 것은 무조건 커스텀 훅의 최상의 레벨에서만 해야함.
* 이름은 use로 시작해야함. 그렇지 않으면 다른 훅을 불러올 수 없음

이벤트 핸들링
```js
DOM에서 클릭 이벤트를 처리하는 예제 코드
<button onclick="activate()">
    Activite
</button>
```

```js
React에서 클릭 이벤트 처리하는 예제코드
<button onClick="(activate)">
    Activite
</button>
```
* 이 둘의 차이점은 이벤트 이름이 onclick에서 onClick으로 변경, 전달 하려는 함수는 문자열에서 함수 그대로 전달
* 이벤트가 발생했을 때 해당 이벤트를 처리하는 함수를 이벤트 핸들러라 한다

이벤트 핸들러 추가하는 방법은?
* 버튼을 클릭하면 이벤트 핸들러 함수인 handleClick()함수를 호출하도록 되어있다.

## 4월 17일 강의 내용 정리
훅이란 무엇인가?
* 클래스형 컴포넌트에서는 생성자(constructor)에서 state를 정의하고, setState() 함수를 통해 state를 업데이트!
* 함수형 컴포넌트에서도 state나 생명주기 함수의 기능을 사용하게 해주기 위해 추가된 기능이 바로 훅(Hook)이다
* 훅의 이름은 모두 use로 시작
* 함수형 컴포넌트도 훅을 사용하여 클래스형 컴포넌트의 기능을 모드 동일하게 구현할 수 있게 됨

useState
* useState는 함수형 컴포넌트에서 state를 사용하기 위한 hook
```js
import React, {useState} from "react";

export default function Counter(props) {
    const [count, setCount] =useState(0)
    return (
        <>
        <p>총 {count}번 클릭하였습니다.</p>
        <button onClick={() => setCount(count+1)}>클릭</button>
        </>
    )
}
```

useEffect
* useState와 함께 많이 사용되는 Hook
* 사이드 이펙트를 수행하기 위한 것
* 클래스 컴포넌트의 생명주기 함수와 가능 기능을 하나로 통합한 기능 제공
```js
useEffect(이펙트 함수, 의존성 배열)
```
* 의존성 배열은 이펙트가 의존하고 있는 배열로, 배열 안에 있는 변수 중에 하나라도 값이 변경 되었을 때 이펙트 함수가 실행됨
* 이펙트 함수는 처음 컴포넌트가 렌더링 된 이후, 그리고 재렌더링 이후에 실행

useMemo
* useMemo() 혹은 Memoizde value를 리턴하는 Hook
* 이전 계산값을 갖고 있기 때문에 연산량의 많은 작업의 반복을 피할 수 있다
* 이 훅은 렌더링이 일어나는 동안에 실행된다
```js
const memoizedValue = useMemo(
    ()=>{
        //연산량이 높은 작업을 수행하여 결과를 반환
        return computeExpensiveValue(의존성 변수1, 의존성 변수2);
    },
    [의존성 변수1, 의존성 변수2]
);
```
* 따라서 의존성 배열을 넣지 않는 것은 의미가 없다
* 만약 빈 배열을 넣게 되면 컴포넌트 마운트 시에만 실행
```js
const memoizedvalue = useMemo(
    () => computeExpensiveValue(a, b)
);
```

useCallback
* useCallback() 혹은 useMemo()와 유사한 역할을 합니다
* 차이점은 값이 아닌 함수를 반환한다는 것
* 의존성 배열을 파라미터로 받는 것은 useMemo와 동일
* 파라미터로 받은 함수를 콜백이라 부름
* useMemo와 마찬가지로 의존성 배열 중 하나라도 변경되면 콜백함수를 반환
```js
const memoizedCallback = useCallback(
    () => {
        doSomething(의존성 변수1, 의존성 변수2)
    },
    [의존성 변수1, 의존성 변수2]
);
```

useRef
* useRef() 혹은 레퍼런스를 사용하기 위한 훅
* 레퍼런스란 특정 컴포넌트에 접근할 수 있는 객체를 의미
* 레퍼런스 객체에는 .current라는 속성이 있는데 이것은 현재 참조하고 있는 엘리먼트를 의미
```js
const refContainer = useRef(초기값);
```
* 이렇게 반환된 레퍼런스 객체는 컴포넌트의 라이프타임 전체에 걸쳐서 유지
* 즉, 컴포넌트 마운트 해제 전까지는 계속 유지됨

훅의 규칙
1. 첫 번째는 무조건 최상의 레벨에서만 호출해야 하는 것. 최상위 컴포넌트의 레벨 의미
2. 반복문이나 조건문 또는 중첩된 함수들 안에서 훅을 호출하면 안 됨
3. 이 규칙에 따라서 훅은 컴포넌트가 렌더링 될 때마다
## 4월 3일 강의 내용 정리
* 컴포넌트 구조라는 것은 작은 컴포넌트가 모여 큰 컴포넌트를 구성하고, 다시 이런 컴포넌트들이 모여서 전체 페이지를 구성하다는 것을 의미
* 컴포넌트는 자바스크립트 함수처럼 입력과 출력이 있다는 면에서는 유사
* 다만 입력은 Props가 담당, 출력은 리엑트 엘리먼트의 형태로 출력.    Props? proprty의 준말.
컴포넌트에 어떤 속성, props를 넣느냐에 따라 속성이 다른 엘리멘트가 출력.
* Props의 특징은 읽기 전용이고, 변경할 수 없다.

* Pure 함수는 인수로 받은 정보가 함수 내부에서도 변하지 않는 함수
```js
// input를 변경하지 않으며 같은 input에 대해서 항상 같은 output을 리턴
funtion sum(a,b) {
    return a + b;
}
```
* impure 함수는 인수로 받은 정보가 함수 내부에서 변하는 함수
```js
// input를 변경함
funtion withdraw(account, amount) {
    account.total -=amount;
}
```

* JSX를 사용하지 않는 경우 props의 전달 방법은 createElement()함수를 사용

* createElememt()함수의 두 번째 매개변수가 props이다
* JSX를 사용하지 않으면 이와 같이 코드를 작성
```js
    React.createElement(
        Profile,{
            name : "소플",
            introdution "안녕하세요, 소플입니다.",
            viewCount : 1500;
        },
        null
    );
```
컴포넌트의 렌더링
```js
funtion Welcome(props){
    return<h1>안녕,(props.name)</h1>
}
const element = <Welcome name="인제 /">;
ReatDOM.render(
    element,
    document.getElementById('root')
);
```
State란?  
* 리엑트 컴포넌트 상태 의미
* 상태의 의미는 정상인 지 비정상인 지가 아니라 컴포넌트 데이터를 의미

state를 변경하고자 할 때에는 setState()함수를 사용

## 3월 27일 강의 내용 정리
* JSX란? Javascript에 XML을 주가한 확장 문법.
* JSX는 내부적으로 XML/HTML 코드를 자바스크립트로 변환을 해 주고, React가 createElement함수를 사용하여 자동으로 자바스크립트로 변환을 해준다.
* 모든 자바스크립트 문법을 지원하고 자바스크립트 문법에 XML과 HTML을 섞어서 사용한다
* 엘리먼트는 리액트 앱을 구성하는 요소를 의미
* 리엑트 엘리먼트는 Virtual DOM의 형태를 취하고 있다
* 업데이트 속도같은 경우, DOM은 느리고 Virtual DOM은 빠름
* 리액트 앨리먼트는 자바스크립트 객체의 형태로 존재
* 컴포넌트(Button등), 속성(color등) 내부의 모든 children을 포함하는 일반 JS객체

다음은 id값이 root인 div태그로 단순하지만 리액트에 필수로 들어가는 중요코드
```js
<div id = 'root'></div>
```
엘리먼트를 렌더링하기 위해선 이와같은 코드가 필요
```js
const element = <h1>안녕, 리엑트!</h1>
ReactDOM.render(element, doqument.getElementById('root'));
```

***
## 3월 20일 수업 내용 정리
* 리엑트의 장점으로는 빠른 업데이트와 렌더링 속도인데, 이것을 가능하게 하는 것이 Virtual DOM이다.
* Virtual DOM은 DOM 조작이 변화하지 않은 것까지 바꿔줘 비효율적인 이유로 속도가 느려 고안한 방법이다.
* 또 다른 장점으론 컴포넌트를 사용해 반복되는 작업을 줄여줘 생산성을 높여준다.

***
## 3월 13일 강의 내용 정리
기본적인 사용법 배움