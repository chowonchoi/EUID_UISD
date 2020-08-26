<!-- @format -->

[back](README.md)

# 3주차 학습 내용

- ## 200824 월요일

## [ 2D 트랜스 폼 ]

### CSS transform 속성(properties)

CSS trans form 에서 가장 중요한 속성은 transform과 transform-origin 이다.

- **transform-orign**  
   원점의 위치를 지정한다. 기본값은 엘리먼트의 왼쪽(left), 위(top)이지만, 수정이 가능하다.  
   회전(rotation), 확대/축소(scaling), 비틀기(skewing) 같이 한 점을 기준으로 수행되는 변환에 대해서 이 속성을 지정할 수 있다.

- **transform**  
   엘리먼트(element)에 적용된 변환(transform)을 지정한다.  
   몇 가지 변환을 공백으로 구분하여 순서대로 지정해 놓음으로써, 여러가지 변환을 동시에 적용할 수 있다.

### CSS 트랜지션

스펙 꾸러미의 일부인 속SS 트랜지션(transitions)은 CSS 속성을 변경할 때 애니메이션 속도를 조절하는 방법을 제공합니다.  
속성 변경이 즉시 영향을 미치게 하는 대신, 그 속성의 변화가 일정 기간에 걸쳐 일어나도록 할 수 있습니다.  
예를 들어, 어떤 요소의 색상을 흰색에서 검은색으로 변경한다면, 변화는 대개 즉시 일어납니다.  
CSS 트랜지션을 이용하면, 모두 커스터마이즈 가능한 어떤 가속도 곡선을 따르는 시간 주기마다 변화가 일어납니다.

CSS transitions는 (**명시적으로 목록을 작성해서**) 어떤 속성을 움직이게 할지,  
(**딜레이를 설정해서**) 언제 애니메이션이 시작할지,  
(**지속시간을 설정해서**) 트랜지션을 얼마나 지속할지,  
그리고 (**예를 들면, 선형이거나 초기 빠름, 종료 느림과 같은 타이밍 함수를 정의해서**) 어떻게 트랜지션을 실행하는지 결정하게 합니다.

```
[속성]

transition-property  : 트랜지션 속성
transition-duration  : 트랜지션 시간
transition-timing-function  : 트랜지션 타이밍 함수
transition-delay  : 트랜지션 지연시간
transition  : 트랜지션 속기형
```

### 3D 트랜스폼

CSS 속성을 공간에 지정하는 건 조금 까다롭다.  
먼저 시점을 정함으로서 3D 공간을 구성하고, 2D 엘리먼트가 그 공간 안에서 어떻게 동작할지를 설정해야한다.

1. 시점(perspective) 정하기  
   먼저 정해야할 건 시점이다.  
   시점 때문에 3차원 공간의 느낌이 난다.  
   엘리먼트가 사용자로부터 멀어질수록 작아진다.  
   멀어질수록 얼마나 빨리 작아질지는 **perspective** 속성을 통해 지정한다.  
   작은 값을 지정할 수록 원근감이 깊어진다.

---

- ## 200825 화요일

## [ 테이블 요소 ]

1. table 요소 :  
   테이블 몸체에 해당되며, 행(row)/열(column) 및 셀(cell)을 포함한다.  
   복잡한 내용을 x, y 축에 따라 이해하기 쉽게 데이터를 구조화하는데 테이블을 사용한다.  
   가장 좋은 테이블 디자인은 최대한 단순하게 표를 구성하는 것이다.  
   테이블 내 테이블을 중첩해서는 안된다.  
   테이블 레이아웃 (배치) 목적으로 사용해서는 안된다.  
   border 속성을 사용해 테두리를 그릴 수 있다. (CSS로 대체하는 것이 좋다.)

2. caption 요소 :  
   테이블의 제목을 명시적으로 제공하며, 제작자는 표이 내용을 이해할 수 있도록 정보를 제공해야 함.  
   테이블 내용이 복잡해 설명이 필요하다면 아래 나열된 방법 중 하나를 선택해 기술해야 한다.

```
   [설명(summary)을 추가하는 방법]

   1. aria-describedby 속성을 사용해 설명 단락(paragraph)을 연결
   2. < figure > 요소에 aria-labelledby 속성을 사용해 제목(caption)을 연결
```

3. tr 요소 :  
   테이블의 행(row)을 말하며 내부에 셀 제목(header), 셀 내용(data)을 포함한다.

4. th 요소 :  
   테이블 셀 제목(header cell in a table)으로 **행(tr) 내부에 포함되어야 한다.**

   ```
   [속성]

   1. scope: 행(row) 또는 열(col), 행그룹(rowgroup), 열그룹(colgroup)의 제목임을 명시
   2. abbr: 제목이 길어 축약(Abbreviation)이 필요할 때 사용
   3. colspan: 열(column)을 그룹 지을 때 사용
   4. rowspan: 행(row)을 그룹 지을 때 사용
   ```

5. td 요소 :  
   테이블 셀 내용 (data cell in a table)으로 행(tr) 내부에 포함되어야 한다.

   ```
   [속성]
   1. colspan: 열(column)을 그룹 지을 때 사용
   2. rowspan: 행(row)을 그룹 지을 때 사용
   3. headers: 셀 제목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용
   ```

6. thead 요소 :  
   테이블 행 블록 (row block) 내에 제목 열 그룹(column headers)으로 구성할 경우 사용된다.  
   선택적(option)으로 사용한다. (필수 아님)

7. tbody 요소 :  
   행 블록 내에 테이블 데이터로 구성할 때 사용한다.  
   선택적(option)으로 사용한다. (필수 아님)

8. tfoot 요소 :  
   행 블록 내에 열 요약(column summaries)로 구성할 때 사용한다.  
   선택적(option)으로 사용한다. (필수 아님)

9. col 요소 :  
   테이블 열(column)을 하나 이상 묶고자 할 때 사용한다.  
   일반적으로 colgroup 요소 내부에 포함시킨다.  
   선택적(option)으로 사용한다. (필수 아님)

```
[속성]
span: 열 묶음 개수 설정
```

10. colgroup 요소 :  
    테이블 열(column) 그룹을 만들고자 할 때 사용한다.  
    내부에 col 요소를 포함하거나, 포함하지 않을 수 있다.  
    선택적(option)으로 사용한다. (필수 아님)

```
[속성]
span: colgroup 요소가 col을 포함하지 않을 경우, 열 묶음 개수 설정
```

## 애니메이션

CSS3 애니메이션은 엘리먼트에 적용되는 CSS 스타일을 다른 CSS 스타일로 부드럽게 전환시켜 줍니다.  
애니메이션은 애니메이션을 나타내는 CSS 스타일과 애니메이션의 중간 상태를 나타내는 키프레임들로 이루어집니다.

CSS 애니메이션은 기존에 사용되던 스크립트를 이용한 애니메이션보다 다음 세 가지 이유에서 이점을 가집니다.

```
1. 자바스크립트를 모르더라도 간단하게 애니메이션을 만들 수 있습니다.

2. 자바스크립트를 이용한 애니메이션은 잘 만들어졌더라도 성능이 좋지 못할 때가 있습니다.
CSS 애니메이션은 frame-skipping 같은 여러 기술을 이용하여 최대한 부드럽게 렌더링됩니다.

3. 브라우저는 애니메이션의 성능을 효율적으로 최적화할 수 있습니다.
예를 들어 현재 안 보이는 엘리먼트에 대한 애니메이션은 업데이트 주기를 줄여 부하를 최소화할 수 있습니다.

```

```
애니메이션 (Animation)
CSS 애니메이션을 만드려면 animation 속성과 이 속성의 하위 속성을 지정한다.
애니메이션의 총 시간과 반복 여부등을 지정할 수 있습니다.
이 속성은 애니메이션의 중간상태를 기술하지 않는다.
애니메이션의 중간 상태는 아래에서 다룰 @keyframes 규칙을 이용하여 기술한다.

1. animation-name : 애니메이션 이름
2. animation-duration : 애니메이션 시간
3. animation-timing-function : 애니메이션 타이밍 함수
4. animation-delay : 애니메이션 지연시간
5. animation-direction : 애니메이션 종료 후, 진행(순/역)방향
6. animation-iteration-count : 애니메이션 반복 횟수 (infinite: 무한반복)
7. animation-play-state : 애니메이션 재생/일시정지 설정
8. animation-fill-mode : 애니메이션 시작 전/종료 후 키프레임 설정 (forwards: 유지)
9. animation : 애니메이션 속기형
```

**문법(Syntax)**

- 값(Values)  
  normal :  
  애니메이션은 매 사이클마다 정방향으로 재생됩니다.  
  즉, 순환 할 때 마다 애니메이션이 시작 상태로 재설정되고 다시 시작됩니다.  
  이 것은 기본 값입니다.

- reverse  
  애니메이션은 매 사이클마다 역방향으로 재생됩니다.  
  즉, 순환 할 때마다 애니메이션이 종료 상태로 재설정되고 다시 시작됩니다.  
  애니메이션 단계가 거꾸로 수행되고 타이밍 기능 또한 반대로 됩니다.  
  예를 들어, ease-in 타이밍 기능은 ease-out 형태로 변경됩니다.

- alternate  
  애니메이션은 매 사이클마다 각 주기의 방향을 뒤집으며, 첫 번째 반복은 정방향으로 진행됩니다.  
  사이클이 짝수인지 홀수인지를 결정하는 카운트가 하나에서 시작됩니다.

- alternate-reverse  
  애니메이션은 매 사이클마다 각 주기의 방향을 뒤집으며, 첫 번째 반복은 역방향으로 진행됩니다.  
  사이클이 짝수인지 홀수인지를 결정하는 카운트가 하나에서 시작됩니다.

- none  
  애니메이션은 실행되지 않을 때 대상에 스타일을 적용하지 않습니다.요소는 대신 적용된 다른 CSS 규칙을 사용하여표시됩니다. 이 것은 기본값입니다.

- forwards  
  대상은 실행 된 애니메이션의 마지막 keyframe에 의해 설정된 계산 된 값을 유지합니다.  
  마지막 키 프레임은 animation-direction 및 animation-iteration-count 의 값에 따라 다릅니다.

- backwards  
  애니메이션은 대상에 적용되는 즉시 첫 번째 관련 keyframe에 정의 된 값을 적용하고 animation-delay 기간 동안 이 값을 유지합니다.  
  첫 번째 관련 키프레임은 animation-direction의 값에 따라 다릅니다.

- both  
  애니메이션은 앞뒤 양쪽 모두의 규칙을 따르므로 애니메이션 속성이 양방향으로 확장됩니다.

---

- ## 200826 수요일

## 그레디언트

CSS 그레이디언트는 < image > 자료형의 특별한 종류인 < gradient >로 나타내며 두 개 이상의 색 간의 점진적 전환을 표현합니다. 그레이디언트에는 선형(linear-gradient() 함수), 방사형(radial-gradient 함수), 각진 원형(conic-gradient 함수) 세 종류가 있으며, 각각의 변형본으로 계속해서 반복하는 repeating-linear-gradient, repeating-radial-gradient, repeating-conic-gradient 함수도 있습니다.

그레이디언트는 배경처럼 < image >를 사용하는 곳에는 어디에나 적용할 수 있습니다. 그레이디언트는 동적으로 생성하므로, 비슷한 효과를 보기 위해 래스터 이미지를 사용하는 방식을 사용하지 않아도 됩니다. 또한 브라우저가 직접 생성하므로 확대했을 때 래스터 이미지보다 좋은 품질을 보이며 크기 조절도 즉시 가능합니다.

## 1.선형(Linear) 그레디언트 :

가장 기본적인 그레이디언트 종류를 생성하기 위해서는 두 가지의 색만 지정하면 됩니다. 각각의 색을 "색상 정지점"이라고 부릅니다. 최소 두 가지가 필요하지만, 제한 없이 원하는 만큼 추가할 수 있습니다.

**[예시]**

```css
.simple-linear {
  background: linear-gradient(blue, pink);
}
```

**[방향전환]**  
기본적으로, 선형 그레이디언트는 위에서 아래로 진행합니다. 그러나 방향을 지정함으로써 그레이디언트를 회전할 수 있습니다.

```css
.horizontal-gradient {
  background: linear-gradient(to right, blue, pink);
}
```

**[대각선 그레디언트]**  
그레디언트가 한쪽 모서리에서 다른 쪽 모서리를 잇는 대각선 방향으로 진행하도록 할 수 있습니다.

```css
.diagonal-gradient {
  background: linear-gradient(to bottom right, blue, pink);
}
```

**[각도 사용]**  
더 정밀하게 방향을 지정하고 싶다면 특정 각도를 지정할 수 있습니다.  
각도를 사용할 때 0deg 는 아래쪽에서 위쪽으로 진행하는 선형 그레이디언트를, 90deg 는 왼쪽에서 오른쪽으로, 등등 시계 방향으로 회전합니다. 음의 각도는 시계 반대 방향으로 회전합니다.

```css
.angled-gradient {
  background: linear-gradient(70deg, blue, pink);
}
```

## 원형(Radial) 그레디언트

**[Simple gradient]**

```css
.radial-gradient {
  background-image: radial-gradient(cyan 0%, transparent 20%, salmon 40%);
}
```

**[Non-centered gradient]**

```css
.radial-gradient {
  background-image: radial-gradient(
    farthest-corner at 40px 40px,
    #f35 0%,
    #43e 100%
  );
}
```

## border-radius :

    border-radius 속성은 요소 테두리 경계의 꼭짓점을 둥글게 만듭니다. 하나의 값을 사용해 원형 꼭짓점을, 두 개의 값을 사용해 타원형 꼭짓점을 적용할 수 있습니다.
    꼭짓점 반경은 요소의 테두리 존재 여부와는 별개로 전체 background에 적용됩니다. 원형 꼭짓점으로 인해 배경이 잘리는 지점은 background-clip 속성이 지정합니다.
    border-collapse의 값이 collapse인 표 요소는 border-radius 속성의 영향을 받지 않습니다.

**[예제]**

```css
border-radius: 30px;
border-radius: 25% 10%;
border-radius: 10% 30% 50% 70%;
border-radius: 10% / 50%;
border-radius: 10px 100px / 120px;
border-radius: 50% 20% / 10% 40%;
```

**[값]**

```
- radius:
  테두리의 각 꼭짓점 반지름을 나타내는 < length > 또는 < percentage >. 한 개 값 구문에서만 사용합니다.

- top-left-and-bottom-right:
왼쪽 위와 오른쪽 아래 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 두 개 값 구문에서만 사용합니다.

- top-right-and-bottom-left:
오른쪽 위와 왼쪽 아래 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 두 개 또는 세 개 값 구문에서만 사용합니다.

- top-left:
왼쪽 위 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 세 개 또는 네 개 값 구문에서만 사용합니다.

- top-right:
오른쪽 위 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 네 개 값 구문에서만 사용합니다.

- bottom-right:
오른쪽 아래 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 네 개 값 구문에서만 사용합니다.

- bottom-left:
왼쪽 아래 꼭짓점의 반지름을 나타내는 < length > 또는 < percentage >. 네 개 값 구문에서만 사용합니다.
```

- length:

길이 값을 사용해 원의 반지름 또는 타원의 짧은반지름과 긴반지름을 지정합니다. 음의 값은 유효하지 않습니다.

- percentage:

백분율 값을 사용해 원의 반지름 또는 타원의 짧은반지름과 긴반지름을 지정합니다. 가로축 값은 요소 박스의 너비에 대한 백분율이고, 세로축 값은 박스의 높이에 대한 백분율입니다. 음의 값은 유효하지 않습니다.

## box-shadow

box-shadow CSS 속성은 요소의 테두리를 감싼 그림자 효과를 추가합니다. 쉼표로 구문해서 여러 그림자 효과를 입힐 수 있습니다. 박스 그림자는 요소에서의 수평수직 거리(오프셋), 흐릿함과 확산 정도, 색상으로 이루어집니다.

box-shadow 속성은 거의 모든 요소의 테두리에서 그림자를 드리울 수 있도록 도와줍니다. border-radius가 요소에 함께 적용됐다면 박스 그림자의 모서리도 똑같이 둥근 모서리를 갖게 됩니다. 여러 그림자의 z축 순서는 text-shadow와 동일하게 처음 그림자일수록 위로 올라옵니다.

박스 그림자 생성기는 상호작용형 도구로, 쉽게 box-shadow의 값을 생성할 수 있습니다.

**[예제]**

```css
box-shadow: 10px 5px 5px red;
box-shadow: 60px -16px teal;
box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, 0.2);
box-shadow: inset 5em 1em gold;
box-shadow: 3px 3px red, -1em 0 0.4em olive;
```

**[구문]**

```css
/* offset-x | offset-y | color */
box-shadow: 60px -16px teal;

/* offset-x | offset-y | blur-radius | color */
box-shadow: 10px 5px 5px black;

/* offset-x | offset-y | blur-radius | spread-radius | color */
box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);

/* inset | offset-x | offset-y | color */
box-shadow: inset 5em 1em gold;

/* Any number of shadows, separated by commas */
box-shadow: 3px 3px red, -1em 0 0.4em olive;

/* Global keywords */
box-shadow: inherit;
box-shadow: initial;
box-shadow: unset;
```

**하나의 box-shadow는 다음 구성요소로 지정할 수 있습니다.**

```
+ 두 개에서 네 개의 <length> 값.
  + 두 개의 값을 사용하면 <offset-x><offset-y>로 분석합니다.
  + 세 번째 값이 주어지면 <blur-radius>로 분석합니다.
  + 네 번째 값이 주어지면 <spread-radius>로 분석합니다.
+ 선택사항으로 inset 키워드.
+ 선택사항으로 <color> 값.
```

**[값]**

```
inset:
값을 지정하지 않으면(기본값) 요소가 공중에 떠있는 것처럼 밖에 드리우는 그림자가 됩니다.
inset 키워드가 존재하면 요소가 움푹 들어간 것처럼 그림자가 요소의 테두리 안, 배경색 위, 내부 콘텐츠 밑에 그려집니다.
```

```
<offset-x> <offset-y>:
그림자의 위치를 설정하는 두 개의 <length> 값입니다. <offset-x>는 수평 거리를 의미하며 음수 값은 그림자를 요소의 왼쪽에 표시합니다. <offset-y>는 수직 거리를 의미하며 음수 값은 그림자를 요소의 위쪽에 표시합니다. 가능한 단위는 <length>를 참고하세요.
두 값이 모두 0이면 그림자가 요소 바로 뒤쪽에 위치하며, <blur-radius> 또는 <spread-radius>가 존재하면 흐려지는 효과를 볼 수 있습니다.
```

```
<blur-radius>:
세 번째 <length> 값입니다. 크면 클 수록 그림자 테두리가 흐려지므로 크기는 더 커지고 색은 더 밝아집니다. 음수 값은 사용할 수 없습니다. 값을 설정하지 않으면 0이 되어 테두리가 선명해집니다. 명세는 흐림 효과의 지름을 어떻게 계산해야 하는지 정확한 알고리즘은 명시하지 않았지만 대신 다음과 같이 설명하고 있습니다.
```

```
<spread-radius>:
네 번째 <length> 값입니다. 양수 값은 그림자가 더 커지고 확산하며, 음수 값은 그림자가 줄어듭니다. 기본값은 0(그림자와 요소 크기 동일)입니다.
```

```
<color>:
가능한 키워드와 표기법은 <color>를 참고하세요.
기본값은 브라우저에 따라 다릅니다. 보통 color 속성의 값을 사용하지만, Safari는 투명한 그림자가 기본값입니다.
```

---
