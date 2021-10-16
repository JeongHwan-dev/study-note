# CSS 속성 선언 순서

**CSS 속성 선언 순서**를 정해놓으면 팀 프로젝트 시 여러 명이 작업할 때 CSS가 통일성을 가져서 가독성도 좋고 운영 유지에도 좋습니다.

```CSS
#CSS-property-order {

  /* 1. 레이아웃 */
  display: ;
  visibility: ;
  opacity: ;
  overflow: ;
  float: ;
  clear: ;

  position: ;
  top: ;
  right: ;
  bottom: ;
  left: ;
  z-index: ;

  /* 2. BOX */
  width: ;
  min-width: ;
  max-width: ;

  height: ;
  min-height: ;
  max-height: ;

  margin: ;
  margin-top: ;
  margin-right: ;
  margin-bottom: ;
  margin-left: ;

  padding: ;
  padding-top: ;
  padding-right: ;
  padding-bottom: ;
  padding-left: ;

  outline: ;

  border: ;
  border-top: ;
  border-right: ;
  border-bottom: ;
  border-left: ;

  border-width: ;
  border-top-width: ;
  border-right-width: ;
  border-bottom-width: ;
  border-left-width: ;

  border-style: ;
  border-top-style: ;
  border-right-style: ;
  border-bottom-style: ;
  border-left-style: ;

  border-color: ;
  border-top-color: ;
  border-right-color: ;
  border-bottom-color: ;
  border-left-color: ;

  /* 3. 배경 */
  background: ;
  background-color: ;
  background-image: ;
  background-repeat: ;
  background-position: ;

  cursor: ;
  list-style: ;
  caption-side: ;

  /* 4. 폰트 */
  font: ;
  font-family: ;
  font-size: ;
  font-weight: ;

  line-height: ;
  color: ;
  word-spacing: ;
  letter-spacing: ;
  white-space: ;

  text-align: ;
  text-indent: ;
  text-transform: ;
  text-decoration: ;

  /* 5. 기타 */
  ...

}
```

> **속성 선언 기준**  
> `1: 레이아웃 ➜ 2: BOX ➜ 3: 배경 ➜ 4: 폰트 ➜ 5: 기타`

<br />

## 참고 자료

> https://github.com/brandon-rhodes/Concentric-CSS

> https://gist.github.com/awkale/ad46e2ade70e833fa178

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
