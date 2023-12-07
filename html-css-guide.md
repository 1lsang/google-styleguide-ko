# Google HTML/CSS Style Guide
### 목차
  * [배경(Background)](#1-배경background)
  * [일반 규칙(General)](#2-일반-규칙general)
    + [일반적인 스타일 규칙(General Style Rules)](#21-일반적인-스타일-규칙general-style-rules)
    + [일반적인 포맷팅 규칙(General Formatting Rules)](#22-일반적인-포맷팅-규칙general-formatting-rules)
    + [일반적인 메타 규칙(General Meta Rules)](#23-일반적인-메타-규칙general-meta-rules)
  * [HTML](#3-html)
    + [HTML 스타일 규칙 (HTML Style Rules)](#31-html-스타일-규칙html-style-rules)
    + [HTML 포맷팅 규칙(HTML Formatting Rules)](#32-html-포맷팅-규칙html-formatting-rules)
  * [CSS](#4-css)
    + [CSS 스타일 규칙(CSS Style Rules)](#41-css-스타일-규칙css-style-rules)
    + [CSS 포맷팅 규칙(CSS Formatting Rules)](#42-css-포맷팅-규칙css-formatting-rules)
    + [CSS 메타 규칙(CSS Meta Rules)](#43-css-메타-규칙css-meta-rules)
  * [끝맺는 말(Parting Words)](#끝맺는-말parting-words)

## 1 배경(Background)
이 문서는 HTML과 CSS의 포맷팅과 스타일 규칙을 정의합니다. 이 문서는 협업과 코드 품질을 개선하고 지원하는 infrastructure를 활성화하는 것을 목표로 합니다. GSS 파일을 포함해서 HTML과 CSS를 사용하는 작업 파일 원본(raw)에 적용됩니다. 일반적인 코드 품질이 유지되는 한에서 도구는 자유롭게 난독화, 축소 및 컴파일할 수 있습니다.

## 2 일반 규칙(General)
### 2.1. 일반적인 스타일 규칙(General Style Rules)
#### 2.1.1 프로토콜(Protocol)
임베디드 리소스는 가능한 경우 HTTPS를 사용합니다.

해당 파일을 HTTPS로 사용할 수 없는 경우가 아니라면, 이미지 및 기타 미디어 파일, 스타일 시트, 스크립트는 항상 HTTPS(`https:`)를 사용하세요.

```html
<!-- ❌ Not recommended: 프로토콜을 생략한 경우 -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```

```html
<!-- ❌ Not recommended: HTTP를 사용한 경우 -->
<script  src="http://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```

```html
<!-- ✅ Recommended -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```

```css
/* ❌ Not recommended: 프로토콜을 생략한 경우 */
@import '//fonts.googleapis.com/css?family=Open+Sans';
```

```css
/* ❌ Not recommended: HTTP를 사용한 경우 */
@import 'http://fonts.googleapis.com/css?family=Open+Sans';
```

```css
/* ✅ Recommended */
@import 'https://fonts.googleapis.com/css?family=Open+Sans';
```

### 2.2 일반적인 포맷팅 규칙(General Formatting Rules)
#### 2.2.1 들여쓰기(Indentation)
한 번에 2칸씩 공백으로 들여쓰기합니다.

탭을 사용하거나 탭과 공백을 섞어 들여쓰기를 하지 마세요.

```html
<ul>
  <li>Fantastic</li>
  <li>Great</li>
</ul>
```

```css
.example {
  color: blue;
}
```

#### 2.2.2 대문자 사용(Capitalization)
소문자만 사용합니다.

모든 코드는 소문자만 사용해야 합니다: 이는 HTML 요소의 이름, 속성, 속성 값(`text/CDATA` 제외), CSS의 선택자, 속성 및 속성 값(문자열 제외)에 적용됩니다.

```html
<!-- ❌ Not recommended -->
<A HREF="/">Home</A>
```

```html
<!-- ✅ Recommended -->
<img src="google.png" alt="Google">
```

```css
/* ❌ Not recommended */
color: #E5E5E5;
```

```css
/* ✅ Recommended */
color: #e5e5e5;
```

#### 2.2.3 후행 공백(Trailing Whitespace)
후행 공백을 제거합니다.

후행 공백은 불필요하며 차이를 복잡하게 만들 수 있습니다.

```html
<!-- ❌ Not recommended -->
<p>What?_
```

```html
<!-- ✅ Recommended -->
<p>Yes please.
```

### 2.3 일반적인 메타 규칙(General Meta Rules)
#### 2.3.1 인코딩(Encoding)
UTF-8 인코딩을 사용합니다(BOM 아님).

> **Byte Order Mark**
> 유니코드 문자 U+FEFF를 문서 가장 앞에 추가하여 문서를 읽는 프로그램에 정보를 전달하는 방식.
> 하지만 UTF-8의 경우 인코딩 형식이 고정되어 있어 권장하지 않음.

에디터에서 바이트 순서 표시 없이 UTF-8을 문자 인코딩으로 사용하는지 확인하세요.

HTML 템플릿 및 문서는 `<meta charset="utf-8">`을 통해 인코딩을 지정합니다. 스타일 시트의 인코딩은 UTF-8을 가정하므로 지정하지 않습니다([참고](https://developer.mozilla.org/ko/docs/Web/CSS/@charset)). 

(인코딩과 인코딩 지정 시기 및 방법에 대한 자세한 내용은 [Handling character encodings in HTML and CSS](https://www.w3.org/International/tutorials/tutorial-char-enc/)에서 확인할 수 있습니다.)
#### 2.3.2 주석(Comments)
가능한 경우, 필요에 따라 코드를 설명합니다.

주석을 사용해 코드를 설명합니다: 무엇을 다루고 있는지, 어떤 용도로 사용되며, 해당 솔루션을 사용하거나 선호하는 이유는 무엇인지 설명하세요.

(완전하게 문서화된 코드를 요구하는 것은 현실적으로어렵기 때문에 주석은 선택 사항입니다. HTML 및 CSS 코드의 경우 프로젝트의 복잡성에 따라 달라질 수 있습니다.)

#### 2.3.2 실행 과제 (Action Items)
할 일과 실행 과제를 `TODO`로 표시합니다.

`@@`와 같은 다른 형식이 아니라 `TODO` 키워드만 사용해 할 일을 강조하여 표시하세요.

`TODO(연락처)` 형식처럼 괄호 안에 연락처(사용자 이름 또는 메일링 리스트)를 추가합니다.

`TODO: 실행 과제 내용`의 형태로 콜론(`:`) 뒤에 실행 과제를 추가합니다.

```html
{# TODO(john.doe): revisit centering #}
<center>Test</center>
```

```html
<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```

## 3 HTML
### 3.1 HTML 스타일 규칙 (HTML Style Rules)
#### 3.1.1 문서 타입 (Document Type)
HTML5를 사용합니다.

모든 HTML 문서에서 HTML5(HTML 구문)가 선호됩니다: `<!DOCTYPE html>`.

(텍스트/html로 HTML을 사용하는 것이 좋습니다. XHTML은 사용하지 마세요. XHTML(`application/xhtml+xml`)은 브라우저와 인프라 지원이 모두 부족하고, HTML보다 최적화를 할 수 있는 여지가 적습니다.)

#### 3.1.2 HTML 유효성 (HTML Validity)
가능한 유효한 HTML을 사용합니다.

파일 크기와 관련되어 달성할 수 없는 성능 목표 때문에 불가능한 경우가 아니라면 유효한 HTML 코드를 사용하세요. 

[W3C HTML 검사기](https://validator.w3.org/nu/)와 같은 도구를 사용하여 테스트하세요.

유효한 HTML을 사용하는 것은 측정 가능한 기준 품질 속성으로, 기술 요구 사항과 제약 조건을 파악하는 데 도움이 되며, 적절한 HTML 사용을 보장합니다.

```html
<!-- ❌ Not recommended -->
<title>Test</title>
<article>This is only a test.
```

```html
<!-- ✅ Recommended -->
<!DOCTYPE html>
<meta charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```

#### 3.1.3 의미론적 사용(Semantics)
HTML은 용도에 맞게 사용합니다.

요소(때로는 "태그"라고도 불림)를 그 요소가 생성된 용도에 맞게 사용합니다. 예를 들어, 제목에는 heading 요소(`h1`~`h6`), 단락에는 `p` 요소, 앵커에는 `a` 요소 등을 사용합니다.

HTML을 목적에 맞게 사용하는 것은 접근성, 재사용 및 코드 효율성을 위해 중요합니다.

```html
<!-- ❌ Not recommended -->
<div onclick="goToRecommendations();">All recommendations</div>
```

```html
<!-- ✅ Recommended -->
<a href="recommendations/">All recommendations</a>
```

#### 3.1.4 멀티미디어 대체 콘텐츠(Multimedia Fallback)
멀티미디어에 대한 대체 콘텐츠를 제공합니다.

이미지, 동영상, 캔버스를 통한 애니메이션 객체와 같은 멀티미디어의 경우 대체 접근 방법을 제공해야 합니다. 이미지의 경우 대체 텍스트(alt)를 의미를 담아서 작성하고, 비디오와 오디오는 가능하면 스크립트와 캡션을 제공합니다.

접근성을 위해 대체 콘텐츠를 제공하는 것은 중요합니다: 시각장애를 가진 사용자는 `@alt`가 없으면 이미지의 내용을 알기 어렵고, 다른 사용자들도 비디오나 오디오 콘텐츠의 내용을 이해하기 어려울 수 있습니다.

```html
<!-- ❌ Not recommended -->
<img src="spreadsheet.png">
```

```html
<!-- ✅ Recommended -->
<img src="spreadsheet.png" alt="Spreadsheet screenshot.">
```
#### 3.1.5 관심사 분리(Separation of Concerns)
구조, 프레젠테이션, 동작을 분리합니다.

구조(마크업), 프레젠테이션(스타일링), 동작(스크립팅)을 엄격하게 분리하고, 세 가지 간의 상호 작용을 최소한으로 유지하세요.

즉, 반드시 문서와 템플릿은 HTML만 포함하고, HTML은 오로지 구조적인 용도로 사용되어야 합니다.  프레젠테이션과 관련된 모든 것은 스타일시트로, 동작과 관련된 모든 것은 스크립트로 옮기세요.

또한, 문서와 템플릿에 스타일시트와 스크립트를 가능한 한 적게 연결하여 접촉 영역을 최대한 작게 유지하세요. 

구조와 프레젠테이션, 동작을 분리하는 것은 유지보수 측면에서 중요합니다. 스타일시트와 스크립트를 업데이트하는 것보다 HTML 문서와 템플릿을 변경하는 것이 항상 더 많은 비용이 듭니다.

```html
<!-- ❌ Not recommended -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!</center>
```

```html
<!-- ✅ Recommended -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>I’ve read about this on a few sites but today I’m actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.
<p>It’s awesome!
```
#### 3.1.6 엔티티 참조(Entity References)
엔티티 참조를 사용하지 마세요.

파일과 편집기에서 팀이 동일한 인코딩(UTF-8)을 사용한다면, `&mdash;``, &rdquo;`, `&#x263a;`와 같은 엔티티 참조를 사용할 필요가 없습니다.

`<` 및 `&`와 같이 HTML에서 특별한 의미를 갖는 문자, 제어 문자, no-break space(`&nbsp;`)와 같은 보이지 않는 문자는 예외로 사용할 수 있습니다.

```html
<!-- ❌ Not recommended -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.
```

```html
<!-- ✅ Recommended -->
The currency symbol for the Euro is “€”.
```
#### 3.1.7 옵셔널 태그(Optional Tags)
옵셔널 태그는 생략할 수 있습니다(선택 사항).

파일 크기 최적화와 스캔 가능성을 위해 옵셔널 태그를 생략하는 것이 좋습니다. [HTML5 사양](https://html.spec.whatwg.org/multipage/syntax.html#syntax-tag-omission)에서 생략할 수 있는 태그들이 정의되어 있습니다.

(이러한 접근 방식은 웹 개발자가 일반적으로 배우는 것과 크게 다르기 때문에 좀 더 일반적인 지침으로 확립되기까지 유예 기간이 필요할 수 있습니다. 일관성과 단순성을 위해 일부 옵셔널 태그뿐만 아니라 모든 옵셔널 태그를 생략하는 것이 가장 좋습니다.)

```html
<!-- ❌ Not recommended -->
<!DOCTYPE html>
<html>
  <head>
    <title>Spending money, spending bytes</title>
  </head>
  <body>
    <p>Sic.</p>
  </body>
</html>
```

```html
<!-- ✅ Recommended -->
<!DOCTYPE html>
<title>Saving money, saving bytes</title>
<p>Qed.
```

#### 3.1.8 `type` Attributes
스타일시트와 스크립트의 `type` 속성을 생략합니다.

스타일시트(CSS를 사용하는 경우) 및 스크립트(JavaScript를 사용하는 경우)에는 `type` 속성을 사용하지 마세요.

HTML5는 `text/css`와 `text/javascript`를 기본값으로 사용하므로, CSS와 Javascript `type` 속성을 지정할 필요가 없습니다. 이는 구형 브라우저에서도 안전하게 작동합니다.

```html
<!-- ❌ Not recommended -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css"
    type="text/css">
```

```html
<!-- ✅ Recommended -->
<link rel="stylesheet" href="https://www.google.com/css/maia.css">
```

```html
<!-- ❌ Not recommended -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"
    type="text/javascript"></script>
```

```html
<!-- ✅ Recommended -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```

#### 3.1.9 `id` Attributes
불필요한 `id` 속성을 사용하지 마세요.

스타일링에는 `class` 속성을, 스크립팅에는 `data` 속성을 사용하는 것을 추천합니다.

`id` 속성이 반드시 필요한 경우에는 항상 값에 하이픈을 포함하여 Javascript 식별자 구문와 일치하지 않도록 하는 것이 좋습니다.(예시: `profile` 또는 `userProfile` 대신 `user-profile` 사용).

요소에 `id` 속성이 있을 경우, 브라우저는 이를 [전역 `window` 프로토타입에서 명시된 속성](https://html.spec.whatwg.org/multipage/window-object.html#named-access-on-the-window-object)으로 사용할 수 있도록 설정하여 예상치 못한 동작이 발생할 수 있습니다. 하이픈이 포함된 `id` 속성 값은 여전히 속성 이름으로 사용할 수 있지만, Javascript의 전역 변수로 참조할 수는 없습니다.

```html
<!-- ❌ Not recommended: `window.userProfile`는 <div> 태그를 참조합니다. -->
<div id="userProfile"></div>
```

```html
<!-- ✅ Recommended: `id`속성은 필수이며 해당 값에 하이픈이 포함되어야 합니다. -->
<div aria-describedby="user-profile">
  …
  <div id="user-profile"></div>
  …
</div>
```

### 3.2 HTML 포맷팅 규칙(HTML Formatting Rules)

#### 3.2.1 일반적인 포맷팅(General Formatting)
모든 블록, 목록 또는 표 요소에 새 줄을 사용하고, 그 하위 요소를 모두 들여쓰기합니다.

요소의 스타일과 관계없이(CSS의 `display` 속성별로 다르게 보이기 때문) 모든 블록, 목록 또는 표 요소는 새 줄에 넣습니다.

또한, 블록, 목록 또는 표 요소의 자식 요소는 들여쓰기합니다.

(목록 요소 사이의 공백으로 인해 문제가 발생하는 경우, 모든 `li` 요소를 한 줄에 넣어도 괜찮습니다. 이 경우에 린트 도구는 오류 대신 경고를 표시하는 것이 좋습니다.)

```html
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
```

```html
<ul>
  <li>Moe
  <li>Larry
  <li>Curly
</ul>
```

```html
<table>
  <thead>
    <tr>
      <th scope="col">Income
      <th scope="col">Taxes
  <tbody>
    <tr>
      <td>$ 5.00
      <td>$ 4.50
</table>
```
#### 3.2.2 HTML 줄 바꿈(HTML Line-Wrapping)
긴 줄은 나눌 수 있습니다.(선택 사항).

HTML의 열 제한에 대한 권장 사항은 없지만, 가독성을 크게 향상시킬 수 있다면 줄 바꿈하는 것을 고려할 수 있습니다.

줄 바꿈시, 하위 요소와 구분하기 위해 각 줄에 들여쓰기를 해야 합니다. 줄 바꿈은 프로젝트 내에서 일관되게 적용되어야 하며, 자동화된 코드 포맷팅 도구로 적용하는 것이 가장 좋습니다.

```html
<button
  mat-icon-button
  color="primary"
  class="menu-button"
  (click)="openMenu()"
>
  <mat-icon>menu</mat-icon>
</button>
```

```html
<button mat-icon-button color="primary" class="menu-button"
    (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```

```html
<button
    mat-icon-button
    color="primary"
    class="menu-button"
    (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```

```html
<button mat-icon-button
        color="primary"
        class="menu-button"
        (click)="openMenu()">
  <mat-icon>menu</mat-icon>
</button>
```
#### 3.2.3 HTML 따옴표(HTML Quotation Marks)

속성 값을 사용할 때는 큰따옴표를 사용합니다.

속성 값을 작은따옴표(`''`)가 아닌 큰따옴표(`""`)로 감쌉니다.
```html
<!-- ❌ Not recommended -->
<a class='maia-button maia-button-secondary'>Sign in</a>
```

```html
<!-- ✅ Recommended -->
<a class="maia-button maia-button-secondary">Sign in</a>
```
## 4 CSS

### 4.1 CSS 스타일 규칙(CSS Style Rules)
#### 4.1.1 CSS 유효성(CSS Validity)
가능한 경우 유효한 CSS를 사용합니다.

CSS 유효성 검사기 버그를 다룰 때나 특정 소프트웨어나 플랫폼에서 사용되는 고유한 문법이 필요한 경우가 아니라면, 유효한 CSS 코드를 사용하세요.

[W3C CSS 검사기](https://jigsaw.w3.org/css-validator/)와 같은 도구를 사용하여 테스트하세요.

유효한 CSS를 사용하는 것은 측정 가능한 품질 기준으로, 효과가 없거나 제거할 수 있는 CSS 코드를 찾아내어 CSS를 적절하게 사용할 수 있습니다.
#### 4.1.2 클래스 네이밍(Class Naming)
의미 있거나 일반적인 클래스 이름을 사용합니다.

관념적이거나 암호화된 이름 대신, 항상 해당 요소의 목적을 반영하거나 일반적인 클래스 이름을 사용하세요.

구체적이면서 요소의 목적을 반영하는 이름이 이해하기 쉽고 변경 가능성이 낮기 때문에 가장 좋습니다.

일반적인 이름은 형제 요소와 다르게 단순히 특별하거나 의미가 없는 요소를 위한 대안입니다. 일반적으로 "헬퍼(helpers)"로서 필요합니다.

기능적인 이름이나 일반적인 이름을 사용하면 불필요한 문서나 템플릿이 변경될 확률이 줄어듭니다.
```css
/* ❌ Not recommended: 의미가 없는 이름 */
.yee-1901 {}

/* ❌ Not recommended: 관념적인 이름 */
.button-green {}
.clear {}
```

```css
/* ✅ Recommended: 구체적인 이름 */
.gallery {}
.login {}
.video {}

/* ✅ Recommended: 일반적인 이름 */
.aux {}
.alt {}
```

#### 4.1.3 클래스 이름 스타일(Class Name Style)
필요한 만큼 길이 내에서 가능한 짧은 클래스 이름을 사용합니다.

가능한 간결하게 클래스의 내용을 전달할 수 있도록 시도하세요.

이러한 방식의 클래스 이름을 사용하면 적절한 수준의 이해도와 코드 효율성에 기여할 수 있습니다.

```css
/* ❌ Not recommended */
.navigation {}
.atr {}
```

```css
/* ✅ Recommended */
.nav {}
.author {}
```

#### 4.1.4 클래스 이름 구분자(Class Name Delimiters)
클래스명에서 단어는 하이픈으로 구분합니다.

이해도와 스캔 가능성(scannability)을 높이기 위해 선택기에서 단어와 약어를 하이픈 이외의 다른 문자로 연결하지 마세요.

```css
/* ❌ Not recommended: “demo”와 “image”를 분리하지 않음 */
.demoimage {}

/* ❌ Not recommended: hyphen 대신 underscore를 사용함 */
.error_status {}
```

```css
/* ✅ Recommended */
.video-id {}
.ads-sample {}
```

#### 4.1.5 접두사(Prefixes)
애플리케이션별로 접두사를 선택자의 앞에 붙이세요(선택 사항).

대규모 프로젝트뿐만 아니라 다른 프로젝트나 외부 사이트에 임베드되는 코드의 경우, 클래스 이름에 접두사(네임스페이스)를 사용합니다. 짧고 고유한 식별자 뒤에 대시를 사용하세요.

네임스페이스를 사용하여 이름 충돌을 방지하고 검색 및 수정 등의 유지보수 작업을 더 쉽게 할 수 있습니다.

```css
.adw-help {} /* AdWords */
.maia-note {} /* Maia */
```

#### 4.1.6 타입 선택자(Type Selectors)
타입 선택자로 클래스 이름을 한정하지 마세요.

헬퍼 클래스처럼 꼭 필요한 경우가 아니라면, 요소 이름을 클래스와 함께 사용하지 마세요.

[성능상의 이유](http://www.stevesouders.com/blog/2009/06/18/simplifying-css-selectors/)로 불필요한 부모 선택자는 사용하지 않는 것이 좋습니다.

```css
 /* ❌ Not recommended */
ul.example {}
div.error {}
```

```css
/* ✅ Recommended */
.example {}
.error {}
```

#### 4.1.7 ID 선택자(ID Selectors)
ID 선택자를 피하세요.

ID 속성은 전체 페이지에서고유해야 하며, 페이지에 여러 엔지니어가 작업한 여러 컴포넌트가 포함되어 있는 경우 이를 보장하기 어렵습니다. 모든 상황에서 클래스 선택자를 사용해야 합니다.

```css
 /* ❌ Not recommended */
#example {}
```

```css
/* ✅ Recommended */
.example {}
```

#### 4.1.8 축약형 속성(Shorthand Properties)
가능하면 축약형 속성을 사용합니다.

CSS에서 `font`와 같은 속성은 축약형을 제공하며, 하나의 값만 명시적으로 설정하는 경우에도 가능하면 항상 축약형을 사용합니다.

축약형 속성을 사용하면 코드 효율성과 이해도를 높이는 데 유용합니다.

```css
 /* ❌ Not recommended */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

```css
/* ✅ Recommended */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

#### 4.1.9 0과 단위(0 and Units)
필요한 경우가 아니라면 "0" 값 뒤의 단위 지정은 생략합니다.

꼭 필요한 경우가 아니라면 `0` 값 뒤에 단위를 사용하지 마세요.

```css
flex: 0px; /* 이 flex 기반 속성은 단위가 필요합니다. */
flex: 1 1 0px; /* 단위가 없어도 모호하지 않지만, IE11에서는 필요합니다. */
margin: 0;
padding: 0;
```

#### 4.1.10 선행 0(Leading 0s)
값에는 항상 선행 "0"을 포함합니다.

-1에서 1 사이의 값 또는 길이 앞에는 `0`을 넣습니다.

```css
font-size: 0.8em;
```

#### 4.1.11 16진수 표기볍(Hexadecimal Notation)
가능한 경우 3자 16진수 표기를 사용합니다.

허용되는 색상 값의 경우 3자 16진수 표기가 더 짧고 간결합니다.

```css
 /* ❌ Not recommended */
color: #eebbcc;
```

```css
/* ✅ Recommended */
color: #ebc;
```

#### 4.1.12 Important 선언(Important Declarations)
`!important` 선언을 사용하지 마세요.

`!important` 선언은 CSS의 자연스러운 cascade를 깨뜨려 스타일을 추론하고 작성하기 어렵게 만듭니다. 대신 [선택자 명시도(selector specificity)](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)을 사용하여 속성을 덮어쓰세요.

```css
 /* ❌ Not recommended */
.example {
  font-weight: bold !important;
}
```

```css
/* ✅ Recommended */
.example {
  font-weight: bold;
}
```

#### 4.1.13 Hacks

> 본문에서 Hacks이라는 표현을 해킹이라고 번역하였지만, 실제로는 꼼수...정도라고 생각하면 될 것 같습니다.

브라우저 감지와 CSS 해킹을 피하고, 먼저 다른 접근 방식을 시도하세요.

브라우저 감지나 특수 CSS 필터, 일시적인 해결책 및 해킹을 통해 스타일링의 차이를 해결하고 싶은 유혹이 있을 수 있습니다. 하지만 그런 접근 방식은 효율적이고 관리하기 쉬운 코드 기반을 달성하고 유지하기 위해 최후의 수단으로 고려해야 합니다. 다시 말해, 브라우저 감지나 해킹을 자유롭게 할 수 있도록 하는 것은 가장 단순한 방법을 택하는 것으로 장기적으로 프로젝트에 해가 될 수 있습니다. 즉, 브라우저 감지와 해킹을 허용하고 쉽게 사용할 수 있도록 할 경우, 그것들을 더 자주 그리고 더 많이 사용하게 될 것이기 때문입니다.

### 4.2 CSS 포맷팅 규칙(CSS Formatting Rules)

#### 4.2.1 선언 순서(Declaration Order)
알파벳순으로 선언을 정렬합니다(선택 사항).

프로젝트에서 일관된 순서로 선언을 정렬하세요. 일관된 정렬 순서를 자동화하고 강제하는 도구가 없는 경우, 일관된 코드를 얻기 위해 학습하고 기억하고 수동으로 유지 관리하기 쉬운 방식인 알파벳 순서로 배치하는 것을 고려할 수 있습니다.

정렬을 위해 vendor 접두사들은 무시하세요. 하지만 특정 CSS 속성에 대한 여러 vendor 접두사가 있는 경우 정렬된 상태로 유지해야 합니다(예시: -moz 접두사가 -webkit 앞에 오는 경우)

```css
background: fuchsia;
border: 1px solid;
-moz-border-radius: 4px;
-webkit-border-radius: 4px;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em;
```

#### 4.2.2 블록 콘텐츠 들여쓰기(Block Content Indentation)
모든 블록 콘텐츠를 들여쓰기합니다.

모든 [블록 콘텐츠](https://www.w3.org/TR/CSS21/syndata.html#block), 즉 규칙 내의 규칙과 선언을 들여쓰기하여 계층 구조를 반영하고 이해도를 높입니다.

```css
@media screen, projection {

  html {
    background: #fff;
    color: #444;
  }

}
```

#### 4.2.3 선언 종결(Declaration Stops)
모든 선언 뒤에 세미콜론을 사용합니다.

일관성 및 확장성을 위해 모든 선언을 세미콜론으로 끝내세요.

```css
 /* ❌ Not recommended */
.test {
  display: block;
  height: 100px
}
```

```css
/* ✅ Recommended */
.test {
  display: block;
  height: 100px;
}
```

#### 4.2.4 속성 이름 종결(Property Name Stops)
속성 이름의 콜론 뒤에 공백을 사용합니다.

일관성을 위해 프로퍼티와 값 사이에는 항상 공백을 하나만 사용하세요(프로퍼티와 콜론 사이에는 공백을 두지 마세요).

```css
 /* ❌ Not recommended */
h3 {
  font-weight:bold;
}
```

```css
/* ✅ Recommended */
h3 {
  font-weight: bold;
}
```

#### 4.2.5 선언 블록 분리(Declaration Block Separation)
마지막 선택자와 선언 블록 사이에 공백을 사용합니다.

마지막 선택자와 선언 블록을 시작하는 여는 중괄호 사이에는 항상 공백을 하나만 사용하세요.

여는 중괄호는 주어진 규칙에서 마지막 선택자와 같은 줄에 있어야 합니다.

```css
/* ❌ Not recommended: 공백이 없음 */
.video{
  margin-top: 1em;
}

/* ❌ Not recommended: 불필요한 줄바꿈이 있음 */
.video
{
  margin-top: 1em;
}
```

```css
/* ✅ Recommended */
.video {
  margin-top: 1em;
}
```

#### 4.2.6 선택자와 선언 분리(Selector and Declaration Separation)
선택자와 선언을 새 줄로 구분합니다.

각 선택자와 선언은 항상 새 줄로 시작합니다.

#### 4.2.7 규칙 분리(Rule Separation)
새 줄로 규칙을 구분합니다.

규칙 사이에는 항상 빈 줄(줄 바꿈 두 개)을 넣으세요.

```css
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```

#### 4.2.8 CSS 따옴표(CSS Quotation Marks)
Use single (`''`) rather than double (`""`) quotation marks for attribute selectors and property values.

Do not use quotation marks in URI values (`url()`).

Exception: If you do need to use the `@charset` rule, use double quotation marks—[single quotation marks are not permitted](https://www.w3.org/TR/CSS21/syndata.html#charset).

속성 선택자와 속성 값에는 큰따옴표(`""`)가 아닌 작은따옴표(`''`)를 사용합니다.

URI 값(`url()`)에는 따옴표를 사용하지 마세요.

예외: `@charset` 규칙을 사용해야 하는 경우, 큰따옴표를 사용해야 하며 [작은따옴표는 허용되지 않습니다](https://www.w3.org/TR/CSS21/syndata.html#charset).

```css
 /* ❌ Not recommended */
@import url("https://www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}
```

```css
/* ✅ Recommended */
@import url(https://www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```
### 4.3 CSS 메타 규칙(CSS Meta Rules)

#### 4.3.1 (Section Comments)
섹션별로 주석을 달아 섹션을 그룹화합니다(선택 사항).

가능하면 주석을 사용하여 스타일 시트 섹션을 함께 그룹화합니다. 새 줄로 섹션을 구분합니다.

```css
/* Header */

.adw-header {}

/* Footer */

.adw-footer {}

/* Gallery */

.adw-gallery {}
```

## 끝맺는 말(Parting Words)
_일관성을 유지하세요._

코드를 작성할 때, 잠시 시간을 내어 기존 코드를 살펴보고 스타일을 파악하세요. 모든 산술 연산자 주위에 공백을 사용한다면 여러분도 공백을 사용해야 합니다. 주석 주위에 해시 마크로 이루어진 작은 상자가 있다면 여러분의 주석에도 해시 마크 상자를 넣으세요.

스타일 가이드라인의 목표는 사람들이 코딩 방법보다는 코딩 내용에 집중할 수 있도록 공통의 코딩 어휘를 사용하는 것입니다. 이 문서에서는 사람들이 어휘를 알 수 있도록 글로벌 스타일 규칙을 제시하지만, 로컬 스타일도 중요합니다. 파일에 추가한 코드가 주변의 기존 코드와 크게 다르면 독자가 코드를 읽으려고 할 때 리듬을 잃게 됩니다. 이를 피하세요.