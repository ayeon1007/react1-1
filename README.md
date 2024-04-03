# react1-1

# 202230234 조아연

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