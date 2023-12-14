---
{"dg-publish":true,"permalink":"/my-project/express-routing/","dgPassFrontmatter":true,"created":"2023-12-13T17:50:08.559+09:00","updated":"2023-12-14T17:17:56.431+09:00"}
---

# What Is Routing
- URI 및 특정 엔드포인트에 대한 클라이언트 요청에 애플리케이션 응답 방법
- 하나 이상의 핸들러 함수를 가질 수 있으며, 라우트가 일치할 때 실행
## Route Structure
```javascript
app.METHOD(PATH, HANDLER)
```
- app : express 인스턴
- METHOD : HTTP 요청 메소드
- PATH : 서버에서의 경로
- HANDLER : Route가 일치할 실행되는 함수
## Route Method
- 라우트 메소드는 HTTP 메소드 중 하나로부터 파생되며, `express` 클래스의 인스턴스에 연결
- Express에서 지원하는  HTTP 메소드
>[!note] HTTP Method 종류
>`get`, `post`, `put`, `head`, `delete`, `options`, `trace`, `copy`, `lock`, `mkcol`, `move`, 
>`purge`, `propfind`, `proppatch`, `unlock`, `report`, `mkactivity`, `checkout`, `merge`,
> `m-search`, `notify`, `subscribe`, `unsubscribe`, `patch`, `search`,  `connect`
-  `app.all()`은 어떠한 HTTP 메소드로부터도 독립
## Route Path
- 요청 메소드와 조합해 요청이 이루어질 수 있는 엔드포인트를 정의
- 라우트 경로는 문자열, 문자열 패턴 또는 정규식일 수 있습니다.
## Route Handler
- 여러 콜백 함수를 제공하여 요청을 처리
- 조건에 `next()`를 지정하여 나머지 콜백함수를 우회가능
- 함수, 함수의 나열, 정의된 함수의 배열 통해서도 Handler 지정가능
- Express에서 지원하는  응답(res) 메소드
>[!note] HTTP Method 종류
>
|메소드|설명|
|---|---|
|[res.download()](https://expressjs.com/ko/4x/api.html#res.download)|파일이 다운로드되도록 프롬프트|
|[res.end()](https://expressjs.com/ko/4x/api.html#res.end)|응답 프로세스를 종료|
|[res.json()](https://expressjs.com/ko/4x/api.html#res.json)|JSON 응답을 전송|
|[res.jsonp()](https://expressjs.com/ko/4x/api.html#res.jsonp)|JSONP 지원을 통해 JSON 응답을 전송|
|[res.redirect()](https://expressjs.com/ko/4x/api.html#res.redirect)|요청의 경로를 재지정|
|[res.render()](https://expressjs.com/ko/4x/api.html#res.render)|보기 템플리트를 렌더링|
|[res.send()](https://expressjs.com/ko/4x/api.html#res.send)|다양한 유형의 응답을 전송|
|[res.sendFile()](https://expressjs.com/ko/4x/api.html#res.sendFile)|파일을 옥텟 스트림의 형태로 전송|
|[res.sendStatus()](https://expressjs.com/ko/4x/api.html#res.sendStatus)|응답 상태 코드를 설정한 후 해당 코드를 문자열로 표현한 내용을 응답 본문으로서 전송|
# app.route()
## What is Route()
- Route Path에 대하여 Chain 가능한 Route Handler를 작성하게 해주는 기능
## Code
```javascript
app.route('/book')
  .get(function(req, res) {
    res.send('Get a random book');
  })
  .post(function(req, res) {
    res.send('Add a book');
  })
  .put(function(req, res) {
    res.send('Update the book');
  });
```
- 동일한 라우트 경로에서 분기된 다른 Route Method를 통해 Route Handler를 체인
# express.Router
## What is express.Router
- 모듈 마운팅 핸들러 작성 Class
- Route Pathe에 의한 일종의 “mini-app”
- main js(app.js, index.js)에서 Router모듈을 express 객체의 .use(path, Router)로드
## Code
>[!note] birds.js
>```javascript
>var express = require('express');
>var router = express.Router();
>
>//middleware that is specific to this router
>router.use(function timeLog(req, res, next) {
>	console.log('Time: ', Date.now());
>	next();
>});
>// define the home page route
>router.get('/', function(req, res) {
>	res.send('Birds home page');
>});
>// define the about route
>router.get('/about', function(req, res) {
>	res.send('About birds');
>});
>
>module.exports = router;
>```

>[!note] app.js
> ```javascript 
> var birds = require('./birds');
> ...
> app.use('/birds', birds);
> ```



