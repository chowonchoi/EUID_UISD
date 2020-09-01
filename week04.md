<!-- @format -->

[back](README.md)

# 4주차 학습 내용

## 200901 월요일

## 플렉시블 레이아웃

### flex box

flexbox는 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는 CSS3의 새로운 레이아웃 방식이다.  
flexbox의 장점을 한 마디로 표현하면 '복잡한 계산 없이 요소의 크기와 순서를 유연하게 배치할 수 있다'라고 할 수 있다.  
정렬, 방향, 순서, 크기 등을 유연하게 조절할 수 있기 때문에 별도의 분기 처리를 줄일 수 있고, CSS만으로 다양한 레이아웃을 구현할 수 있다.

**flex 컨테이너 VS flex 아이템**  
flexbox는 복수의 자식 요소인 flex item과 그 상위 부모 요소인 flex container로 구성된다.  
display: flex 속성이 적용된 요소는 flex container가 되고, flex container의 자식 요소는 flex item이 된다.

```
flex container 속성:
flex-direction, flex-wrap, justify-content, align-items, align-content
```

```
flex item 속성:
flex, flex-grow, flex-shrink, flex-basis, order
```

```css
/* flex 아이템을 행으로 표현 */
display: flex;
flex-direction: row;
```

```css
/* flex 아이템을 열로 표현 */
display: flex;
flex-direction: column;
```

**flex 컨테이너 플로우 축(axis)**

**justify-content 설정**  
주축과 교차축에 대한 정렬
**flex-direction 설정**

```css
display: flex;
flex-direction: row/row-reverse/column/column-reverse
justify-content: flex-start/center/flex-end
space-between/space-around/space-evenly
```

**flex-wrap 설정**  
flex-item 요소들이 강제로 한줄에 배치되게 할 것인지, 또는 가능한 영역 내에서 벗어나지 않고 여러행으로 나누어 표현 할 것인지 결정하는 속성입니다.  
 만약 영역 내에서 벗어나지 못하게 설정한다면, 동시에 요소의 방향 축을 결정할 수 있습니다.

**가운데 배치 설정**
justify-content: center / align-items: center

**아이템 순서 설정**

- order  
  같은 container 안 플렉스 아이템의 나열 순서 지정.
  ※ 번호가 같을 경우, 소스 코드 나열 순서대로 정렬됨.
