learning address : https://roadmap.sh/best-practices/frontend-performance

### High Priority

## Minimize number of iframes

- iframe 을 지양해라

iframe 은 성능 및 접근성과 유용성에도 좋지 않다.  
검색 엔진에 의해 인덱싱이 되지도 않는다.

## Minified CSS - Remove comments, whitespaces etc

- css 를 축소하라

css 파일을 축소하면 용량이 줄어들며 콘텐츠가 더 빨리 로드된다.

## CSS files are non-blocking

- css 를 미리로드해라

"preload" 를 사용할 경우 브라우저 렌더링전에 CSS 파일을 로드할 수 있다.

```html
<link rel="preload" as="style" href="/css/common.css" />
```

## Inline the Critical CSS (above the fold CSS)

- css 부분 추출"

FCP(First Contentful Paint)를 위해서 스크롤하지 않는 페이지에 보이는 부분만 스타일을 분류하려 로드한다.

## Avoid the embedded / inline CSS

- 인라인 CSS 를 지양해라

```html
<!-- html element 에 style 넣는게 inline css -->
<div style="display:flex"></div>
```

## Analyse stylesheets complexity

- CSS 이슈 및 중복을 제거해라

CSS 파일에 중복되는 코드를 제거하여 용량을 줄인다.

## Compress your images / keep the image count low

- 이미지를 최적화해라

이미지를 최적화하여 용량을 줄인다.

## Choose your image format appropriately

- 이미지 형식을 고려해라

Lighthouse 를 사용하여 차세대 형식을 사용할 수 있는 이미지를 식별한다.

## Minify your JavaScrip

- 자바스크립트 축소

불필요한 공백, 주석, 줄 바꿈등을 모두 제거하여 파일크기를 줄인다.

## Non Blocking JavaScript: Use async / defer

- 파싱을 멈추지 말고 JS를 불러와라

`async` `defer` 속성을 이용해서 상황에 맞춰 잘 사용해서 불러온다.

## Use HTTPs on your website

- HTTP 를 사용해라

## Keep your page weight < 1500 KB (ideally < 500 kb)

- 페이지 가중치를 줄여라

이상적으론 500KB 미만이며, 웹 상에 따라 킬로바이트 중앙값은 약 1500KB이다.

## Keep your page load time < 3 seconds

- 페이지 로드 시간을 3초 이내로 줄여라  
  FCP 기준상 3초 이상일 경우 사용자 이탈률이 높아진다.

## Keep the Time To First Byte < 1.3 seconds

- 브라우저 대기 시간을 줄여라

TTFB 를 1.3초 미만으로 유지한다

## Minimize HTTP Requests

- HTTP 요청 최소화

로드하는 모든 파일이 웹 사이트에서 필요한건지 체크 필요

## Serve files from the same protocol

- 동일한 프로토콜 사용

HTTP 는 HTTP 가 사용하고 HTTPS 는 HTTPS 에서 사용해야된다.

## Avoid requesting unreachable files (404)

- 404 예외처리하기

404 에러페이지일 경우 검색엔진에 악영향을 미칠수 있어서 별도의 페이지 제공

## Set HTTP cache headers properly

- HTTP 캐싱

브라우저 서버간의 비용이 많이 들기 때문에 왕복 횟수를 피하기 위해 HTTP 헤더로 캐싱을 한다.

## GZIP / Brotli compression is enabled

- 압축해라

압축을 하여 JS 파일의 크기를 줄여서 성능을 향상시킨다.

### Medium Priority

## Minified HTML - Remove comments and whitespaces

- HTML 축소

공백, 주석, 속성들을 모두 제거하여 HTML의 크기를 줄인다.

## Use Content Delivery Network

- CDN 사용

CDN 을 사용하여 정적 자산을 제공하여 서버의 부하를 줄이고 성능이 향상된다.  
또는 나라별 JS 가져오는 속도에서도 차이가 있었던거 같음

## Prefer using vector image rather than bitmap images

- 벡터 이미시를 선호한다.

벡터 이미지(SVG)는 이미지보다 작은 경향이 있으며, 확장 및 CSS 적용에 좋다.

## Set width and height attributes on images (aspect ratio)

- 이미지의 크기 설정

이미지의 높이와 너비를 설정하면 페이지가 로드 될 때 이미지에 필요한 공간이 예약된다.  
단 설정하지 않았을 경우 모든 적정한 공간을 예약할 수 없으며 페이지 레이아웃이 변경된다.

## Avoid using Base64 images

- base64 이미지는 피하기

1. base64 이미지는 바이너리 이미지보다 크기 떄문에 로딩이 느리다.
2. html, css 에 base64 주소가 들어갈 경우 용량이 커져 로드가 느려진다.
3. base64 는 별도의 리소스가 아니기 때문에 캐싱을 할 수 없다.
4. base64 는 이전 브라우저가 호환이 되지 않을 수도 있다.

## Offscreen images are loaded lazily

- 지연로딩

응답 시간을 개선하고, 사용자에게 필요하지 않을 수 있는 이미지를 로드하지 않는다.

## Ensure to serve images that are close to your display size

- 반응형 이미지

기기별로 뷰포트보다 큰 이미지는 필요하지 않음  
`srcset` `picture` 를 사용한다고 함

## Avoid multiple inline JavaScript snippets <script>

- 인라인 자바스크립트 피하기

HTML body element 사이에 script 태그가 있을 시 페이지 로드 속도가 느려질 수 있음  
만약 사용해야 할 경우 `async` `defer` 를 사용하여 대응할 수 있음

## Keep your dependencies up to date

- 종속성 업데이트

신규 버전에서 최적화 및 보안 수정에 제공되기에 되도록 추천하는 스킬  
또는 `npm-check` 라이브러리로 상태가 확인이 가능하다.

## Check for performance problems in your JavaScript files

- JS 성능 체크

JS 소스가 복잡할 경우 런타임 성능을 저하시킬 수 있으며,  
개발자 도구에서 타임라인에서 스크립트 이벤트를 평가하고 제거

## Service Workers for caching / performing heavy tasks

- 서비스 워커 사용하기

PWA 에서 서비스 워커를 사용하여 데이터 캐싱기능을 해줌

## Cookie size should be less than 4096 bytes

- 쿠키 크기 조절하기(4096Byte 이하)

쿠키는 웹 서버와 브라우저 사이의 HTTP 헤더에서 교환되며,  
크기가 클 경우 응답 시간에 영향을 미칠수 있어서 최대한 크기를 작게 유지해야 한다.

## Keep the cookie count less than 20

- 쿠키 개수 조절(20개 미만)

최대한 적을수록 HTTP 요청에 대한 부담이 줄어드나봄

### Low Priority

## Pre-load URLs where possible

- URL 미리로드

`Prefetching` 을 사용하면 필요한 리소르를 브라우저에서 자동으로 가져올 수 있으며,  
리소스가 캐시에 저장하여 웹 페이지 로드 속도를 높일 수 있다.

## Concatenate CSS into a single file

- CSS 연결

HTTP2 를 사용한다

## Remove unused CSS

- 사용하지 않는 CSS 제거

사용하지 않은 CSS 를 제거하여 파일 크기를 줄일 수 있다.

## Use WOFF2 font format

- WOFF 2.0 웹폰트를 사용하기

구글에서는 WOFF 2.0 웹 글꼴 압축 형식이 WOFF 1.0 에 비해 30% 의 향상된 성능을 제공한다.  
그 다음에 WOFF 2.0 => WOFF 1.0 => TTF 를 사용하는걸 권장하고 있다.

## Use preconnect to load your fonts faster

- 글꼴에 대한 사전 연결

글꼴을 사전에 미리 연결하면 성능 향상을 볼 수 있다.

## Keep the web font size under 300kb

- 웹 글꼴 크기를 300KB 미만으로 유지

글꼴이 많을 수록 다운로드 속도가 느리게 걸려서 렌더링도 느려진다.  
예전에 NotoSansKR 를 사용할 때 많이 사용하는 폰트만 모아둔걸 사용한 적이 있음

## Prevent Flash or Invisible Text

- 플래시 텍스트 방지

웹폰트가 로드될 때 까지 투명한 텍스트는 사용하지 않는다

## Keep an eye on the size of dependencies

- 종속성 크기 확인하기

사용하고 있는 라이브러리의 크기를 확인해서 가벼운 라이브러리 변경 할 수 도 있다.
