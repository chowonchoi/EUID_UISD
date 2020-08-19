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
