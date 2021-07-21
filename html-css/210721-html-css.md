#### HTML – 제목, 문단, 표 등을 정의하고 그 구조와 의미를 부여하는 정적 언어
#### CSS – 마크업 언어(HTML 등)가 실제 표시되는 방법을 지정하여 시각적인 표현을 담당한다. 예쁘게 꾸며주는 역할
#### JS – 콘텐츠를 바꾸고 움직이는 등 페이지를 동적으로 꾸며주는 역할 

## HTML문법
 
 부모-자식 관계가 존재 tag가 tag를 감싸고 있다면 감싸는 tag가 부모
 조상-자손 관계도 존재 자식tag의 자식tag는 자손 tag라 보는 개념
``` 
Ex) 
<section>
<ul>
      <li></li>
    </ul>
</section>
```
이라면 section이 부모tag, ul이 자식 tag, li가 자손 tag가 된다.
물론 ul은 li의 부모tag이며 li도 ul의 자식tag이다.

빈 태그 – 닫히는 개념이 없는 태그들로 <>안에 /가 있는 경우와 없는 경우가 있지만 크게 중요치 않음 혼용하지 않는 것이 중요.

###Head tag

<head></head>내에서 사용하는 태그들은 HTML문서의 정보를 가진다.

#### 1.	Title
HTML문서의 제목을 정의. 웹 브라우저의 탭 부분에서 이름으로 표시됨.

#### 2.	Meta
기타 모든 정보를 표시하는 태그. 
Charset(문자인코딩 방식), name(정보의 종류), content(name속성의 값)등이 들어간다.

#### 3.	Link

외부 문서를 연결할 때 사용. html, css등의 파일을 불러와 연결
<link rel=”관계” href=”가져올 문서의 경로”> 관계에는 stylesheet, icon등이 들어간다.

#### 4.	Style

Css를 html 문서 내부에 작성할 때 사용.

#### 5.	Script

JS를 불러오거나 작성할 때 사용.
불러올 시에는 <script src=”js파일의 경로”></script>의 형식으로 사용한다.


### Body tag

<body></body>내에서 사용하는 태그들은 HTML문서의 구조를 나타냄.

#### 1.	Div

Division의 약자로 분할하는데 사용한다. Div 자체로는 아무 의미를 갖지 않으며 단순히 특정 범위를 묶는 용도로만 사용한다.

#### 2.	Img

이미지를 삽입하는데 사용한다.
<img src=”이미지의 경로” alt=”이미지의 대체 텍스트”>의 형식으로 사용한다.







## CSS문법

선택자, 속성, 값으로 이루어져 있다.

```
선택자{
   속성 : 값
}
의 형식으로 이루어진다.
```
### 선택자(selector)

Html에 css를 적용하기 위해 html의 특정한 요소를 선택하는 사인이다.
예를 들어 html내에서 div태그를 썼다면 css에서 선택자 부분에 div를 넣어준다면 html div부분의 색, 폰트 등을 바꿀 수 있는 틀을 마련하게 된다.

 * 클래스 선택자

html에서 클래스를 지정할 시 
ex)<div class=”title”></div>
css상에서 .title로 지정해 줄 수 있다. 

### 속성(Properties), 값(Value)

속성에는 글자 색, 너비, 여백등이 포함되며 값을 넣어 줌으로써 해당 값으로 변경 가능하다.
```
Ex) div{
      Color: red;
      Width: 300px;
    }
```
#### 속성 margin vs padding

Margin은 요소 외부의 여백을 의미한다. 
Padding은 요소 내부의 여백을 의미한다. 
둘 다 -left, -right, -bottom, -top을 붙여 각각 지정해 줄 수도 있다.

