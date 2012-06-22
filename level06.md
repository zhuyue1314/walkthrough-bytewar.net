#### Level 6

We take a look at the source again with "view-source:" in front of the url in the address bar again and we find:

```javascript
x=prompt('LEVEL: 6\n Enter password:','');
x=new String(x + " z");
var y = "1338";
var z = "1";
var f = "y - z";
if (x == f) { 
    location.href = "?page=levels&level=6&pw=" + x;
} else {
    location.href = "?page=error";
}
```

Many will get fooled by this thinking the password is 1338 - 1 which returns 1337. But "y - z" is a text string, not integer.
So the password is basicaly "y - z", but when we try it, we fail. This is bacause of this: 
```javascript
x=new String(x + " z");
```

This means that what we write into the password promt gets a " z" tail behind it, but the result is suppose to be "y - z" so if we just write "y -" into the promt it will return "y - z".

So the password is then "y -" :)