# 정리를 마크다운으로 해보자

1. [마크다운 문법 및 개요](https://gist.github.com/ihoneymon/652be052a0727ad59601)

2. [마크다운 사용 에디터]( https://typora.io/)

   

***

> 첫주는 심화과정에 대비하여 패스트캠퍼스 온라인 강의로 html, css의 기초를 수강한다.
>
> 단 현재 html과 css의 기본적인 내용을 숙지하고 있으므로 복습위주로 공부한다.

<hr/>

# 시맨틱 구조로 간단한 html 구조를 작성해보자

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>콘텐츠 구분 예제</title>
        <link rel="stylesheet" href="main.css" />
    </head>
    <body>
        <header>
            <h1>header</h1>
            <nav>
                <h2>nav</h2>
            </nav>
        </header>
            <main>
                <section>
                    <h1>Section</h1>
                    <article>
                        <h2>article1</h2>
                        <p>Contents...</p>
                    </article>
                    <article>
                        <h2>article2</h2>
                        <p>Contents...</p>
                    </article>
                    <article>
                        <h2>article3</h2>
                        <p>Contents...</p>
                    </article>
                </section>
    
                <aside>
                    Aside
                </aside>
            </main>
        <footer>
            <address>
                <a href="mailto:ghkdxogus71@naver.com">ghkdxogus71@naver.com</a>
                <a href="tel:+82101012345678">010-1234-5678</a>
            </address>
        </footer>
    </body>
</html>

```

```css
header {
    background: tomato;
    margin: 10px;
    padding: 20px;
}

header nav {
}

header nav ul {
    display: flex;
}

header nav ul li {
    list-style: none;
    margin: 10px;
}

section {
    width : 70%;
    background : tomato;
    margin : 10px;
    padding: 10px;
    box-sizing: border-box;
}
section h1 {
}
main{
    display: flex;
}
article {
    background-color: yellowgreen;
    margin-bottom: 10px;
    padding: 10px;
}

article h2 {
}

article p {
}

aside {
    width: 30%;
    background-color: tomato;
    margin: 10px;
    padding: 20px;
    box-sizing: border-box;
}
footer {
    margin : 10px;
    padding: 20px;
    background-color: tomato;
}

footer address {
}

footer address a{
    display: block;
}

```

![image-20200311111232640](https://user-images.githubusercontent.com/50760015/76815169-4438f300-6840-11ea-95e6-5d963eb7adb8.png)

<hr/>

# css실습 전 환경설정

>  브라우저에서 제공하는 스타일이 표준화 되지 않았기 때문에 많은 브라우저에서 동일한 결과를 얻기 위해서 브라우저를 초기화 시켜야한다.

## 브라우저를 초기화 하기

직접 작성하여도 상관없지만 페이지가 많아질수록 불편하기 때문에 자동적으로 만들어진 라이브러리를 사용하는게 편하다.

1. [reset.css(github)](https://gist.github.com/DavidWells/18e73022e723037a50d6)
2. [reset.css(cdn)](https://cdnjs.com/libraries/meyer-reset)

<hr/>

## 코딩 가능한 사이트

내가 사용하였을때 가장 편했던 사이트 2가지를 소개한다.

1. [codePen](https://codepen.io/)
2. [codeSandbox](https://codesandbox.io/)

<hr/>

## 좀 더 편하게 html, css, javascript를 코딩하기

#### [emmet](https://emmet.io/) : **에밋**(Emmet)은 [HTML](https://ko.wikipedia.org/wiki/HTML), [XML](https://ko.wikipedia.org/wiki/XML), [XSL](https://ko.wikipedia.org/wiki/XSL) 문서 등을 편집할 때 빠른 코딩을 위해 사용하는 [플러그인](https://ko.wikipedia.org/wiki/플러그인)이다. 





> 내가 사용하는 vscode에서 사용하는 플러그인
>
> 1. Auto Close Tag : 태그를 자동으로 닫아줌
> 2. Auto Rename Tag : 짝태그를 수정
> 3. Bracket Pair Colorizer : 괄호마다 색상 다르게 표시
> 4. ESLint : JavaScript 코드에서 발견 된 문제 패턴을 식별하기위한 정적 코드 분석 도구
> 5. IntelliSense for CSS class names in HTML :  작성된 css 파일을 로드하여 css class를 자동 완성 함
> 6. Korean Language Pack for Visual Studio Code : vscode의 설정들을 한국어로 만들어줌
> 7. Live Server : 수정된 코드를 바로바로 반영하여 보여줌
> 8. Prettier - Code formatter : 코드를 설정대로 정렬해줌
> 9. vscode-icons : vscode의 확장자마다 보기 좋은 아이콘으로 보여줌

<hr/>

### css의 속성 - 박스모델

1. 가로너비 : width, max-width, min-width

2. 세로너비 : height, max-height, min-height

3. 요소의 바깥 여백 : margin(margin-top, margin-bottom, margin-right, margin-left)

   * 음수의 값 사용가능

   * 단축속성으로 

     * margin: 위, 우, 아래, 좌
     * margin : 위, [좌, 우], 아래;
     * margin : [위, 아래], [좌, 우]
     * margin : [위, 아래, 좌, 우]

   * 마진을 사용할 때 마진 중복이라는 현상이 일어난다.

     1. 형제 요소들의 margin-top과 margin-bottom이 만났을 때
     2. 부모 요소의 margin-top과 자식요소의 margin-top이 만났을 때
     3. 부모 요소의 margin-bottom과 자식요소의 margin-bottom이 만났을 때

     * 마진 중복이 발생할 시 둘다 양수이면 더 큰값으로 음수이면 더 작은수로 한다.
     * 각각 다르면 각 수를 더한다.

4. 요소의 내부 여백 : padding, 나머지 요소는 margin와 같다.

   * 추가된 padding 값만큼 요소의 크기가 커진다.

     * ```css
       /*크기가 120px 120px가 되어버린다.*/
       width: 100px;
       height: 100px;
       padding: 20px;
       ```

     * 위처럼 계산이 꼬이거나 하지 않기 위해 box-sizing: border-box;속성을 사용한다.

     * ```css
       /*크기가 100px 100px으로 고정된다.*/
       width: 100px;
       height: 100px;
       padding: 20px;
       box-sizing: border-box;
       ```

5. 요소의 테두리 선 : border(border-width, border-style, border-color)

   1. border-style

      1. soild : 실선
      2. dotted : 점선
      3. dashed : 파선
      4. double : 두줄선

      * 등이 있다

   2. padding처럼 요소의 크기가 증가할 수 있다.

6. 요소의 크기 계산 기준 설정 : box-sizing

   1. content-box(기본값)
      1. width, height만으로 요소 크기 계산
   2. border-box
      1. width, height와 border, padding까지 포함하여 계산한다.

7. 요소의 박스 타입을 설정 : display

   1. block(div), inline(span), inline-block(input) 등등을 설정할 수 있다.
   2. none로 설정하면 요소가 사라진다.

8. 요소의 크기 이상으로 자식요소가 넘쳤을대 내용의 보여짐을 제어

   1. visible : 넘친 부분을 자르지 않고 그대로 보여줌
   2. hidden : 넘친 부분을 잘라내고, 보이지 않도록함
   3. scroll : 넘친 부분을 잘라내고 스크롤바를 이용하여 보이게 함(잘리는 부분이 없더라도 수평 수직 스크롤바가 생성)
   4. auto : 넘친 부분이 있는 경우 잘라내고 스크롤바를 이용하여 보이게 함(잘리는 부분이 ㅇ벗으면 스크롤바 생성 X)

9. 요소의 투명도를 지정 : opacity

   1. 투명도는 0 ~ 1사이의 수로 표현한다.  (0.5 === 50%)

<hr/>

### css속성 - 글꼴, 문자

1. 글자 관련 속성 : font

   * 단축속성(기울기 두께 크기 / 줄높이 글꼴(내가 설정, 없을경우 시스템 글꼴))
     * 단축속성을 이용할려면 font-size(크기), font-family(글꼴)를 필수로 입력해야한다.

   1. font-style : 글자 기울기 지정
      1. normal : 스타일 없음
      2. italic : 이텔릭체
      3. oblique : 기울임체
   2. font-weight : 글자 두께 지정
      1. normal : 기본 글자 두게(400)
      2. bold : 두껍게(700)
      3. bolder : 부모요소보다 더 두껍게
      4. lighter : 부모요소보다 더 얇게
      5. 숫자 : 100~900에서 100단위로 직접 설정
   3. font-size : 글자 크기 지정
      1. 여러 많은 속성이 있지만 단위, %를 가장 많이 사용
   4. line-height : 줄 높이(줄 간격) 지정, reset.css하면 1정도로 지정됨
      1. 기본이 normal이지만 브라우저마다 다 다른 값을 가지기 때문에 값을 직접 설정해주는게 좋다.
      2. 단위를 적거나, 단위를 적지 않으면 글자의 크기의 배수로 지정이 된다.
   5. font-family : 글꼴(서체) 지정
      1. [글꼴후보1, 글꼴후보2, ...], 글꼴계열
      2. 글꼴계열은 필수이다.
      3. 글꼴후보를 두는 이유는 비슷한 글꼴을 지정하여서 해당 컴퓨터에 글꼴이 없을경우 대체하여 표현한다.
         1. serif : 바탕체 계열
         2. sans-serif : 고딕체 계열
         3. monospace : 고정너비 글꼴계열, 개발글꼴
         4. cursive : 필기체 계열
         5. fantasy : 장식(재미있게 문자 표현) 계열
   6. 글꼴의 색상 지정 : color
      1. 표현방식은 6가지가 있다.
         1. 색상이름 : 브라우저에서 제공하는 색상 이름
            1. red, blue ...
         2. Hex 색상코드 :  16 진수 색상
            1. #ffffff, #000000...
         3. RGB : 빛의 삼원색
            1. rgb(255, 255, 255)
         4. RGBA : 빛의 삼원색, 투명도
            1. rgba(255, 255, 255, 0.5)
         5. HSL : 색상, 채도, 명도
            1. hsl(120, 100%, 50%)
         6. HSKA : 색상, 채도, 명도, 투명도
            1. hska(120, 100%, 50%, 0.5)
   7. 문자 정렬 방식을 지정 : text-align
      1. left : 왼쪽 정렬
      2. right : 오른쪽 정렬
      3. center : 가운데 정렬
      4. justify : 양쪽 정렬(1줄 X, 2줄 이상, 줄바꿈 X)
   8. 문자의 장식(line)을 설정 : text-decoration
      1. none(선 없음), underline(밑줄 지정), overline(윗줄 지정), line=through(중앙 선 지정)
   9. 들여쓰기 : text-indent
      1. 음수 값 사용 가능
         * 음수값을 사용하면 들여쓰기
      2. 만약 존재는 하지만 보여주기 싫은 요소가 있을경우 명시적으로 -9999px을 입력한다.
   10. 문자의 자간(글자 간격) 설정 : letter-spacing
   11. 단어 사이(띄어쓰기) 간격 설정 : word-spacing

<hr/>

# css속성 - 띄움, 위치

1. 요소를 좌우 방향으로 띄움(수평 정렬) : float

   1. 원래는 좌우 방향을 띄우지만 그걸 이용하여 수평 정렬이 가능

      * 정렬과 다르게 left는 좌측부터 쌓기 시작 right는 우측부터 쌓기 시작한다.

      * 단 요즘은 flax-box로 한다.

   2. 요소는 수직으로 쌓인다. float를 적용하면 적용된 요소 주변으로 문자가 흐르게 된다. 

      * clear로 float를 제거할 수 있다.

      * clear로 적절한 곳에서 해제하지 않으면  아래쳐럼 짤린다.

      * ![image-20200312134324841](https://user-images.githubusercontent.com/50760015/76815197-51ee7880-6840-11ea-9e6b-acd0712382a6.png)

      * 위의 현상을 방지할려면 속성을 해제해야 한다.

        1. 형제요소에 clear:(left, right, both) 추가

        2. 부모요소에 overflow: (hidden, auto)

        3. 부모요소에 clearfix 클래스 추가(추천)

           1. ```css
              /*float부모 요소에 지정*/
              .clearfix::after{
                  content: "";
                  clear: both;
                  display: block; /*or 'table'*/
              }
              ```

              

        

   3. float 속성이 추가된 요소는 display 속성값이 대부분 block로 바뀐다.

      1. flex, inline-flex은 바뀌지 않는다.

2. float 속성이 적용되지 않도록 지정 : clear

   1. left, right, both, none 속성이 있다.

3. 요소의 위치 지정 방법의 유형(기준)을 설정 : position

   1. 속성
      1. static : 유형 없음/배치 불가능
      2. relative : 요소 자신을 기준으로 배치
         1. 주변에 영향을 주거나 받는다
         2. 그래서 주의해서 사용해야 한다.
      3. absolute : 위치 상 부모 요소를 기준으로 배치
         1. 구조상의 부모가 아닌 위치상의 부모이다.
         2. 위치상의 부모는 가장 가까운 position이 있는 부모를 의미한다. 최종적으로는 window(전체 뷰포트)까지 올라간다.
         3. 다른 속성들은 위치가 바뀔수도 있기 때문에 position: relative;를 설정한다.
      4. fixed : 브라우저(뷰포트)를 기준으로 배치
         1. absolute를 사용할 때 position값이 없을 경우 사용되는것과 같음
      5. sticky : 스크롤 영역 기준으로 배치
         1. 스크롤이 내려가도 붙어있다가 부모요소가 스크롤에서 사라지면 같이 사라진다.
         2. ![image-20200313112439437](https://user-images.githubusercontent.com/50760015/76815210-59158680-6840-11ea-9b3e-33f9e7f8b7b7.png)
   2. top, left, right, bottom으로 position 기준에 맞는 거리 설정
   3. 요소가 쌓여 있는 순서를 통해 여떤 요소가 사용자와 가까이 있는지를 결정 : 요소 쌓임 순서
      1. static을 제외한 position 속성 값이 있을경우 가장 위에 쌓임
      2. position이 모두 존재한다면 z-index속성의 숫자 값이 높을 수록 위에 쌓임
      3. position 속성의 값이 있고, z-index속성의 숫자 값이 같다면, HTML의 마지막 코드일 수록 위에 쌓임
   4. display 수정
      1. absolute, fixed을 사용하면 대부분 black으로 수정됨

<hr/>

# css속성 - background

1. 배경의 단축 : background

   1. background : 색상 이미지경로 반복 위치 스크롤특성;

2. 배경 색상 : background-color

   1. 색상, 투명도

3. 배경 이미지 : background-image

   1. 다중 이미지 속성

   2. ```css
      .box1{
          /*개별속성*/
          background-image: url('../li1.jpg'),
              url('../li2.jpg'),
      		url('../li3.jpg');
      }
      .box2{
          /*단축속성*/
          background: url('../li1.jpg') no-repeat,
              url('../li2.jpg') no-repeat 100px 50px,
              url('../li3.jpg') repeat-x;
      }
      ```

4. 배경 이미지 반복 : background-repeat

   1. repeat : 수직, 수평 반복
   2. repeat-x: 수평 반복
   3. repeat-y: 수직 반복
   4. no-repeat : 반복 없음

5. 배경 이미지 위치 : background-position

   1. background-position : 방향 1 방향 2;
   2. background-position : x축 y축;
   3. background-position : 50px bottom  //bottom top는 y축 left랑 right는 x축이다.

6. 배경 이미지의 스크롤 여부 : background-attachment

   1. scroll : 배경 이미지가 요소를 따라서 같이 스크롤 됨
   2. fixed : 배경 이미지가 뷰포트에 고정되어 요소와 같이 스크롤 X
   3. local : 요소 내 스크롤시 배경 이미지가 같이 스크롤됨

7. 배경 이미지의 크기를 지정 : background-size

   1. auto : 배경 이미지가 원래의 크기로 표시됨
   2. 단위 : 단위 지정, width height 형태로 입력가능, width만 입력하면 비율에 맞게 지정됨
   3. cover : 배경 이미지의 크기 비율을 유지하며, 요소의 더 넓은 너비에 맞춰짐, 이미지가 잘릴 수 있음
   4. contain : 배경 이미지의 크기 비율을 유지하며, 요소의 더 짧은 너비에 맞춰짐, 이미지가 잘리지 않음

<hr/>

# css속성 - 전환 & 변환

1. css속성의 시작과 끝을 지정(전환 효과)하여 중간 값을 애니메이션
   1. transition : 단축속성
      1. 쉼표로 나눠서 적용
   2. transition-property : 전환 효과를 사용할 속성 이름
      1. all or 속성이름
   3. transition-duration : 전환 효과의 지속시간 설정
      1. 기본은 s(초),  ms(밀리초)로도 가능
   4. transition-timing-function : 타이밍 함수 지정
      1. [Easing functions 정리](https://easings.net/)
      2. cubic-bezier(n, n, n, n)으로 자신만의 값을 정의
      3. steos(횟수) 
   5. transition-delay : 전환 효과의 대기시간 설정
      1. 기본은 s(초),  ms(밀리초)로도 가능
2. 요소의 변환 효과(변형)를 지정 : transform 
   1. 속성은 없고 함수로 정의한다.
   2. 배치하고 끝내는 경우는 position으로도 가능하지만 실시간으로 변화할 경우는 transform을 사용한다.
      * transition사용할때는 transform사용하자
   3. 2D속성
      1. [transform  2D](https://www.w3schools.com/css/css3_2dtransforms.asp)
      2. translate() : 이동(x축, y축)(단위로 지정)
      3. scale() : 크기(x축, y축)(배수로 지정)
      4. rotate() : 회전(각도)(deg)
      5. skew() : 비틀기(x축 y축)(deg)
   4. 3D속성
      1. [transform 3D](https://www.w3schools.com/css/css3_3dtransforms.asp)
      2. translate3d() : 이동(x, y, z)
      3. scale3d() : 크기(x, y, z)
      4. rotate3d() : 회전(x, y, z, 각도)
      5. persoective(n) : 원근법(거리) 
   5. transform 다른 속성
      1. transform-origin :  요소 변환의 기준점을 설정
         1. x축
            1. 기본값으로 50%
            2. left, right, center, %, 단위 사용
         2. y축
            1. 기본값으로 50%
            2. top, bottom, center, % 단위 사용
         3. z축
            1. 단위 사용
         4. transform-origin : 0% 0%로 설정하면 왼쪽 상단을 기준점 삼는다.
      2. transform-style : 3D 변환 요소의 자식 요소도 3d변환 사용 여부
         1. flat : 기본값으로 사용하지 않는다.
         2. preserve-3d : 자식 요소의 3d변환을 사용한다.
            1. 자손적용 X 자식만 적용
      3. perspective : 하위 요소를 관찰하여 원근 거리를 설정
         1. 속성과 함수의 차이
            1. perspective : 적용대상은 관찰 대상의 부모요소, 기준점 요소는 perspective-origin
            2. transform: perspective() : 적용 대상은 관찰 대상 기준점 설정은 transform-origin
      4. perspective-origin : 원근 거리의 기준점을 설정
         1. x축
            1. 기본값으로 50%
            2. left, right, center, %, 단위 사용
         2. y축
            1. 기본값으로 50%
            2. top, bottom, center, % 단위 사용
      5. backface-vsibility : 3D 변환으로 회전된 요소의 뒷면 설정을 숨김
         1. 뒤집으면 반전된 상태가 됨
         2. visible : 숨기지 않음
         3. hidden : 숨김

<hr/>

# css속성 - 애니메이션 & 다단

1. 요소의 애니메이션을 설정/제어 : animation

   1. animation : 애니메이션이름 지속시간 [타이밍함수 대기시간 반복횟수 반복방향 전후상태 재생/정지];

   2. ```css
      .box{
          width: 100px;
          height: 100px;
          background: tomato;
          animation: hello 2s linear infinite both;
      }
      @ketframes hello{
          0% {width: 200px; }
          100% { width: 50px; }
      }
      ```

2. 2개 이상의 애니메이션 중간 상태(프레임)을 지정 : @ketframes

   1. ```css
      @ketframes 애니메이션이름{
          0% {속성: 값; }
          50% {속성: 값; }
          100% {속성: 값; }
      }
      ```

3. 애니메이션 반복 방향 : animation-direction

   1. normal : 정방향
   2. reverse : 역방향
   3. alternate : 정방향에서 역방향 반복
   4. alternate-reverse : 역방향에서 정방향으로 반복

4. 애니메이션의 전후 상태(위치)를 설정

   1. ![image-20200313154357890](https://user-images.githubusercontent.com/50760015/76815228-65014880-6840-11ea-8c8c-6fe2365a95ee.png)

5. 애니메이션의 재생과 정지를 설정 : animation-play-state

   1. running, paused

<hr/>

# Multi-Columns

1. 일반 블록 레이아웃을 확장하여 여러 텍스트 다단으로 쉽게 정리하여 가독성 확복
2. 속성
   1. column-width : 단의 최적 너비를 설정
   2. column-count : 단의 개수를 설정
   3. column-gap : 단과 단 사이의 간격 설정
   4. column-rule : 단과 단 사이의 (구분)선을 지정 

<hr/>

# css속성/Flex(Flexible Box)

1. 수평 정렬을 하기 위해 나온 개념 예전에 많은 방법들이 있었지만 이제는 display:flex;로 쉽게 설정한다.

2. flex는 2개의 개념으로 나뉜다. container은 items를 감싸는 부모요소, item을 정렬하기 위해서는 container이 필요하다

   1. container

      1. display, flex-flow, justify-content 등이 있다.

         1. flex-flow : flex items의 주 축을 설정하고 items의 줄바꿈도 설정한다.

            1. ```css
               .flex-container{
                   flex-flow: row-reverse wrap
               }
               ```

            2. 주 축으로는 row(수평축), row-reverse, column(수직축), column-reverse

            3. 줄바꿈은 : nowrap, wrap, wrap-reverse

            4. 기본적으로 items는 한 줄에서만 표시되고 줄 바꿈 되지 않는다. 그렇기 때문에 부모요소에 따라 크기가 변할 수 있다.

         2. justify-content

            1. 주 축의 정렬 방법을 설정한다.
            2. justify-content의 속성
               1. flex-start : 시작점
               2. flex-end : 끝점
               3. center : 중간값
               4. space-between : 양끝에 요소를 붙이고 중간값
               5. space-around : 모든 요소의 남은 여백을 균등하게 분배

         3. align-content : 교차축일떄 items의 정렬

            1. 주의할 점은 items가 여러 줄 이고 여백이 있어야 사용가능
            2. justify-content와 속성이 같고 stretch(기본값, 교차축을 채우기 위해 items를 늘림)

         4. align-items : 교차축일떄 items의 정렬

            1. 주의할 점은 items가 여러줄이면 align-content가 우선 이걸 사용할려면 align-content가 기본값이어야 한다
            2. stretch, flex-start, flex-end, center, baseline(items를 문자 기준선에 정렬)가 있다.

   2. items

      1. order, flex, align-self 등이 있다.
         1. order : flex item의 순서를 설정
         2. flex : flex-grow, flex-shrink, flex-basis의 단축속성
            1. flex-grow : flex item의 증가 너비 비율 설정
            2. flex-shrink : flex item의 감소 너비 비율을 설정
            3. flex-basos : flex item의 (공간 배분 전) 기본 너비 설정
         3. align-self : 교차 축에서 item의 정렬 방법을 설정

<hr/>

# css속성/grid

1. display: grid;로 사용한다.

2. 열과 행의 크기를 정할 수 있다.

   1. grid-template-columns : 열의 크기 정의, grid-template-rows: 행의 크기 정의
      1. 동시에 라인의 이름 정의 가능
      2. fr 단위를 사용 가능
         1. 비율을 의밓마
      3. repeat() 함수를 사용 가능
         1. repeat(반복할 횟수, 반복할 단위)

3. grid-column, grid-row

   1. 특정 아이템을 위치시키기 
   
   2. ```css
      .item{
          grid-row: grid-row-start: 열 위치 / grid-row-end: 열 위치;
          grid-column: grid-column-start: 행 위치 / grid-column-end: 행 위치;
   }
      ```
   
   3. ```css
      .item:nth-child(1) {
          grid-column: 1 / 3;
          grid-row: 1 / 3;
      }
      
      .item:nth-child(2) {
          grid-row: 1 / 3;
      }
      
      .item:nth-child(4) {
          grid-row: 4 / 5;
          grid-column: -1 / -3;
      }
      ```
   
   4. ![image-20200317201224255](https://user-images.githubusercontent.com/50760015/76850890-a66b1580-688b-11ea-883b-fdde7d672708.png)
   
   5. grid는 맨 위는 row의 1번 선 맨 왼쪽은 column의 1번 선이다.
   
   6. 음수값은 각각 맨 아래 맨 오른쪽이 시작점이다.
   
4. grid-template-areas

   1. 3X3의 grid일때

      1. header header header
      2. main  main  aside
      3. footer footer footer

   2. ```css
      .container{
          display:grid;
          grid-template-rows: repeat(3, 100px);
          grid-template-columns: repeat(3, 1fr);
          grid-template-areas: 
          "header header header"
          "main main aside"
          "footer footer footer";
      }
      
      .item{
          border: 10px solid red;
      }
      
      .item:nth-child(1){
          grid-area: header;
      }
      .item:nth-child(2){
          grid-area: main;
      }
      .item:nth-child(3){
          grid-area: aside;
      }
      .item:nth-child(4){
          grid-area: footer;
      }
      
      ```

   3. ![image-20200317202902976](https://user-images.githubusercontent.com/50760015/76852081-f3e88200-688d-11ea-8668-e8f67a2ec3cd.png)

5. row-gap, column-gap

   1. 한 줄의 간격의 크기를 정한다.
   2. gap : row-gap column-gap으로 사용가능하다.
   3. 각 속성 앞에 grid가 붙어있는 경우도 있는데 현재는 사용하지 않아도 되지만 일부 버전 브라우저의 지원을 위해 grid-의 사용을 고려할 수 있다.

6. gird-auto-rows, gird-auto-column

   1. 암시적 행의 크기를 정의한다.
   2. 명시적 행 밖에 정의했을 때의 크기를 지정할 수 있다.

7. gird-auto-flow

   1. 배치하지 않은 아이템을 어떤 방식으로 자동 배치 알고리즘으로 처리할것인가
      1. row : 각 행 축을 따라
      2. column : 각 열 축을 따라
      3. row dense : 각 행 축을 따라 빈 영역을 메우면서
      4. column dense : 각 열 축을 따라 빈 영역을 메우면서

8. grid-template-rows, grid-template-rows

   1. 명시적 크기와 라인의 이름 정의
      1. grid-template-rows: [선이름] 1행크기, 2행크기 [선이름]
   2. fr(공간비율) 과 repeat함수 사용가능
      1. 12개의 행을 만들때 하나하나 정의 X
      2. grid-template-columns: repeat(12, 100px)
         1. 12개의 행을 100px

9. gird-row(grid-row-start, grid-row-end의 단축속성)

   1. /로 구분한다.					
   2. span이  start에 있는경우 end값부터 span만큼 올라오고
   3. span이 end에 있는경우 start부터 span 만큼 내려간다.

10. grid-area

    1. grid-row-start, grid-row-end, gird-column-start, gird-column-end의 단축속성이다
    2. 혹은 grid-template-area가 참조할 영역 이름 설정이 가능하다.
    3. 단 이름을 설정하면 gird-row와  gird -column을 사용 불가능