<!-- @format -->

[back](README.md)

# 2주차 학습 내용

- ## 200817 월요일

## 임베디드 요소

embed 요소는 외부에서 콘텐츠를 가져오는 요소를 지칭한다.

---

- 1. HTML 픽쳐(Picture) 요소

```html
0개 이상의
<source />
요소와 1개 이상의 <img />를 포함하는 컨테이너 요소. 다양한 스크린 환경에 맞는
적합한 이미지를 제공하기 위한 목적으로 사용한다.
<source />
요소를 사용할 수 없는 경우, <img /> 요소가 화면에 표시된다.
```

```html
[사용예시] (+picture 엘리먼트는 img를 포함한 컨테이너 요소)

<picture>
  <source
    srcset="media/image/kitten-large.png"
    type="image/png"
    media="(min-width: 900px)"
  />
  <img src="media/image/kitten-small.png" alt="웃는 고양이" />
</picture>
```

---

- 2. HTML 비디오(Video) 요소

```html
동영상 콘텐츠를 html 문서에 포함하기 위해서 사용한다. src 속성이나 source 요소를
이용해 여러개의 동영상 소스 중 하나를 표시한다.
```

```html
[사용예시]
<video src="videofile.mp4" poster="posterimage.jpg" controls autoplay="true" loop="true" muted="true">
HTML5 <code><video></code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
<a href="http://outdatebrowser.com/ko"> 최신형 브라우저로 업데이트</a> 업데이트 하세요.
</video>

[속성]
src - 비디오 파일 경로
poster - 포스터 이미지 경로
preload - auto(기본 값) 브라우저를 미리 읽어와서 사용자 경험을 향상
controls - 재생 컨트롤 표시 설정
autoplay - 자동 재생 설정
loop - 반복 설정
```

---

- 3. HTML 오디오(Audio) 요소

```
음악파일을 표시한다.
```

```html
[사용예시]

<figure style="margin: 0;">
  <img
    src="media/audio/tobu-Itro_Cloud9--cover.jpg"
    alt="Cloud9 - Tobu & Itro"
    width="300"
    height="300"
  />
  <figcaption>
    <audio src="media/audio/tobu-Itro_Cloud9.mp3" controls>
      <p>
        HTML <code>audio</code>요소를 지원하지 않는 구형 웹 브라우저를 사용
        중입니다.
        <a herf="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a
        >하세요.
      </p>
    </audio>
  </figcaption>
</figure>
```

---

- 4. HTML 트랙(Track) 요소

```
비디오/오디오 재생 시 자막을 표시한다.
* vtt : video text track의 약자 (각각의 자막에 인덱스를 가지고 있다.)
```

```html
[사용예시]

<video src="videofile.mp4" poster="posterimage.jpg">
  <track
    kind="subtitles"
    src="videofile.ko.vtt"
    srclang="ko"
    label="한국어"
    default
  />
  <track kind="subtitles" src="videofile.en.vtt" srclang="en" label="English" />
</video>
```

---

- 5. HTML 인라인 프레임(iframe) 요소

```
다른 html 페이지를 현재 페이지에 포함시키는 중첩된 브라우저 컨텍스트를 나타낸다.
iframe 은 인라인 프레임으로, html 문서에 외부의 html 페이지들을 포함시킬 수 있다.
```

```
[속성]
src - 프레임 소스 설정
width - 프레임 너비 설정
height - 프레임 높이 설정
allowfullscreen - 프레임 전체 화면 설정
```

---

- 6. HTML 이미지 맵(map) 요소

클릭으로 연결 가능한 링크 주소를 만들고 싶다면 이미지 맵을 사용한다.

```
이미지 맵(클릭 가능한 링크 영역)을 정의하기 위해 <area />와 함께 한다. map은
눈에 보이지 않는다.
+ <area /> 요소 : 이미지의 핫스팟 지역 정의, 하이퍼링크
설정. (map 내부에서만 사용 가능)

[속성]
shape - 핫스팟 모양 설정
coords - 모양의 좌표 값 설정
href - 하이퍼링크 주소 설정
target - 새 창 (탭) 열림 설정
alt - 대체 텍스트 설정
hreflang - 연결된 페이지의 언어 속성 설정
download - canvas 데이터 다운로드 설정
```

```html
[사용예시]

<img src="products-map.jpg" alt="제품모음" usemap="#products-map" /><map
  name="products-map"
>
  <area shape="circle" coords="200,250,25" href="another.html" />
</map>
```

---

- 7. HTML 확장 가능한 벡터그래픽(SVG) 요소

```
확장 가능한 벡터 그래픽(SVG)는 2차원의 벡터 그래픽을 기술하기 위한 XML 마크업 언어이다.
```

```html
[예시 코드]
<img src="svgfile.svg" alt="SVG File" />
: img로 불러온 svg 파일은 css로 스타일을 지정해줄 수 없음

<svg widht="150" height="150" viewBox="0 0 150 150">
  <circle r="50" cx="75" fill="#333" stroke="#900" stroke-widht="4" />
</svg>
```

---

- ## 200818 화요일

## 박스 모델

- 1. block vs inline vs inline-block 요소간 특성에 대한 이해
- 2. margin vs border vs padding vs content 박스 간 특성에 대한 이해
- 3. dimension & box-sizing & overflow 속성 사용에 대한 이해

```
블록 박스 :
블록 박스는 다른 블록 박스에 포함되거나, 포함할 수 있고 너비 (widht) / 높이 (height)설정이 가능합니다. 내부에 콘텐츠를 포함하지 않을 경우 높이는 0 입니다.

```

```
인라인 박스:
인라인 박스는 다른 인라인 박스에 포함되거나, 포함할 수 있지만, 블록 요소는 포함할 수 없습니다. 너비(width)와 높이 (he8ght) 설정이 가능하지 않습니다. 내부에 포함한 콘텐츠 만큼 높이와 너비를 가지게 됩니다.
```

```
인라인 블록 박스:
인라인 블록 박스는 기본적으로 인라인처럼 화면에 렌더링되지만, 블록 박스처럼 너비(width) / 높이(height) 설정이 가능 합니다. (<img>,<input>,<button> 등)
```

- margin-box (외부 공간 박스) > border-box (테두리 공간 박스) > padding-box (내부 공간 박스) > content-box (콘텐츠 공간 박스) 로 감싸고 있다.

- 인라인 박스는 좌/우 방향으로 마진, 패딩 공간을 설정할 수 있으나, 상/하 방향으로는 공간이 설정되지 않습니다.

- 시계 방향으로 top, right, bottom, left 순으로 구조되어 있다.

```
Dimension 설정:
블록 박스, 인라인 블록 박스는 "수치 설정을 통해 박스의 크기를 변경할 수 있습니다."

1. widht - 박스 너비
2. height - 박스 높이
3. min-widht - 박스 최소 너비
4. min-height - 박스 최소 높이
5. max-widht - 박스 최대 너비
6. max-height - 박스 최대 높이
```

```
Overflow 설정:
부모 박스의 영역을 자식 박스가 넘어서게 될 때 화면에 어떻게 렌더링 할 지를 결정하게 됩니다.

1. auto - 자동 값을 사용할 경우, 흐름이 넘치면 x/y 축 모두 스크롤 바가 자동으로 생깁니다. 흐름이 넘치지 않으면 스크롤 바는 보이지 않습니다.

2. visible - 흐름이 넘친 영역이 모두 보여집니다.

3. hidden - 흐름이 넘친 영역이 모두 감춰집니다.

4. scroll - x/y 축 스크롤이 무조건 보입니다.
```

---

- ## 200819 수요일

## 인터랙티브 요소

```
<details> 요소 :
- 디스클로저 위젯으로 정보를 감추거나, 펼쳐서 보여준다. 모든 정보를
  일시에 공개하지 않고 사용자의 요구에 맞춰 정보를 공개할 수 있다.(화면의
  복잡함을 줄임) 아코디언 컴포넌트와 비슷하게 작동한다.
  참고로 각주(footnote)에는 적합하지 않다.

  [속성]
  open- 페이지 로딩 시, 위젯을 펼쳐
  표시하도록 설정

  [사용예시]
  <details open>
    ...
  </details>
```

```
<summary> 요소 :
- <details> 요소의 레이블/캡션(제목), 서머리(요약) 등을 표시한다. 폼<fieldset> 요소의 제목을 <legend>가 표시하듯 비슷하다.
```

```
<dialog> 요소 :
사용자의 결정 또는 정보 입력을 요구하는 컴포넌트를 말함.
'모달 윈도우' 또는 '대화상자'로도 불린다.
-
```

## 스크립팅 요소들

- [script] 요소 :
  JavaScript 코드 또는 파일을 HTML 문서에 작성하거나, 연결할 때 사용한다.

```
[속성]

1. src -
2. type -
3. async -
4. defer -
```

- [nonscript] 요소 :  
  사용자의 웹 브라우저 환경에서 스크립트를 지원되지 않거나, 스크립트가 꺼져있는 경우, 문서에 표시될 문구를 삽입한다.

- [canvas] 요소 :  
   자바스크립트를 사용하여 그래픽(비트맵)을 그릴 때 사용한다.
  canvas 요소로부터 2D 또는 WebGL 컨텍스트 객체를 추출해 그래픽을 그릴 수 있다.

## 리스트(Lists)

- 비 순차 목록: Unordered List  
  ul 요소는 Unordered List의 줄임 말로, 말 그대로 Un-order 된, 순서가 없는 목록 요소입니다.

  ol과 거의 동일하여, ul 역시 블럭요소이지만 자식으로 li 요소만 포함할 수 있습니다. 당연하지만, ol에서 썼던 start나 reversed 같은 속성은 사용할 수 없습니다. 보통 메인 메뉴 같은 요소들도 ul 요소로 마크 업을 하기 때문에, 자주 사용하게 되는 요소 중 하나 입니다.

* 순차 목록: Ordered List  
  ol 요소는 Ordered List의 줄임 말로, 순서가 있는 목록입니다. ol 요소 안에 li(list 의 줄임) 요소로 목록 항목을 표현합니다.

  이 ol 요소로 순위나, 레시피 등 순서가 있는 부분을 나타낼 수 있습니다.

- 설명 목록: Definition List  
  dl 요소는 ol과 ul이 li 요소만 자식으로 놓듯이, dt와 dd 요소만을 자식으로 둘 수 있습니다. 그리고 주의할 점은 dt는 인라인 요소이며, dd는 블럭 요소입니다. 때문에 dt 안에 블럭 요소를 넣으시면 안됩니다.

## 배경 스타일링

요소의 배경(background)은 요소의 content-box, padding-box, border-box 아래에 있는 영역입니다. (margin-box 제외)  
모던 브라우저에서는 배경을 차지하는 영역을 background-clip 속성을 사용하여 변경할 수 있습니다.

- 배경 색: background-color  
   배경색을 설정합니다.

- 배경 이미지: background-image  
  요소의 배경에 표시할 배경 이미지를 지정합니다. 이미지 또는 그래디언트 이미지를 사용합니다.

- 배경 위치: background-position  
  배경이 요소 배경 안에 표시되어야 하는 위치를 설정합니다.

- 배경 고정: background-attachment  
  내용이 스크롤 될 때 요소의 배경 동작을 설정합니다.

- 배경 반복: background-repeat  
  배경을 반복할지 여부를 설정합니다.

- 배경 크기: background-size  
  배경 이미지의 크기를 동적으로 조정할 수 있습니다.

- background  
  배경 속성을 모아 작성하는 속기법입니다.

- 배경 기준: background-origin

- 배경 클리핑: background-clip

---

- ## 200820 목요일

## 유저 인터랙션 속성

- [ hidden 속성 ] :  
  모든 html 요소들은 hidden 속성을 가질 수 있으며, 요소에 설정되면 요소가 아직 페이지의 현재 상태와 직접적으로 관련이 없거나 페이지의 다른 부분에서 내용을 재사용하도록 선언하는 데 사용된다.  
  브라우저는 hidden 속성이 설정된 요소를 화면에 렌더링하지 않는다.

```html
- 주의할 점 : 이 속성은 일반적으로 CSS를 사용해 구현 되므로 CSS 속성에 의해
재정의 될 수 있음에 주의해야 합니다. 즉, hidden 속성이 적용된 요소에 display:
block 스타일을 설정하면 화면에 렌더링 됩니다.

<div hidden style="display: block">
  hidden 속성이 설정 되었지만, 이 콘텐츠는 화면에 렌더링 됩니다.
</div>

- style="display: none;"만 먹이는 것은 그냥 보이지 않는다는 스타일을 지정해서
전체 마크업의 맥락에 포함시키는 것이고 따라서 예컨대 스크린 리더가 내용을
읽어주는 등 다른 미디어에서 처리될 수 있습니다. hidden(="hidden") 속성을 주는
것은 전체 마크업의 맥락에서 배제해 버리는 차원이라고 볼 수 있다.
```

- [ tabindex 속성 ] :  
  요소를 키보드로 탐색할 수 있도록 설정하거나, 제외 또는 순서대로 탐색할 수 있도록 설정할 수 있다.  
  "(Tab)이동" 이란 용어는 순차적 포커스 탐색을 사용하여 포커스 가능(Focusable) 요소 사이를 이동하는 것을 의미한다."

  - 폼 컨트롤 요소들 : input, button, textarea, select 등
  - href 속성을 가진 요소들 : a, area
  - controls 속성을 가진 요소들 : video, audio

- [ accesskey 속성 ] :  
  모든 html 요소는 accesskey 속성을 가질 수 있다. 속성 같은 키보드 단축키로 설정된다.  
  하지만 accesskey 속성의 단축키는 브라우저와 운영체계 플랫폼에 의존하고 있어 운영체제마다 사용자 경험이 달라진다.  
  쉽게말해 Windows 사용자와 Mac OSX 사용자가 사용하는 단축키는 달라진다.

- [ contenteditable 속성 ] :  
  contenteditable 속성이 설정된 요소는 사용자가 직접 편집할 수 있도록 만들어 준다. 값이 true 또는 빈 문자열("")일 경우 편집 허용.
  값이 false 일 경우 편집을 허용하지 않음.

- [ draggable 속성 ] :  
  모든 html 요소는 draggable 속성을 가질 수 있다.
  - 값이 true 일 경우 드래그(Drag) 가능.
  - 값이 false 또는 빈 문자열("")일 경우 드래그 불가능.

## 플로팅 레이아웃

CSS 레이아웃 :  
대표적인 레이아웃 테크닉인 플로팅(floating)과 포지셔닝(positioning), 그리고 플렉스박스(Flexbox), 그리드(Grid)가 있다.

```
일반적인 레이아웃 흐름 (Nomal layout flow) :

html이 기본적으로 화면에 렌더링하는 것을 말합니다.
마크업 순서대로 위에서 부터 아래 방향으로 나열됩니다. (css 레이아웃 미반영)
```

```
플로팅 (Floating) 레이아웃
float 속성을 사용해 박스를 왼쪽(left) 또는 오른쪽(right) 으로 "부유"시키는
레이아웃 기법입니다. 설정 가능한 값은 다음과 같습니다.

    + none
    + left
    + right
```

```css
[예제]
.css{
    float: left;
    height: 70px
    margin-right: 5%
    margin-bottom: 5%
    background: #f4f4f4
}
.css_2{
    widht:45%
}
```

- 부모요소는 부유된 자식 요소를 감싸지 못 한다.  
  그로 인해 [ clear: left;, right; both; 속성 ], 또는 [overflow: auto;, hidden;] 을 사용하여 부모 요소가 자식의 높이값을 감싸준다.

---

- ## 200821 금요일

## 문서 메타데이터 요소들

- [ head ] 요소 :  
  문서의 제목과 스타일시트, 스크립트 링크 또는 선언을 포함하는 문서의 일반적인 정보(메타데이터)를 제공한다.  
  대부분 브라우저는 마크업에서 head 요소가 생략될 경우, 자동으로 head 요소를 생성하지만, 일부는 그렇지 않다.

- [title] 요소 :  
  브라우저의 타이틀 바 (title bar)나 페이지 탭에 보여지는 문서의 제목을 정의.  
  텍스트만 포함할 수 있으며 포함된 태그들은 해석되지 않음.

- [ meta ] 요소 :  
  다른 메타 요소들(title, base, link, style)로 나타낼 수 없는 메타데이터를 정의할 때 사용.

```
[ 메타데이터의 종류 ]
- charset이 설정된 경우 :
charset 선언. 즉 웹페이지를 작성하는 일련의 형식에 사용되는 문자 인코딩(charset)에 대한 설정.
이 속성보다 요소의 lang 속성이 우선하여 적용됨. (즉, 덮어쓰기 됨. 예: <div lang="fr">)

- http-equib 속성이 설정된 경우 :
pragma 지시어(Directibe)로 일반적으로 웹서버가 제공하는 웹페이지가 어떻게 제공되어야 하는지에 대한 정보를 제공.

- name 속성이 설정된 경우 :
문서 수준 메타 데이터의 이름을 정의하며,  content 속성  값을 통해 설정.

```

```
[ 속성 ]

1. charset

2. http-equiv

3. content :
이 속성은 컨텍스트에 따라 http-equiv 또는 name 속성과 연결된 값을 제공.

4. name :

  - application name :
  웹 페이지에서 실행중인 웹 애플리케이션 이름 정의.
  간단한 웹 페이지는 application-name 메타를 정의해서는 안됨.
  - description :
  페이지의 내용에 대한 짧고 정확한 요약을 설정.
  - keywords :
  쉼표로 구분된 문자열로 페이지의 내용과 관련된 키워드를 설정.
  - author :
  문서 작성자의 이름을 정의.
  -robots :
  검색 로봇이 웹 페이지를 크롤링하는 동작에 대한 정의.
    - index
    - noindex
    - follow
    - nofollow
    - noarchive
    - nosnippet
    - noimageindex
  - viewport :
  (비표준) 초기 viewport 크기 설정에 관한 힌트를 제공.
  이 속성은 몇개의 모바일 디바이스에 의해서만 사용됨.
    - widht
    - height
    - initial-scale
    - maximum-scale
    - minimum-scale
    - user-scalable
```

- [ link ] 요소 :  
  현재 문서와 외부 리소스와의 관계(relation)를 명시.  
  이 요소는 스타일시트를 링크 하는데 가장 많이 사용됨.

```
[ 속성 ]
- rel : 문서와의 관계 명시.
- type : 링크된 리소스 MIME 타입 정의. (기본적용 : text/css)
- href : 링크된 리소스 URL 설정.
- hreflang : 링크된 리소스의 언어 설정.
- media : 링크된 리소스가 적용될 미디어(media)를 설정.
```

- [ style ] 요소 :  
  문서나 문서 일부에 대한 스타일 정보를 포함.  
  기본적으로 CSS 언어가 사용됨.

  ```
  [ 속성 ]
  - type
  - media
  - scoped
  - title
  - disabled
  ```

- [ base ] 요소 :  
  문서에 포함된 모든 상대 URL들의 기준 URL을 나타냄.  
  한 문서에 하나의 base 요소만 존재해야 함.

  ## 포지셔닝 레이아웃

  레이아웃 디자인

  - 포지셔닝(Positioning) 레이아웃  
    포지셔닝은 웹브라우저가 렌더링하는 기본 레이아웃 흐름(Normal Layout Flow)을 재정의하여 흥미로운 효과를 만들어 낼 때 사용합니다.  
    예를 들어 기본 레이아웃 흐름에서 레이아웃 내부 일부 요소의 위치를 조정하려면 포지셔닝을 사용하여 조정할 수 있습니다.

    페이지의 다른 부분 위에 떠있는 UI 요소를 만들고 싶거나, 페이지의 스크롤과 상관없이 항상 브라우저창의 동일한 위치에 자리한 UI 요소를 만들고자 한다면 포지셔닝을 사용합니다.

    - 포지셔닝 레이아웃 유형

    1. 정적(static)위치
    2. 상대(relative)위치
    3. 절대(absolute)위치
    4. 고정(fixed)위치
    5. 달라붙는(sticky)위치
