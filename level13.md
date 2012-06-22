#### Level 13

We see a php error which tells us that the script is trying to include "username.phpp", which is a typo. So now we know that username.php is important. We aslo see a "remember me" checkbox which tells us that this levels are using cookies.

Trying to go directly to the file worked: 
http://bytewar.net/levels/13/

Got nothing from username.php at first, but when the source was viewed I discovered another typo which let me see the source.

```php
<PHP
$username = "admin2"; 
?>
```

So now we got the username, lets find the password. As I said before "remember me" functions use cookies, so lets check the cookies.
Write javascript:alert(document.cookie); in the address bar.
This is it:
```
bytewar_remember_me = 865b02aab501e77c8ca524c9bc1cf5c4
```

This is clearly a md5 hash and we can find the value of it by bruteforcing it. The easiest way is to use an online bruteforce tool like http://www.cmd5.org/default.aspx

There you go!
