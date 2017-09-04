# [JS STUDY](https://iolite85.github.io/study) 정리
## 이론 / 정리
### EXAM 1. Javascript / jQuery
- javascript 와 jQuery 차이점  
    - javascript는 메서드를 이용해서 일일히 접근해야 하는 불편함이 있으며, IE하위버전에 지원하지 않는 기능들이 있어 크로스브라우징이 어렵다.
    - jQuery 는 selector 선택을 css와 동일하게 사용 가능하며, 크로스브라우징이 쉽다.
> Javascript Selector

```javascript
document.getElementById('id');
document.getElementsByClass('class'); // ie 하위 버전 지원 안함
document.getElementsByTagName('tagName')
```
> jQuery Select

```javascript
$('#id');
$('.class');
$('tagName')
```
### EXAM 2. Prototype

- prototype 메서드들의 기능과 사용방법 정 리
#### [Array](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/prototype)
- Array.join() : 배열의 모든 요소를 연결해 하나의 문자열로 만듬.
- Array.reverse() : 배열을 반전.(첫 번째 요소는 마지막 요소가 되며 마지막 요소는 첫 번째 요소가 됨)
- Array.sort() : 배열의 요소를 정렬하고 그 배열을 반환.
- Array.slice() : 배열의 일부를 추출한 새 배열을 반환.
- Array.splice() : 배열에서 요소를 추가/삭제.
- Array.push() : 배열의 끝에 하나 이상의 요소를 추가하고, 변경된 배열의 길이를 반환.
- Array.pop() : 배열에서 마지막 요소를 제거하고, 그 요소를 반환.

#### [String](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/prototype)
- String.replace() : 기존 문자열을 교체된 새로운 문자열로 반환.
- String.slice() : 문자열의 일부를 추출하여 반환.
- String.split() : 지정된 구분 기호(' ')를 사용하여 문자열을 분할하고 배열로 반환
- String.trim() : 첫번째 문자열 앞, 마지막 문자열 뒤의 공백을 제거.
- String.indexOf() : 인자 값의 첫 번째 일치하는 인덱스를 반환. 일치하는 값이 없으면 -1을 반환.

#### [Object](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype)
- Object.hasOwnProperty() : 객체가 특정 프로퍼티를 가지고 있는지를  나타내는 불리언(true, false) 값을 반환.(이 메소드는 객체가 특정 프로퍼티를 자기만의 직접적인 프로퍼티로서 소유하고 있는지를 판단하는데 사용된다.  [`in`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/in) 연산과는 다르게, 이 메소드는 객체의 프로토타입 체인을 확인하지는 않는다.)
### EXAM 3. 함수선언 및 호출 / if (조건문) 

- **선언함수 : **함수호출구문이 함수선언구문 앞에 와도 함수가 호출이 되기 때문에 가급적 지양하는 방법

  ```javascript
  function sum() {
      var a = 10;
      var b = 20;
      var c = a + b;
  };
  ```


- **익명함수** :  반드시 함수정의 후 함수 밑에서 호출하는 방식(함수 호이스팅 X)

  ```javascript
  var sum = function () {
      var a = 10;
      var b = 20;
      var c = a + b;
  };
  ```

- if(조건문)을 사용하여 index 제어
> Point
> - index 가 li의 개수를 초과 한 경우 첫번째 index로, index가 0 보다 작으면 마지막 index로 - 무한루프
> - 이벤트가 실행되고 나면 currentIdx를 oldIdx에 저장
### EXAM 4. for/while
- for / while 문을 사용하여 input, checkbox, 구구단 출력
    - 빈 배열을 선언
    - 반복문 실행(조건에 따라 조건문도 같이 실행)
    - push, get(0) 으로 출력
> Point
> - [get()](http://api.jquery.com/get/): 어떤 구조를 객체화 시켜서 가져옮(jquery에서 javascrip 메서드를 바로 사용 할 수 있게 함 )

### EXAM 5. Object
- [object 문제 풀이](https://iolite85.github.io/study/exam5/object.html)
> Point
> - new: 기존 함수에 new 연산자를 붙여서 호출하면 해당 함수는 객체로 생성됨. (생성자 함수)
> - 객체 내에서의 this는 자신을 호출한 객체에 바인딩 됨.

### EXAM 6. Array (배열)
- [Array을 객체화 하여 문제 풀이](https://iolite85.github.io/study/exam6/array.html)
> Point
>
> - Math.random() : 랜덤 함수 
> - slice() 메소드를 이용 배열을 복제하여 배열과 배열 비교
> - for문 안에 for문 사용 하여 이중배열 구성

#### 배열 정렬

``` javascript
var array = [10, 20, 40, 5];
array.sort(function(a, b){
    return b - a // 역순(큰수부터 나열)
});
```
#### 랜덤

```javascript
var array = [];
for (var i = 0, max = 7; i < max; i++) {
    array[i] = Math.floor(Math.random() * 7); // floor 정수로 반환. 반내림
}
```

#### 이중배열

```javascript
var array = [];
for (var i = 0, i < 5; i++) {
    array[i] = []; // Array[[],[],[],[],[]] -- 배열 안에 다섯개의 배열이 생성
    for (var j = 0; j < 5; j++) {
        array[i][j] = i * j; // Array[[0],[1],[2],[3],[4]] -- 배열안의 배열에 값 저장
    }
}
console.log(array);
```
#### 배열과 배열 비교
```javascript
var array = [30, 100, 2, 200];
var cloneArray = array.slice();
```
## 예제
### EXAM 7. [line play - 캐릭터 랜덤 노출](https://iolite85.github.io/study/exam7/line_play.html)
1. 첫 로딩 시 아바타 랜덤 노출
2. 버튼 클릭 시 중복되지 않는 아바타 노출
3. 아바타가 전부 노출이 되고 나면, 다시 세팅 - 무한루프 (단 마지막 아바타와 다시 세팅되어 처음 노출되는 아바타가 동일하면 안됨)
4. 마크업 코드가 사라지면 안됨
> Point
> - 먼저 아바타 배열을 랜덤으로 만들어주고 배열 값을 하나씩 삭제
> - 삭제될 때 currentIdx를 oldIdx에 넣어줌
> - 배열의 인덱스값과 실제 인덱스값 혼동 주의
### EXAM 8. [폴라베어를 잡아라](https://iolite85.github.io/study/exam8/exam8.html)
1. 선택한 곰 인덱스대로 선택 / 선택한 곰을 제외한 인덱스 중 랜덤 선택 
2. 곰이 선택되어 있지 않고 ‘선택하기’를 누르면 ‘곰을 선택하세요’ alert
3. 곰 선택 이벤트가 모두 완료되고 다시 ‘선택하기’ 버튼을 누르면 ‘이미 참여했습니다’ alert
> Point
> - 초기 옵션 설정 (처음 false, 곰을 클릭하고 나면 true로 치환)
> - true / false 로 이벤트 타입 컨트롤
> - 곰 선택(radio) [change()](https://api.jquery.com/change/) event: 
>   - [currentTarget() ](https://api.jquery.com/event.currentTarget/): 이벤트 리스너가 바인딩 되어있는 대상(실제 이벤트가 걸려있는 요소)
>   - [closest()](https://api.jquery.com/closest/) : 셀렉터와 가장 일치하는 가장 근접한 상위 요소(직계부모 부터 최상위 요소까지 모두 탐색)를 리턴 - 직계부모 선택 시 [parent()](https://api.jquery.com/parent/)를 사용할 수 있으나 코드 확장성이 용이하지 않음
> - [setTimeout()](https://www.w3schools.com/jsref/met_win_settimeout.asp): 지정한 시간이 만료된 뒤 함수나 지정된 코드를 실행

### EXAM 9. [layer popup](https://iolite85.github.io/study/exam9/layerPop.html)

- 접근성(키보드 제어)을 유지하며 레이어팝업 띄우기 / 제거하기
1. 탭으로 접근 가능
2. 닫기를 누르지 않으면 레이어팝업 내에서 계속 탭이 돌아야 함.
3. 버튼 여러개 존재할 때, 각 버튼을 클릭할 때마다 해당 레이어를 띄우지만, 레이어가 닫힐 경우 클릭한 버튼으로 포커스를 이동시킨다.
4. 레이어팝업 외부영역(dimmed) 클릭 시 레이어팝업 닫기 (clickoutside 이벤트 사용)
> Point
> - 이벤트가 발생하는 순서에 유의
> - js로 레이어 팝업 앞, 뒤에 빈 태그를 넣어주고 tabindex를 넣음 (attr('tabindex','0'))
> - 레이어를 띄우는 순간 js 로 넣은 span 태그로 focus가 가도록 함
> - [clickoutside plugin](http://benalman.com/projects/jquery-outside-events-plugin/) 사용
>   - 레이어가 열리면 setTimeout으로 약간의 시간차를 두고 clickoutside 실행
>   - 레이어가 닫힐 때 clickoutside off

### EXAM 10. [Tab / Slide](https://iolite85.github.io/study/exam10)
#### 1. Tab
- 테마(Number)를 클릭할 경우, 각 Number와 매칭되는 컨텐츠(Number)를 보여지게 한다.
- 이전/다음 버튼을 클릭할 경우, 기존 Number들을 -/+ 하면서 보여지게 하고, loop 되게 한다.
- 해당 컨텐츠에 맞는 Number를 페이징처럼 보여지게 한다. ( 4번째 컨텐츠이면, 4 / 8 )
- hash 사용
#### 2. Slide (Carousel)
- 위 tab 1과 기능 동일
- 2가지 이상의 모션(fade, slide) 옵션
> Point
> - 인터렉션 타입에 따라 분리하여 처리(tab / slide / fade)
> - e.preventDefault(): 이벤트의 동작 중단(Anchor 이동 정지)
> - 현재 탭의 넘버를 get(0).innerHTML로 넣어주는 방법 외에, text()로 추가하는 방법도 있음.

### EXAM 11. [Form 제어](https://iolite85.github.io/study/exam11)
- 체크박스, 라디오버튼, 셀렉트 박스 제어
- 셀렉트 박스는 [plugin](https://github.com/realyuki/study/blob/gh-pages/convention/03_Prototype.md) 으로 만들어 사용
> Point 
> - 이벤트 처리는 input을 대상으로 change 이벤트가 발생할 때
> - 태그속성에 따라서 기능이 제어되는 속성에 대해서는 prop() 사용
> - Form에서 checkbox나 radio버튼처럼, 요소 자체에 filter할 수 있는 기능(checked, name 등)이 있으면 굳이 플러그인화가 필요하지 않음.
### EXAM 12. [Sort](https://iolite85.github.io/study/exam12)
- table 의 열(col)을 정렬
1. 테이블의 컨텐츠 선택
2. 각각 버튼을 누르면 배열 생성 후 정렬 (sort): 번호(오름차순), 제목(알파벳 a, b, c...), 작성자(한글 ㄱ, ㄴ, ㄷ...)
3. 정렬된 값을 배열에 넣어준 후 값 반환
> Point
> - 정렬 후 table에 값을 넣을 때 tr을 tbody.children() 으로 선택
> - last().after() / first().before()

### EXAM 13. [Sticky + Top Button](https://iolite85.github.io/study/exam13)
- 스크롤이 일정 구간을 지나면 nav 상단 고정
- header / footer 에서는 top button 비노출, 헤더와 푸터를 제외한 부분에서 노출
> Point
> - [offset()](http://api.jquery.com/offset/): 요소의 브라우저상의 위치값을 반환
> - [outerHeight()](https://api.jquery.com/outerHeight/): margin 값을 포함하지 않을거면 false, 포함한다면 true

### EXAM 14. [Anchor Nav](https://iolite85.github.io/study/exam14)
1. 첫 번째 컨테이너의 top 지점을 지날 때 퀵메뉴 fix
2. 각 메뉴 클릭시 해당 컨테이너의 top 지점으로 스크롤 이동
3. 퀵메뉴의 go to top 링크 클릭 시 브라우저 탑으로 이동
4. 1번에서 3번 또는 3번에서 1번 컨테이너로 스크롤 이동 시 2번 앵커가 활성화되면 안됨

> Point
> - 네비게이션의 href 값을 가진 id값이 페이지 내에 있는지부터 체크 한 후 반환
> - 스크롤이 끝났을 때 한번만 실행되게 clearTimeout()을 사용
> - [clearTimeout()](https://www.w3schools.com/jsref/met_win_cleartimeout.asp): setTimeout()으로 실행 한 함수를 멈출때 사용
> - 1번에서 3번 또는 3번에서 1번 컨테이너로 이동 시 2가 활성화 되면 안되기 때문에 scroll이 끝나면 anchor를 활성화
```javascript
...
scrollFunc : function () {
    this.quickFixedFunc();
    win.clearTimeout(this.scrollEndTime);
    this.scrollEndTime = win.setTimeout($.proxy(this.scrollEndFunc, this), 150);
},
...
```

### EXAM 15. [Responsive Gnb](https://iolite85.github.io/study/exam15/gnb.html)
- 반응형으로 PC/Mobile gnb 구현
- PC: focusin 시 outside로 동작하도록 구현
- Mobile: navigation outside 구현
> Point
> - 반응형 type 체크 (중요)
> - 모바일, pc 일때 각각의 이벤트가 실행되도록 해줌 (불필요한 이벤트 발생 막음)
> - UTIL.isSupportTransform 으로 반응형 지원 여부 체크하여 이벤트 발생 (반응형을 지원하지 않으면 pc 이벤트만 발생시킴)
