# react1-1

# 202230234 조아연

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