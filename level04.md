#### Level 4

View the source again with the view-source method I described on level 2 and you will find this JavaScript:

```javascript
<script language="JavaScript" type="Text/JavaScript" src="www.bytewar.net/levels/4/password.js"></script>
<script language="JavaScript" type="Text/JavaScript">
password=prompt('LEVEL: 4\n Enter password:','');
if (password == unescape(this_is_the_pw)) {
    location.href = "?page=levels&level=4&pw=" + password;
} else {
    location.href = "?page=error";
}
</script>
```

"this_is_the_pw" is not the password, but a variable which you need to find the value of. 
We see the unescape() function which means that the password is in hex. But where is the value of this_is_the_pw?

Well we see that an external JavaScript file is included. "www.bytewar.net/levels/4/password.js", lets check it out: `"don't believe in everything you see..."`

Many get fooled by this, because when people see "www" they think it's a domain name, but it's actually a folder name. So when we go to "http://bytewar.net/www.bytewar.net/levels/4/password.js" instead we get the real thing:

```javascript
var this_is_the_pw = "%72%6F%66%6C";
```

Now go to http://www.nickciske.com/tools/hex.php and write %72%6F%66%6C in the hex field and hit decode.

Done.