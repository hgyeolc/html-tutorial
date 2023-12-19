# HTML Practice Note

## 개요
HTML에 대해 학습 및 실습한 내용을 적습니다. MDN 사이트의 HTML 튜토리얼을 참고했습니다.
- https://developer.mozilla.org/ko/

## HTML ?
HTML(Hypertext Markup Language)은 웹 페이지와 그 내용을 구조화하기 위해 사용하는 마크업 언어입니다. 특정 컨텐츠를 생성 또는 수정하거나 또다른 페이지를 하이퍼링크로 연결하여 이동할 수 있습니다.

### 요소(Element)
웹 페이지 구조는 일련의 요소로 이루어져 있으며 태그(Tag)로 감싸 나타냅니다. 

![element](https://developer.mozilla.org/ko/docs/Learn/Getting_started_with_the_web/HTML_basics/grumpy-cat-small.png)

어떤 요소는 속성(Attribute)을 가질 수 있습니다.

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

### 빈(Empty) 요소
어떤 요소들은 내용을 갖지 않습니다.

```html
<img src="" />
<link />
<meta />
```

종료 태그가 따로 존재하지 않고 시작 태그만으로 작성합니다.

다만, 시작 태그의 뒷쪽에 슬래시(/)를 붙여 종료임을 표시합니다. 대부분의 경우 슬래시를 작성하지 않아도 문제 없이 동작하지만(브라우저가 HTML을 해석할 때 자동으로 슬래시를 붙여 동작), 브라우저의 해석이 언제나 올바른 것만은 아닙니다. 따라서 예기치 않은 오류를 피하기 위해 슬래시를 명시적으로 작성하는 것을 권장합니다.

### HTML5 기본 템플릿
에밋(Emmet)으로 작성되는 HTML5의 기본 템플릿은 다음과 같습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta 
    name="viewport"
    content="width=device-width"
  />
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