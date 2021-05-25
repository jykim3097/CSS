# HTML5와 CSS

##블럭 요소와 인라인 요소
* 태그의 이름보다도 그 태그가 블럭인지 인라인인지가 더 중요하다

### 블럭 요소
* 화면 크기의 블럭을 갖는다
* 자동 줄바꿈이 일어난다
* 블럭요소 안에는 블럭요소와 인라인 요소를 가질 수 있다
* 대표적인 블럭요소(태그)
	* h1, p, div, ul, li, section, header, aside, article, footer, hr 등

### 인라인 요소
* 줄바꿈이 없다
* 인라인 요소에는 인라인만 들어갈 수 있다.
* 대표적인 인라인 요소(태그)
	* span, strong, b, img, a 등

## style sheet
* 인라인으로 작성한 스타일 > 내부 스타일 시트 > 외부 스타일 시트 순으로 코드가 실행된다. **(순서)**
* 외부 스타일 시트는 link 태그로 임포트한다
* css 파일에서 css 파일을 import 할 수 있다
```(html)
@import url("common.css");
```

## 선택자
* 태그 선택자, 다중 선택자, 하위 선택자, 자식 선택자, id 선택자, 클래스 선택자

#### 태그 선택자는 말 그대로 해당 태그에 적용할 스타일을 말한다

### 다중 선택자 
* **ul, li {list-style:none;}**
* 여러 개의 태그나 id, 클래스 선택자를 콤마(,)를 사용해 동시에 같은 스타일을 적용할 수 있다

### 하위 선택자 
* **div p {color:red;}**
* 첫번째 태그(또는 id, 클래스 선택자) 아래에 있는 모든 자식들 중 두번째 태그(또는 id, 클래스 선택자)와 같은 이름을 가진 태그(또는 id, 클래스 선택자)에 적용할 스타일
* 띄어쓰기로 구분한다

### 자식 선택자 
* ** section > p {color:blue;}**
* 첫번째 태그(또는 id, 클래스 선택자) 바로 아래에 있는 두번째 태그(또는 id, 클래스 선택자)와 같은 이름을 가진 태그(또는 id, 클래스 선택자)에만 스타일이 적용된다
* '>'로 구분한다

### id 선택자와 클래스 선택자
* id 선택자 : 유니크한 속성을 지닌다, #(이름)으로 표현한다
* 클래스 선택자 : .(이름)으로 표현한다

### 특정 속성을 지닌 태그
* [type="text"] {color:green;} : type이 text인 속성을 가진 모든 요소에 스타일을 적용한다
* [class*="col"] {color:green;} : class 이름에 col이라는 이름이 들어간 모든 요소에 스타일을 적용한다

### 가상 선택자
* hover, focus, active
* hover : 마우스가 닿을 때 적용할 스타일 설정
* focus : 마우스로 클릭했을 때 적용할 스타일 설정
* active : 마우스로 클릭했을 때만 적용되고 사라지는 스타일 설정

## font
### 웹폰트 가져오기
1. link 태그로 import하고 style 태그에서 폰트를 적용한다
```
<link rel="preconnect" href="https://fonts.gstatic.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR&display=swap" rel="stylesheet">

<style>
	* {font-family: 'Noto Serif KR', serif;}
</style>
```
2. style 태그에서 @import url 로 import하고 폰트를 적용한다
```
<style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+KR&display=swap');
        * {
            font-family: 'Noto Serif KR', serif;
            font-size: 30px;
            font-weight: 700;
        }
</style>
```

## 문단 정렬
### text-align
* 블럭 요소에서 가로 정렬
* left, center, right
### vertical-align
* 세로 정렬
* 요소를 나란히 배치할 때 **기준 속성에 문법을 적용**한다
* top, middle, bottom
### line-height
* 문단 간격
* 기준이 되는 태그가 없을 때 height와 line-height를 똑같이 설정하면 세로로 중앙 정렬할 수 있다

## 문단 숨기기(scroll)
* overflow: scroll; 넘치지 않아도 항상 가로세로 스크롤을 만든다
* overflow: hidden; 넘치면 넘친 것은 숨긴다
* overflow: auto; 넘치지 않으면 스크롤을 만들지 않고 넘치면 스크롤을 만든다
* overflow: visible; **Default**, 내용이 넘치면 넘친 채로 보여준다