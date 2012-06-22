#### Level 1

View the source (ctrl+u) in most browsers and you will see this:
```javascript
function test(passwd) {
    if (passwd == "easy") {
    location.href = "?page=levels&level=1&pw=" + passwd;
}
else {
    location.href = "?page=error";
}
}
```

You can easily see that the password is "easy".