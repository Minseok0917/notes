learning address : https://roadmap.sh/best-practices/frontend-performance

## High Priority

### Minimize number of iframes

- iframe 을 지양해라

iframe 은 성능 및 접근성과 유용성에도 좋지 않다.  
검색 엔진에 의해 인덱싱이 되지도 않는다.

### Minified CSS - Remove comments, whitespaces etc

- css 를 축소하라

css 파일을 축소하면 용량이 줄어들며 콘텐츠가 더 빨리 로드된다.

### CSS files are non-blocking

- css 를 미리로드해라

"preload" 를 사용할 경우 브라우저 렌더링전에 CSS 파일을 로드할 수 있다.

```html
<link rel="preload" as="style" href="/css/common.css" />
```

### Inline the Critical CSS (above the fold CSS)

- css 부분 추출"

FCP(First Contentful Paint)를 위해서 스크롤하지 않는 페이지에 보이는 부분만 스타일을 분류하려 로드한다.

### Avoid the embedded / inline CSS

- 인라인 CSS 를 지양해라

```html
<!-- html element 에 style 넣는게 inline css -->
<div style="display:flex"></div>
```

### Analyse stylesheets complexity

- CSS 이슈 및 중복을 제거해라

CSS 파일에 중복되는 코드를 제거하여 용량을 줄인다.

### Compress your images / keep the image count low

- 이미지를 최적화해라

이미지를 최적화하여 용량을 줄인다.

### Choose your image format appropriately

- 이미지 형식을 고려해라

Lighthouse 를 사용하여 차세대 형식을 사용할 수 있는 이미지를 식별한다.

### Minify your JavaScrip

- 자바스크립트 축소

불필요한 공백, 주석, 줄 바꿈등을 모두 제거하여 파일크기를 줄인다.

### Non Blocking JavaScript: Use async / defer

- 파싱을 멈추지 말고 JS를 불러와라

`async` `defer` 속성을 이용해서 상황에 맞춰 잘 사용해서 불러온다.

### Use HTTPs on your website

- HTTP 를 사용해라

### Keep your page weight < 1500 KB (ideally < 500 kb)

- 페이지 가중치를 줄여라

이상적으론 500KB 미만이며, 웹 상에 따라 킬로바이트 중앙값은 약 1500KB이다.

### Keep your page load time < 3 seconds

- 페이지 로드 시간을 3초 이내로 줄여라  
  FCP 기준상 3초 이상일 경우 사용자 이탈률이 높아진다.

### Keep the Time To First Byte < 1.3 seconds

- 브라우저 대기 시간을 줄여라

TTFB 를 1.3초 미만으로 유지한다

### Minimize HTTP Requests

- HTTP 요청 최소화

로드하는 모든 파일이 웹 사이트에서 필요한건지 체크 필요

### Serve files from the same protocol

- 동일한 프로토콜 사용

HTTP 는 HTTP 가 사용하고 HTTPS 는 HTTPS 에서 사용해야된다.

### Avoid requesting unreachable files (404)

- 404 예외처리하기

404 에러페이지일 경우 검색엔진에 악영향을 미칠수 있어서 별도의 페이지 제공

### Set HTTP cache headers properly

- HTTP 캐싱

브라우저 서버간의 비용이 많이 들기 때문에 왕복 횟수를 피하기 위해 HTTP 헤더로 캐싱을 한다.

### GZIP / Brotli compression is enabled

- 압축해라

압축을 하여 JS 파일의 크기를 줄여서 성능을 향상시킨다.
