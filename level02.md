#### Level 2

The popup prompt are in the way for viewing the source, so we will write this in the address bar: 
"view-source:http://bytewar.net/?page=levels&level=2"

In the source we find:
```javascript
password=prompt('LEVEL: 2\n Enter password:','');
 
var a = "newbie";
var b = a.substring(0,3);
 
if (password == b) {
    location.href= "?page=levels&level=2&pw=" + password; 
} else { 
    location.href= "?page=error"; 
}
```

At first sight most people will try "newbie" as the password, but it's not. Substring(0,3) means that we take the first three characters from our "newbie" string, which will return "new" and thats the password.
