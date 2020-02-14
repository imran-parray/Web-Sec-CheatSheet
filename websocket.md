# Testing Cross site Websocket Hijacking

- Open burp and Go to `proxy >> websockets History`

- Go to web page which is using the webSockets [Refresh the page if you already on the same page]

- In `proxy >> websockets History` tab click on any request and Copy the URL

- Now go to <http://websocket.org/echo.html>

- Paste the URL in their and Click Connect to Connec to the websocket

- Once the connection is established you must be able to send frames to the server from this page.
Capture the websocket frames using burp proxy from a valid session and send them to see how the
server responds. If the server responds in the same way as it did for the valid session then it
most likely is vulnerable to Cross-Site WebSocket Hijacking

- Now Play around the web app to find Commands which can be send through the WebSocket to perform the most critical attack.

-Use this code as an POC

```js

websocket = new WebSocket('wss://ac141f3e1e2fb2d98039035e00f300ef.web-security-academy.net/chat')
websocket.onopen = start
websocket.onmessage = handleReply
function start(event) {
  websocket.send("READY");
}
function handleReply(event) {
  console.log(event.data)
}


```


Refrences:

<https://portswigger.net/web-security/websockets>

<https://medium.com/@sharan.panegav/account-takeover-using-cross-site-websocket-hijacking-cswh-99cf9cea6c50>
