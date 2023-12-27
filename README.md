# HTML Practice Note

## 개요

HTML에 대해 학습 및 실습한 내용을 적습니다. MDN 사이트의 HTML 튜토리얼을 참고했습니다.
- https://developer.mozilla.org/ko/

<br />

## HTML ?

HTML(Hypertext Markup Language)은 웹 페이지가 어떻게 구조화되어 있는지 브라우저에게 알려주기 위해 사용하는 마크업 언어입니다. 특정 컨텐츠를 생성 또는 수정하거나 또다른 페이지를 하이퍼링크로 연결하여 이동할 수 있습니다.

### 요소(Element)

웹 페이지 구조는 일련의 요소로 이루어져 있으며 태그(tag)로 감싸 나타냅니다. 

![element](https://developer.mozilla.org/ko/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

어떤 요소는 속성(attribute)을 가질 수 있습니다.

![attr](https://developer.mozilla.org/ko/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-attribute-small.png)

속성은 실제 컨텐츠로 표시되지 않고 요소에 대한 추가적인 정보를 담고 있습니다. '속성명="값"'으로 나타내며 어떤 속성은 값을 가지지 않기도 합니다(ex. `required`).

속성이 항상 가져야 하는 것은 다음과 같습니다.

1. 요소 이름과 속성 사이에는 공백이 있어야 합니다. 속성이 여러개라면 속성과 속성 사이에도 공백이 있어야 합니다.

2. 속성 이름 뒤에는 등호(=)가 와야 합니다.

3. 속성 값의 앞뒤에 열고 닫는 인용부호(" 또는 ')가 있어야 합니다.

### 요소 중첩(Nesting)

요소를 다른 요소의 안에 놓을 수 있습니다.

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

### 블록(Block) 요소 vs 인라인(Inline) 요소

HTML에는 두 가지 종류의 요소가 있습니다. 바로 블록 레벨 요소와 인라인 요소입니다.

- 블록 레벨 요소는 한 줄(line)을 전부 차지하는 블록을 만들며 일반적으로 웹페이지의 구조적 요소를 나타낼 때 사용됩니다. 단락(paragraphs), 목록(lists), 네비게이션 메뉴(navigation menus), 꼬리말(footer) 등을 표현할 수 있습니다. 서로 다른 블록 요소끼리는 중첩될 수 있지만, 인라인 요소에는 중첩될 수 없습니다.

- 인라인 요소는 새로운 줄을 만들지 않으며 항상 블록 레벨 요소에 포함되어 있습니다. 문장, 단어 같은 작은 부분에 대해 사용됩니다(ex. 하이퍼링크, 텍스트).

### 빈(Empty) 요소

어떤 요소들은 내용을 갖지 않습니다.

```html
<img src="" />
<link />
<meta />
```

닫힌 태그가 따로 존재하지 않고 단일(single) 태그만으로 작성합니다.

다만, 태그의 뒷쪽에 슬래시(/)를 붙여 닫힘을 표시합니다. 대부분의 경우 슬래시를 작성하지 않아도 문제 없이 동작하지만(브라우저가 HTML을 해석할 때 자동으로 슬래시를 붙여 동작), 브라우저의 해석이 언제나 올바른 것만은 아닙니다. 따라서 예기치 않은 오류를 피하기 위해 슬래시를 명시적으로 작성하는 것을 권장합니다.

### HTML5 기본 템플릿

에밋(emmet)으로 작성되는 HTML5의 기본 템플릿은 다음과 같습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width" />
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

- `<!DOCTYPE html>` : HTML 문서의 가장 첫 줄로 명시해야 하는 내용입니다. HTML 버전을 나타냅니다.

- `<html></html>` : HTML 문서의 전체 범위를 나타냅니다. 이 요소는 페이지 전체의 컨텐츠를 감싸며, 루트(root) 요소라고도 합니다. 문서의 고유 언어를 설정하는 `lang` 속성을 포함합니다.

- `<head></head>` : 사용자에게 보여지는 컨텐츠가 아닌 문서 자체의 정보를 나타냅니다. 페이지의 제목, 설명, 참조할 파일들(CSS/JS) 등을 포함합니다.

- `<meta charset="utf-8" />` : 문서가 사용할 문자 집합을 나타냅니다. 웹 초창기의 문자 코드는 'ASCII'의 로마자 위주 코드였고, 1byte 남짓의 작은 공간에 자국 문자를 할당했었습니다. 이런 상황에서 다른 국가에 이메일을 보냈더니 글자 깨짐 현상이 나타났고, 그 대책으로 4byte(32bit, 약 42억 자)의 넉넉한 공간에 세상의 모든 문자를 할당하는 방법이 제시됐습니다. 이를 유니코드(Unicode), 전 세계의 모든 문자를 다루도록 설계된 표준 문자 전산 처리 방식이라 합니다. 이로 인해 각 언어와 문자 체계에 따른 충돌 문제가 해결됐고 한글, 한자, 아랍 문자 등을 통일된 환경에서 사용할 수 있습니다. `utf`는 유니코드의 인코딩 방식 중 하나이며 현재 호환성이 가장 좋은 인코딩은 `utf-8`입니다.

- `<meta name="viewport" content="width=device-width" />` : 뷰포트의 너비에서 페이지가 렌더링하도록 하며, 모바일 브라우저가 뷰포트보다 넓은 페이지를 렌더링한 후 축소하는 것을 방지합니다.

- `<title></title>` : 브라우저의 탭에 나타나는 페이지 제목을 설정합니다.

- `<body></body>` : 사용자에게 보여지길 원하는 모든 컨텐츠를 포함합니다.

<br />

## 메타데이터(Metadata)

### `<head>` 요소

head 태그는 브라우저에 내용이 표시되지 않는 대신 페이지에 대한 메타데이터를 포함합니다.

### `<title>` 요소

head 태그에 포함되는 요소인 `<title>`은 body 태그의 최상위 부분에 들어가는 `<h1>`과 헷갈릴 수 있습니다.

- `<h1>`은 일반적으로 페이지당 한 번씩 사용되는데, 페이지 내용물의 제목이나 뉴스의 헤드라인을 표시하기 위해 표시됩니다.

- `<title>`은 문서의 컨텐츠가 아니라 HTML 문서 전체의 제목을 표현하기 위한 메타데이터입니다.

### `<meta>` 요소

HTML 문서에 메타데이터를 적용하는데에 사용합니다.

1. 문서의 문자(character) 인코딩 지정

- `<meta charset="utf-8" />`

- 위의 설명처럼, 웹 페이지에서 어떤 문자라도 취급할 수 있다는 것을 의미합니다.

- 크롬과 같은 어떤 브라우저는 자동으로 잘못된 인코딩을 고치기 때문에, 문자 깨짐 현상을 겪지 않을 수도 있습니다. 그래도 다른 브라우저에서 있을 잠재적인 문제를 피하기 위해 인코딩을 `utf-8`로 설정해야 합니다.

2. 저자와 설명 추가

```html
<meta name="author" content="my-name" />
<meta name="description" content="some-description" />
```

- 많은 `<meta>` 요소가 `name`과 `content` 속성을 가집니다. `name`은 정보의 형태, `content`는 실제 메타데이터의 컨텐츠입니다.

- 저자를 지정하는 것은 컨텐츠 작성자에 대한 정보를 볼 수 있게 해줍니다. 일부 컨텐츠 관리 시스템에는 페이지 작성자 정보를 자동으로 추출해서 사용할 수 있는 기능이 있습니다.

- 페이지 컨텐츠 관련 키워드를 포함시키는 것은 검색 엔진에서 이 페이지가 더 많이 표시될 가능성을 높여줍니다. 이러한 활동을 SEO(Search Engine Optimization)라고 합니다.

- 참고: 이외에도 많은 `<meta>` 기능들이 있지만 현재에는 더이상 사용되지 않습니다. 대표적으로 다른 검색 용어에 대해 해당 페이지의 관련성을 부여하기 위해 검색 엔진에 키워드를 제공하던 `<meta name="keywords" content="fill, in, your, keywords, here" />` 구문이 있습니다. 그러나 스팸 발송자들이 키워드 목록에 수백 개의 키워드를 채워버리는 악용 사례가 생겨버렸기 때문에 해당 기능은 검색 엔진들이 아예 무시를 해버리게 되었습니다.

3. 다른 종류의 메타데이터 삽입

```html
<meta property="og:image" content="my-og-image.png" />
<meta property="og:description" content="my-og-description" />
<meta property="og:title" content="my-og-title" />
<meta name="twitter:title" content="my-twitter-title" />
```

여러 메타데이터 중 어떤 것들은 특정 사이트(ex. SNS 사이트)에 사용할 수 있는 특정 정보를 제공하도록 설계되었습니다.

- Open Graph Data는 Facebook이 웹 사이트에 더 풍부한 메타데이터를 제공하기 위해 발명한 프로토콜입니다. 이는 사용자에게 보다 나은 정보를 보여줄 수 있습니다.

- Twitter에서도 유사한 형태의 독점 메타데이터를 가지고 있습니다.

### 커스텀 아이콘

커스텀 아이콘을 메타데이터에 추가하고 특정 컨텐츠에서 보여지게 할 수 있습니다. 이를 파비콘(favicon, favorite icon)이라 하며 16x16 픽셀의 크기를 갖습니다. 페이지의 탭이나 북마크 패널에서 볼 수 있습니다.

사이트에 파비콘을 추가하는 방법은 다음과 같습니다.

1. `index.html` 파일이 있는 디렉토리에 `.ico` 포멧의 파일을 저장합니다. 대부분의 브라우저는 `.gif` 또는 `.png`와 같은 보다 일반적인 형식의 파비콘을 지원하지만 ICO 포멧을 사용하면 IE6까지 작동합니다.

2. `<head>`에 다음 구문을 추가합니다.

```html
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon" />
```

### HTML에 CSS, JS 적용하기

웹 페이지에 디자인을 더할 CSS, 사용자와 상호작용 기능을 위한 JS 파일을 적용하는 방법은 다음과 같습니다.

```html
<link rel="stylesheet" href="my-css-file.css" />
```

- `<link>`는 항상 문서의 `<head>` 부분에 위치합니다.

- `rel="stylesheet"`는 스타일 시트임을 나타냄과 동시에 해당 파일의 경로를 뜻하는 `href`를 포함합니다.

```html
<script src="my-js-file.js"></script>
```

- `<script>`는 반드시 `<head>`에 들어갈 필요는 없습니다. 주로 `</body>`의 바로 앞, 문서 본문의 맨 끝에 넣는 것이 좋으며 JS를 적용하기 전에 모든 HTML 내용을 브라우저가 읽도록 하는 것이 좋습니다. 그렇지 않을 경우 JS에서 참조하려는 HTML 요소가 아직 존재하지 않는 것으로 판단하여 에러가 날 수 있습니다.

### 문서의 기본 언어 설정

`<html>`에 페이지의 기본 언어를 설정할 수 있습니다.

```html
<html lang="ko"></html>
```

HTML 문서는 언어가 설정되어 있으면 검색 엔진에 의해 보다 효과적으로 색인화(언어별 결과에 올바르게 표시)되며 화면 판독기를 사용하는 시각장애가 있는 사용자에게 유용합니다.

또한 문서의 하위 섹션을 다른 언어로 인식하도록 설정할 수도 있습니다. 다음 구문은 일본어로 인식됩니다.

```html
<p>
  Japanese example:
  <span lang="jp">ご飯が熱い</span>
</p>
```

<br />

## 텍스트 표현(기본)

HTML의 주요 작업 중 하나는 브라우저가 텍스트를 올바르게 표시할 수 있도록 텍스트 구조와 의미를 제공(semantics)하는 것입니다.

### 제목과 단락

대부분의 구조화된 텍스트는 제목과 단락으로 구성됩니다. 각 제목은 `<heading>`, 단락은 `<p>` 안에 있어야 합니다.

```html
<h1>I am the title</h1>
<p>I am a paragraph</p>
```

`<heading>`은 `<h1>`에서 `<h6>`까지 총 6개가 있습니다. 메인 제목인 `<h1>`부터 시작해 숫자가 높을수록 하위 제목을 나타냅니다.

이처럼 계층을 구조화할 때에는 몇 가지 관례가 있습니다.

- 가급적 페이지당 하나의 `<h1>`만을 사용해야 합니다. 이것은 최상위 제목이며 나머지는 `<h1>`의 밑에 위치합니다.

- 각 제목을 올바른 순서로 사용해야 합니다. `<h2>`는 `<h3>`의 하위로 올 수 없습니다.

- `<heading>`은 총 6개를 사용할 수 있지만 꼭 필요한 것이 아니라면 한 페이지에 3개 이상을 사용하지 않도록 합니다. 너무 많은 목차 레벨을 가진 문서는 탐색하기에 좋지 않습니다. 이러한 상황에서는 가능하면 컨텐츠를 여러 페이지로 나누는 것이 바람직합니다.

이렇게 구조화하는 이유에는 다음과 같은 것들이 있습니다.

- 사용자는 보통 웹 페이지에서 필요한 컨텐츠만을 빠르게 살피며 `<heading>`만 읽기도 합니다. 따라서 몇 초 안에 필요한 컨텐츠를 찾지 못하면 웹 페이지에 머무르는 시간이 매우 짧아집니다.

- 검색 엔진들은 `<heading>`을 페이지 검색 순위에 영향을 주는 중요한 키워드로 고려해 인덱싱합니다. `<heading>`이 없다면 SEO 측면에서 불리합니다.

- 시각 장애인들이 웹 페이지를 조회할 때 사용하는 screen reader라는 소프트웨어는 `<heading>`을 읽어주어 문서의 개요를 전달하며, 문서 전체를 읽지 않아도 되는 편의를 제공합니다.

- CSS와 JS를 원활히 적용시키기 위해 관련 컨텐츠를 감싸는 요소가 필요합니다.

### 목록

HTML에서 목록은 순서의 유무에 따라 다르게 나타냅니다.

- `<ul>`은 순서가 없는(unordered) 목록입니다.

- `<ol>`은 순서가 있는(ordered) 목록입니다.

- `<li>`는 목록 안의 각 항목들을 감싸는 태그입니다.

- 목록 내부에 다른 목록을 추가할 수 있습니다.

```html
<ol>
  <li>Day 1</li>
    <ul>
      <li>HTML</li>
      <li>CSS</li>    
    </ul>
  <li>Day 2</li>
</ol>
```

### 중요(Emphasis)와 강조(Importance)

우리는 말을 하면서 특정 단어에 강세를 두고 발음하는 방법으로 의미를 다르게 표현합니다. 예를 들어 다음 두 문장은 다른 의미를 가집니다.

I am glad you weren't late.

I am *glad* you weren't *late*.

첫 문장은 늦지 않은 것에 대해 안도하는 느낌이지만, 두 번째 문장은 상대가 조금 늦게 도착한 것에 대해 비꼬거나 짜증을 표현하는 것처럼 들립니다.

HTML에서는 이러한 경우를 표시하기 위해 `<em>`을 사용합니다. 문장의 의미를 파악하는데에 도움을 줄 뿐 아니라, 화면 판독기에 인식되면 다른 톤의 목소리로 표현됩니다.

브라우저에서는 기본적으로 `<em>`을 이탤릭체(italic)로 표현하지만, 단지 이탤릭체로 스타일링하기 위해 이 태그를 사용하는 것은 지양합니다. 필요한 경우 `<span>`에 CSS를 더하거나 `<i>`를 사용합니다.

중요한 단어를 강조하는 다른 방법으로는 글자를 두껍게 표현하는 것이 있고, 이를 위해 `<strong>`을 사용합니다.

**Do not** be late!

`<em>`과 마찬가지로, 화면 판독기에 인식되면 다른 톤의 목소리로 표현되며 단순 스타일링 용도로는 `<strong>` 대신 `<span>`에 CSS를 더하거나 `<b>`를 사용합니다.

앞서 살펴본 `<i>`, `<b>`, 그리고 밑줄(underline)을 표시하는 `<u>`와 같은 요소는 본래 빈약한 CSS 지원을 위해 고안되었습니다. 의미론적(semantic)이 아닌 표현(presentation)에만 영향을 주는 요소들이었으며, 더이상 사용되어서는 안됩니다. 의미론적 구성이 접근성, SEO 등에 매우 중요하기 때문입니다.

따라서 HTML5에서는 `<i>`, `<b>`, `<u>`에 새로운 의미론적 역할을 부여했습니다.

- `<i>`는 외래어, 분류학 명칭, 전문 용어, 생각 등에 사용됩니다.

- `<b>`는 주요 단어(문장), 제품 이름 등에 사용됩니다.

- `<u>`는 고유명, 철자 오타 등에 사용됩니다.

특히, 사람들은 밑줄을 하이퍼링크와 강하게 연관시킵니다. 따라서 웹에서는 링크에만 밑줄을 긋는 것이 가장 좋습니다. 의미론적으로도 적합한 경우 `<u>`를 사용하되 CSS를 사용해 더 적합하게 변경할 수 있는지를 고려해야 합니다.

<br />

## 하이퍼링크 만들기

웹에서 하이퍼링크는 문서와 문서, 문서와 리소스 사이를 URL 이동을 통해 연결해줍니다.

### 링크의 구조

파일, 텍스트, 이미지, 비디오, 블록 레벨 요소들까지도 `<a>`로 감싸 링크로 바꿀 수 있습니다. URL은 `href`(hypertext reference) 속성의 값으로 적습니다.

```html
<a href="https://www.google.com">Google Home</a>
```

`title` 속성으로 링크에 부가적인 정보를 추가할 수 있습니다.

```html
<a
  href="https://www.google.com"
  title="This is Google home link">
  Go Google
</a>
```

### URL과 경로(path)

URL(Uniform Resource Locator)은 단순히 리소스가 웹상의 어디에 위치하는지 정의하는 문자열입니다. 또한 URL은 원하는 파일을 찾기 위해 경로를 이용합니다. 경로는 해당 파일이 파일시스템의 어디에 있는지 구체적으로 명시합니다.

문서의 최상위 경로 외에도, 문서 내부의 조각(fragment)으로 이동하도록 연결할 수도 있습니다. 일반적으로는 특정 헤드라인에 연결하는 것이 좋습니다.

문서 조각에 연결하려면 먼저 연결하고 싶은 태그에 `id` 속성을 넣습니다.

```html
<h2 id="about-me">About Me</h2>
```

이후 URL 끝에 해시(#)를 포함해 해당 `id`를 적어 이동합니다.

```html
<p>
  저에 대한 더 많은 정보는
  <a href="#about-me">About Me</a>
  를 확인해주세요
</p>
```

### 링크 작성법

링크가 걸린 텍스트는 링크될 내용을 요약하고 있는 것이 좋습니다.

- 스크린 리더 사용자들은 링크를 통해 문맥을 이동합니다.

- 검색 엔진은 링크 텍스트를 사용해 파일을 인덱싱합니다.

- 일반 사용자들에게는 모든 단어를 읽는 것보다 키워드로 요약된 링크 텍스트가 훨씬 유용합니다.

다음은 좋은 예시와 그렇지 않은 예시입니다.

- Good : <a>Download Firefox</a>

- Bad : <a>Click here</a> to download Firefox

이어서 추가적인 팁들입니다.

- 링크 텍스트에 URL을 직접 넣지 않아야 합니다. 사용자가 URL을 직접 읽는 것은 가독성에 좋지 않습니다.

- 링크 텍스트에 '링크(link)'나 '링크로 이동(links to)'이라고 쓰지 않도록 합니다. 링크는 일반적으로 다른 색상, 밑줄로 스타일링 되며 화면 판독기 또한 링크가 있다고 알려주기 때문에 의미만 중복될 뿐입니다.

- 화면 판독기는 링크 텍스트 전체를 해석하므로 링크 텍스트는 가능한 짧게 적는 것이 좋습니다.

HTML이 아닌 다운로드(ex. PDF)나 스트리밍 되는 리소스에 대한 링크는 명확한 설명 문구를 추가해야 합니다.

- <a>Download the sales report (PDF, 10MB)</a>

브라우저에서 열지 않고 다운로드할 리소스에 링크를 연결하는 경우 `download` 속성으로 파일이 저장될 이름을 지정할 수 있습니다.

```html
<a
  href="https://example.com/download"
  download="product-64bit-installer.exe">
  Download product (64bit)
</a>
```

<br />

## 텍스트 표현(심화)

### 설명 목록(Description List)

목록의 종류 중에서 앞서 살펴본 순서가 있는 목록(`<ol>`), 순서가 없는 목록(`<ul>`) 외에도 설명 목록(`<dl>`)이 존재합니다.

`<dl>`의 사용 목적은 용어나 정의의 설명, 질문 및 답변처럼 특정 항목에 대해 관련 설명을 표시하기 위함입니다.

`<dl>`의 구성 요소는 다음과 같습니다.

- `<dt>` : 설명하고자 하는 용어(description term)

- `<dd>` : 용어에 대한 설명(description definition)

```html
<dl>
  <dt>soliloquy</dt>
  <dd>
    드라마에서 등장인물이 혼잣말을 하며 내면의 생각이나 감정을 표현하고 그
    과정에서 청중에게 전달합니다.
  </dd>
  <dt>monologue</dt>
  <dd>
    드라마에서 등장인물이 자신의 생각을 큰 소리로 말하여 청중 및 다른 등장인물과
    공유하는 것을 말합니다.
  </dd>
</dl>
```

하나의 용어에 여러 개의 설명이 포함될 수 있습니다.

```html
<dl>
  <dt>aside</dt>
  <dd>
    드라마에서 캐릭터가 유머러스하거나 극적인 효과를 위해 청중에게만 의견을
    공유하는 경우. 일반적으로 느낌, 생각 또는 추가 배경 정보입니다.
  </dd>
  <dd>
    서면에서는 현재 주제와 관련되어 있지만 콘텐츠의 주요 흐름에 직접 들어가지
    않으므로 근처에 표시됩니다.
  </dd>
</dl>
```

### 인용(Quotation)과 출처(Citation)

인용구는 블록 레벨 또는 인라인 요소인지에 따라 다르게 표시됩니다.

블록 레벨 컨텐츠(문단, 리스트 등)가 인용된 경우 `<blockquote>`로 감싸고 `cite` 속성에 출처를 표기합니다. 브라우저의 기본 스타일은 블록 인용구를 들여쓰기 된 문단으로 나타냅니다.

```html
<blockquote
  cite="https://www.example.com">
  <p>
    블록 인용구 예시
  </p>
</blockquote>
```

인라인 인용구는 `<q>`를 사용합니다. 브라우저 기본 스타일은 인라인 인용구를 따옴표로 묶은 일반 텍스트로 나타냅니다.

```html
<p>
  <q cite="https://www.example.com">
    단락 나누기가 필요 없는 짧은 인용구를 위한 것입니다.
  </q>
</p>
```

`cite` 속성은 안타깝게도 브라우저, 스크린 리더 등에서 활용 가치가 적습니다. 특별히 스타일을 추가하지 않는 이상 브라우저는 `cite` 컨텐츠를 화면에 표시할 방법이 없습니다.

이를 위해 `<cite>`를 사용할 수 있습니다. 본래 `<cite>`는 출처의 제목을 나타내기 위한 것이나 일반 텍스트에 연결해도 문제가 없습니다. 브라우저 기본 스타일은 `<cite>`를 이탤릭체로 나타냅니다.

```html
<a href="https://www.example.com">
  <cite>출처 예시 사이트</cite>
</a>
```

### 약어(Abbreviation)

약어를 포함할 경우 `<abbr>`를 사용합니다. 약어가 상당히 단축됐다면 용어의 전체 풀이를 `title` 속성의 값으로 제공합니다.

```html
<abbr
  title="HyperText Markup Language">
  HTML
</abbr>
```

이전 버전의 HTML에는 `<acronym>`이 있었지만 약어와 두문자어를 모두 표현하기 위해 `<abbr>`의 사용을 선호함에 따라 HTML 스펙에서 제거되었습니다. `<acronym>`는 사용해서는 안됩니다.

### 연락처(Contact)

`<address>`를 이용해 연락처 세부 정보를 표시할 수 있습니다.

```html
<address>
  <p>대한민국 서울시</p>

  <ul>
    <li>전화: 010-1234-5678</li>
    <li>이메일: me@gmail.com</li>
  </ul>
</address>
```

`<address>`는 인접한 `<article>` 또는 `<body>`에 포함된 연락처 정보를 제공할 때만 사용해야 합니다. 예를 들면 사이트 꼬리말의 전체 사이트 연락처 정보, 문서 내부의 작성자 연락처 정보와 같은 것들입니다.

### 위/아래 첨자(Superscript / Subscript)

날짜, 화학식, 수학 방정식과 같은 항목을 표현할 때 필요한 위/아래 첨자는 `<sup>`과 `<sub>`으로 나타냅니다.

- 20<sup>th</sup> birthday

- H<sub>2</sub>O

- a<sup>2</sup>+b<sup>2</sup>=c<sup>2</sup>

### 컴퓨터 코드

- `<code>` : 일반적인 코드를 표시합니다.

- `<pre>` : 공백을 유지하기 위해 사용합니다. 텍스트 편집기에서 들여쓰기 또는 초과 공백을 사용하면 브라우저가 이를 무시하고 렌더링 된 페이지에 공백을 표시하지 않습니다. 그러나 `<pre>`를 사용하면 텍스트 편집기에서 보는 것과 동일한 결과를 렌더링합니다.

- `<var>` : 변수명을 명확하게 표시합니다.

- `<kbd>` : 키보드 입력(input)을 표시합니다.

- `<samp>` : 프로그램 출력(output)을 표시합니다.

아래는 사용 예시와 그 결과입니다.

- 예시 1

```html
<pre>
  <code>
    const number = 1;
  </code>
</pre>
```

<pre>
  <code>
    const number = 1;
  </code>
</pre>

- 예시 2

```html
<p>
  변수 <var>number</var>에 할당된 값은 숫자 1입니다.
</p>
```

<p>
  변수 <var>number</var>에 할당된 값은 숫자 1입니다.
</p>

- 예시 3

```html
<pre>
  $ <kbd>ls</kbd>
  <samp>index.html  README.md</samp>
</pre>
```

<pre>
  $ <kbd>ls</kbd>
  <samp>index.html  README.md</samp>
</pre>

### 시간과 날짜

현실에서 시간과 날짜를 표현하는 방법은 여러가지가 있습니다.

- 26 December 2023

- 26th December 2023

- December 26 2023

- 12/26/2023

그러나 컴퓨터가 위와 같은 형식을 모두 인식하는 것은 쉽지 않습니다. 이를 위해 시간과 날짜를 기계가 읽을 수 있는 형식(machine-readable)으로 제공하는 `<time>`이 있습니다.

```html
<time datetime="2023-12-26">2023년 12월 26일</time>
<time datetime="2023-12">2023년 12월</time>
<time datetime="12-26">12월 26일</time>
<time datetime="09:30">09:30</time>
<time datetime="2023-12-26T09:30">2023년 12월 26일 09:30am</time>
```

<br />

## 문서 및 웹사이트 구조

### 문서의 기본 섹션(Section)

대부분의 웹 페이지는 비슷한 구성 요소(component)로 이루어져 있습니다. 그러나 풀스크린을 이용한 비디오 또는 게임, 미적인 부분을 강조하기 위해 구조를 변경한 페이지의 경우에는 다를 수 있습니다.

- header : 페이지의 최상단에 위치하는 영역입니다. 같은 사이트 내의 다른 웹 페이지로 이동해도 형태를 유지합니다. 일반적으로 큰 제목, 로고 등으로 구성합니다.

- navigation bar : 페이지의 메인 섹션으로 연결되는 링크들의 모음입니다. header와 마찬가지로 다른 페이지로 이동해도 형태를 유지합니다. 많은 경우에 navigation bar를 header 내부에 포함시키지만, 이는 선택에 따라 다릅니다. 실제로 두 영역을 분리하면 화면 판독기가 더 잘 인식하기 때문에 접근성 측면에서 이점을 갖는다는 의견도 있습니다. 일반적으로 메뉴 버튼, 링크 등으로 구성합니다.

- main content : 페이지의 중앙에 위치하는 영역입니다. 사용자(방문자)에게 전달하고자 하는 핵심 컨텐츠를 포함하며 각 페이지마다 고유한 내용을 담고 있습니다.

- sidebar : 페이지의 좌변 또는 우변에 위치하는 영역입니다. 일반적으로 부가 정보, 링크, 인용문, 광고 등으로 구성합니다.

- footer : 페이지의 최하단에 위치하는 영역입니다. 메인 컨텐츠에 비해 중요하지 않은 정보를 포함합니다. 일반적으로 아주 자잘한 세부 정보, 저작권 고지, 연락처 등으로 구성합니다. SEO를 목적으로 사이트에서 자주 찾거나 인기 있는 컨텐츠로 연결하는 링크를 제공하기도 합니다.

전형적인 웹 페이지는 다음과 같이 구성될 수 있습니다.

![webpage](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure/sample-website.png)

### 컨텐츠 구조화

앞서 다루었듯이, 각 컨텐츠는 의미론적으로(semantic) 올바른 역할을 가지고 있어야 하며 그에 맞는 요소를 사용해야 합니다.

의미론적인 구조 없이 CSS만으로도 위의 웹 페이지 예시처럼 만드는 것은 충분히 가능합니다. 하지만 단지 시각적으로 꾸밀 뿐이라면, 시각 정보를 정상적으로 얻을 수 없는 사람들에게는 페이지가 상당히 난해할 것입니다. 질병관리청에 따르면 우리나라 인구 중 남자의 5.9%, 여자의 0.44%가 선천적 색각 이상을 갖고 있습니다. 서양의 경우 남자의 8%, 여자의 0.5%가 색각 이상입니다. 또한 시각 장애가 있는 사람은 세계 인구의 약 4~5%를 차지합니다.

다음은 의미론적 마크업을 위한 전용 태그들입니다.

- header : `<header>`

- navigation bar : `<nav>`

- main content : `<main>`, 하위 섹션으로 `<section>`, `<article>`, `<div>`를 사용할 수 있습니다.

- sidebar : `<aside>`, 주로 `<main>` 내부에 위치합니다.

- footer : `<footer>`

### 레이아웃 요소

위의 전용 태그들에 대해 레이아웃을 고려한 조금 더 자세한 설명입니다.

- `<main>` : 해당 페이지만의 고유 컨텐츠를 위한 요소입니다. 페이지당 한 번만 사용해야 하고 `<body>`의 바로 밑 자식 요소로 넣습니다. 다른 요소 내부에 중첩되지 않아야 합니다.

- `<article>` : 그 자체로 의미를 가지는 컨텐츠 블록입니다. 페이지의 다른 부분에 의존적이지 않고 단독적으로 쓰일 수 있습니다.

- `<section>` : 그 자체로 의미를 가진다는 점에서 `<article>`과 비슷하지만 페이지를 하나의 같은 기능을 기준으로 그룹핑할 때 사용합니다. 한 `<section>`을 여러 `<article>`로 나눌 수 있고, 한 `<article>`을 여러 `<section>`으로 나눌 수도 있습니다. 각 `<section>`의 내용은 `<heading>`으로 시작하는 것이 좋습니다.

- `<aside>` : 메인 컨텐츠와 직접적이 아닌 간접적으로 관련된 추가 정보를 제공합니다. 용어집, 저자 약력, 관련 링크 등이 포함됩니다.

- `<header>` : 컨텐츠 소개에 관련된 요소 그룹을 담는 블록입니다. `<body>`의 직계 자식으로 쓰였다면 페이지의 글로벌 헤더 용도이지만 `<article>`이나 `<section>`의 자식으로서 특정 섹션의 헤더로 쓰이기도 합니다.

- `<nav>` : 주요 페이지 또는 컨텐츠로 이동하는 기능을 가집니다. 부가 정보, 링크 등은 포함되지 않습니다.

- `<footer>` : 페이지에서 컨텐츠의 끝을 나타냅니다.