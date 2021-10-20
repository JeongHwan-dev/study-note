# HTML 기타

## HTML의 DTD

**DTD**란 **Document Type Definition**으로 마크업 언어에서 문서 형식을 정의하는 것입니다.

```HTML
<!DOCTYPE html>
<!doctype HTML>
```

> HTML5 에서는 위와 같이 대소문자를 구분하지 않고 사용할 수 있습니다.

<br />

## `<img>` 요소의 필수 속성

```HTML
<img src="./images/sample.png" alt="sample" />
```

`<img>` 요소의 필수 속성으로 이미지 자원의 주소를 위한 **src 속성**과 이미지 대체 텍스트를 위한 **alt 속성** 두 개는 **필수 속성**입니다.

<br />

## `<button>` 요소의 type 속성을 생략하는 경우

`<button>` 요소는 type 속성에 따라서 다른 기능을 갖게 됩니다. 그런데 만약 type 속성을 생략하면 `type="submit"`이 적용됩니다. 즉, `<form>...</form>` 요소 내부의 사용자 입력 내용을 전송하는 기능을 갖게 됩니다.

```HTML
// type 속성 생략
<button>전송</button>

// type 속성 명시
<button type="submit">전송</button>
```

> 위와 같이 코드를 작성했을 때 동일하게 동작합니다.

<br />

## `<table>` 콘텐츠의 제목 마크업

`<table>` 요소는 2차원의 격자형 데이터를 표시하기 위한 표 마크업으로써 `<caption>` 요소와 `<figcaption>` 요소로 표의 제목을 마크업할 수 있습니다.

```HTML
// caption 사용 예
<table>
  <caption>표의 제목</caption>
  <tr>
    <th>...</th>
    <td>...</td>
  </tr>
</table>

// figcaption 사용 예
<figure>
  <figcaption>표의 제목</figcaption>
  <table>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
  </table>
</figure>
```

<br />

## `<fieldset>` 콘텐츠의 제목 마크업

`<fieldset>` 요소는 폼 요소를 내용에 따라 나누거나 그룹핑할 때 사용하는 요소로 `<legend>` 요소로 제목을 표시합니다.

```HTML
<form>
  <fieldset>
    <legend>회원 가입(필수 양식)</legend>
  </fieldset>
  <fieldset>
    <legend>회원 가입(선택 양식)</legend>
  </fieldset>
</form>
```

<br />

## `<script>` 요소의 부모 요소로 정당하지 않은 요소

`<script>` 요소는 `<head>`, `<body>` 요소를 부모로 가질 수 있지만, `<html>`, `<noscript>` 요소는 부모가 될 수 없습니다.

> `<head>`, `<body>` 를 부모 요소로 ◯  
> `<html>`, `<noscript>` 를 부모 요소로 ✖️

<br />

## `<form>` 요소의 필수 속성

`<form>` 요소는 정보를 제출하기 위한 대화형 컨트롤을 포함하는 문서 구획을 나타냅니다. 그리고 필수 속성이 없습니다.

선택 속성 중 대표 속성 첫 번째, **action 속성**은 `<form>` 요소에 포함된 사용자 입력 내용을 `전송하는 페이지의 URL을 명시`하는 속성입니다. (명시하지 않으면 현재 페이지 URL을 할당합니다.)

두 번째, **method 속성**은 양식을 제출할 때 사용할 `HTTP 메서드를 명시`합니다. (명시하지 않으면 **GET** 상태입니다.)

- **POST**: 양식 데이터를 요청 본문으로 전송합니다.
- **GET**: 양식 데이터를 action URL과 ? 구분자 뒤에 이어 붙여서 전송합니다.

세 번째, **onsubmit 속성**은 양식이 전송되는 순간을 제어할 수 있는 선택적 자바스크립트 이벤트 리스너입니다.

<br />

## `<form>` 요소를 전송할 때 입력 값을 서버로 전송하지 않는 요소

```HTML
<input disabled>
```

`<form>` 요소에 포함된 사용자 입력 내용이 submit 될 때 콘트롤에 <u>disabled</u> 라는 속성이 포함되어 있으면 해당 요소에 입력된 value 속성의 값은 서버로 전송하지 않습니다.

<br />

## `<main>` 요소의 활용 목적

`<main>` 요소는 문서 또는 애플리케이션의 메인 콘텐츠로써 중심 주제 또는 핵심 기능을 의미합니다. 또한 하나의 문서에 한 번만 선언할 수 있는 요소입니다.

> 단 hidden 속성으로 숨김 처리한 여러 개의 `<main>` 요소를 제공하고 단 하나의 `<main>` 요소만 화면에 표시하도록 처리하는 것을 허용합니다.

<br />

## `<section>` 요소의 활용 목적

`<section>` 요소는 문서의 챕터 또는 프로그램 섹션을 의미합니다. 보통 제목으로 시작하는 한 가지 주제 또는 하나의 애플리케이션 영역이기도 합니다. 그리고 `<section>` 요소의 내용은 주변 맥락을 제거한 상태로 배포하기에는 적절하지 않을 수 있습니다.

> `<artice>` 요소는 주변 맥락을 제거하고 독립적으로 배포하기에 적절하다는 점이 `<section>` 요소와 다릅니다.

<br />

## `<artice>` 요소의 활용 목적

`<article>` 요소는 독립적으로 배포 혹은 재사용 할 수 있는 섹션을 나타냅니다. 웹 페이지 본문, 신문의 기사, 블로그 포스트 본문 또는 댓글 영역을 마크업 하기에 적절한 요소입니다.

> `<section>` 요소는 주변 맥락을 제거하고 독립적으로 배포했을 때 보통 어색하다는 점이 `<article>` 요소와 다릅니다.

<br />

## `<input>` 요소의 type 종류

`hidden, text, search, tel, url, email, password, date, month, week, time, datetime-local, number, range, color, checkbox, radio, file, submit, image, reset, button`

<br />

## HTML5 문법으로 유효하지 않는 코드

`<main>` 요소는 페이지의 핵심 콘텐츠를 의미하는 맥락이기 때문에 body, div 요소 외 다른 요소의 자식 또는 자손이 될 수 없습니다.

```HTML
// 유효한 main 요소 사용
<body>
  <main></main>
</body>

// 유효하지 않은 main 요소 사용
<section>
  <main>...</main>
</section>
```

<br />

## `<b>` ⇆ `<strong>`, `<i>` ⇆ `<em>` 요소들의 차이점

`<b>` 요소와 `<strong>` 요소는 브라우저에 표시되는 모습은 같지만 역할은 다릅니다.

> `<b>`, `<strong>` 요소들에 텍스트를 넣으면 텍스트가 진하게 보이도록 bold 처리가 됩니다.

|    요소    | 사용 예시                 | 브라우저 표시 모습 |
| :--------: | :------------------------ | :----------------- |
|   `<b>`    | `<b>텍스트</b>`           | **텍스트**         |
| `<strong>` | `<strong>텍스트</strong>` | **텍스트**         |

<br />

`<b>` 요소는 단순히 텍스트를 진하게 표시하는 역할만 합니다. 따라서 서식상 다른 텍스트와 대비된 스타일로 강조를 하고 싶을 때 사용합니다.

`<strong>` 요소는 단순히 보여지는 강조가 아닌 실제로 페이지 내의 중요한 부분으로 브라우저에게 알려주는 역할을 합니다.

> 브라우저가 `<strong>` 요소를 해석할 때 페이지 내에서 중요한 부분으로 이해하며, 이는 브라우저에서 지원되는 웹 접근성(Web Accessibility)에 큰 기여를 합니다.

<br />

### 스크린 리더(Screen Reader)를 사용하는 경우

`<strong>` 요소를 사용하면 스크린 리더에서 해당 부분이 강조되었다고 알려주지만 `<b>` 요소는 알려주지 않습니다.

<br />

### `<i>` 요소와 `<em>` 요소의 차이

`<i>` 요소와 `<em>` 요소도 `<b>` 요소와 `<strong>` 요소 차이와 동일하게 `<i>` 요소는 브라우저에 기울임만을 나타내고 `<em>` 요소는 기울임과 함께 실질적인 강조를 의미하게 됩니다.

> 스크린 리더에도 동일하게 영향을 미칩니다.

<br />

### 요약 정리

즉, 특정한 텍스트에 대해 실제로도 강조하고자 하는 경우 `<strong>`, `<em>` 요소들을, 단순하게 텍스트를 bold 처리, 기울임 처리를 하려면 `<b>` 요소, `<i>` 요소를 사용하면 됩니다.

<br />

## 참고 자료

> https://developer.mozilla.org/ko/

> https://akdl911215.tistory.com/316

> https://fastcampus.co.kr/dev_red_jcm

> 새 창 열기 방법 : CTRL+click (on Windows and Linux) | CMD+click (on MacOS)
