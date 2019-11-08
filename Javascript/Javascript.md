## 유사배열 

```javascript
let chkboxes = Array.from(document.querySelectorAll('.questCheckBox'));
const ul = Array.from(chkbox.querySelectorAll('.checkBoxUl'));
```

document.querySelectorAll을 사용하면 해당 클래스명 혹은 아이디 등에 대한 모든 객체를 가져와서 chkboxes에 저장한다. 이때 배열형식으로 넘어오는데
유사배열이라서 자바스크립트의 배열로 바꿔 주기 위해서 `Array.form`으로 감싼다.

```javascript
const multiCnt = chkbox.querySelector('input[name=multiCnt]').value;
```

nam이 multiCnt인 체크박스의 값을 가져온다.

```javascript
const filteredUl = ul.filter(checkbox => checkbox.querySelector('li input[type=checkbox]').checked);
```

filter는 체크박스가 선택된 요소에 대해서 조건이 일치하는 애들을 변수에 담는다.


## 자바 스크립트 map

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map


## 자바스크립트 화살표 함수

화살표 함수 `=>` 는 `function` 키워드와 동일하다.

```javascript
const result = function(x) {
    return x*2;
}

const result = x => {
    return x*2;
}
```

> 즉, `function(x)` 펑션(매개변수) -> `x => `(매개변수) 화살표함수 

## 프로토타입

https://medium.com/@bluesh55/javascript-prototype-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-f8e67c286b67

- 프로토타입 사용 전

```javascript
function Person() {
    this.eyes = 2;
    this.nose = 1;
}

const kim = new Person();
const baek = new Perosn();

console.log(kim.eyes);
console.log(kim.nose);
console.log(baek.eyes);
console.log(baek.nose);
```

이런 방식으로 하면 메모리에 eyes와 nose가 2개씩 총 4개가 할당된다.

`prototype`을 사용하면 해결 가능

- 프로토타입 사용 후

```javascript
function Person() {}
Perosn.prototype.eyes = 2;
Person.prototype.nose = 1;

const kim = new Person();
const baek = new Person();

console.log(baek.nose);
```

메모리에 noes와 eyes가 1개씩 할당 된다.

프로토타입은 객체(eyes, nose)를 빈 공간에 넣어두고 kim과 baek 객체가 eyes와 nose를 공유해서 사용하는 것이다. 