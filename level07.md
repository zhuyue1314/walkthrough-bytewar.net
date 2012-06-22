#### Level 7

View the source and we find this JavaScript:

```javascript
function test(passwd) {
y=String.fromCharCode(115) + String.fromCharCode(101) + String.fromCharCode(passwd.substring(0,1)*11) + String.fromCharCode(114) + String.fromCharCode(101) + String.fromCharCode((passwd.substring(0,1)*13)-1);
if (passwd.substring(1,7) == y) { 
    location.href = "?page=levels&level=7&pw=" + passwd;
} else {
    location.href = "?page=error";
}
}
```

Don't be afraid, it's not as hard as it seems.
First String.fromCharCode() returns the ASCII value of an integer, and some of these values can be collected without doing anything else:

```javascript
String.fromCharCode(115) = "s"
String.fromCharCode(101) = "e"
String.fromCharCode(114) = "r"
String.fromCharCode(101) = "e"
```
We can set it up like this: se?re? - We also see that the first char in the password must be an integer since the script multiplies it with other numbers. And since it's just the first char (integer) it's using only the combination of 0-9.

Then we can bruteforce this shit.

```javascript
var i = 0;
while(i < 10) {
    document.write(i);
    document.write(
    String.fromCharCode(115) +
    String.fromCharCode(101) +
    String.fromCharCode(i*11) + 
    String.fromCharCode(114) +
    String.fromCharCode(101) +
    String.fromCharCode((i*13)-1));
    document.write("<br />\n");
    i++;
}
```

Run this in your browser and it will return:
```
1sere
2sere
3se!re&
4se,re3
5se7re@
6seBreM
7seMreZ
8seXreg
9secret
```

No doubt what the password is.