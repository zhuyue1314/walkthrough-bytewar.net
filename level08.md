#### Level 8

In the source you will see that an external JavaScript file is included: http://bytewar.net/levels/8/l23.php

Relax the level is not broken, it's a fake 404 file. View the source of it and you will find: "You got the password to access the next level stored on your computer, good search"

Time to check cookies... In the address bar write `javascript:alert(document.cookie);`

You will see at the bottom: `access=look_in_your_head...`

"Head..." means header. There are many ways to view the header information, but I used Google Chrome Developer Tool. Hit Shift+Ctrl+I and goto resources and select /?page=levels&level=8

Look at the response headers:

```
Cache-Control:no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Connection:Keep-Alive
Content-Type:text/html
Date:Fri, 19 Mar 2010 19:55:58 GMT
Expires:Thu, 19 Nov 1981 08:52:00 GMT
Keep-Alive:timeout=5, max=100
Pragma:no-cache
Server:Apache
The_password_is:ohyeah
Transfer-Encoding:chunked
X-Powered-By:PHP/5.2.12
```

And there you go :)