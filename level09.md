#### Level 9

We look in the source again and find:

```javascript
x=prompt('LEVEL: 9\n Enter password:','');
if ( !((017232200000>>eval('0x'+x)) - (0xC3D*x+7)) ) {
    location.href = "?page=levels&level=9&pw=" + x;
} else {
    location.href = "?page=error";
}
```

The simplest way is to just bruteforce it, and thats what we will do...

```javascript
var x = 0;
while(x < 1000000) {
    if ( !((017232200000>>eval('0x'+x)) - (0xC3D*x+7)) ) {
        alert(x);
        break;
    }
    x++;
}
```

Just run the script in the JavaScript console in your browser and you will get the answer :)