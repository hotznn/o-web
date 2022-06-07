# o-web
a Web-Request Module.

## Install
> npm install o-web

# DEMO

normal
```javascript
var web = require('o-web');
+async function(){
  var o = await web.get("https://www.bimwook.com:11180/woo/about.do");
  if(!o.error){
    console.log(o.data.toString());
  }
  else {
    console.log(o.error);
  }
}();
```

POST:
```javascript
var web = require('o-web');
+async function(){
  var body = [];
  body.push("u=bamboo");
  body.push("p=******");
  var o = await web.post("https://www.bimwook.com:11180/woo/about.do", body.join("&"));
  if(!o.error){
    console.log(o.data.toString());
  }
  else {
    console.log(o.error);
  }
}();
```

You can also set headers
```javascript
var web = require('o-web');
+async function(){
  var o = await web.get(
    "https://www.bimwook.com:11180/woo/about.do", 
    {"User-Agent":"Mozilla/5.0 (AS-YOU-WISH)", "Cookie":"foo=bar;"}
  );
  if(!o.error){
    console.log(o.data.toString());
  }
  else {
    console.log(o.error);
  }
}();
```
with proxy
```javascript
var web = require('o-web');
+async function(){
  var o = await web.get("https://www.bimwook.com:11180/woo/about.do", {}, "127.0.0.1:10808");
  if(!o.error){
    console.log(o.data.toString());
  }
  else {
    console.log(o.error);
  }
}();
```

The return object:
```javascript
{
  data:<Buffer>,
  text: <String>,
  error: <error>,
  code: <int>,
  headers: <object>
}
```
That's All.
