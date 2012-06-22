#### Level 3

So here we need Westlife to get over 10000 points in just one vote, there are meny ways to solve this level, but the easiest was is to go in and change the html manually.
I used Google Chrome's Developer Tool (Shift+Ctrl+I). Go in and change the value of the select-input like I did in this image:

```html
<select name="vite">
    <option value="1">1</option>
    <option value="2">2</option>
    <option value="3">3</option>
    <option value="4">4</option>
    <option value="10000">5</option>
```
After you have changed the value to 10000 click on the page and choose number 5 on the select-input and then hit submit.