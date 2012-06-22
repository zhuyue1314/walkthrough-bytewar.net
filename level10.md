#### Level 10

We get an alert which tells us to find where it comes from.
By looking at the source it should be at levels/10/src.php (http://bytewar.net/levels/10/src.php) but if you open it you get a 404 (file not found).
But lets find out whats really going on here, the alert must come from somewhere.

I opened Chrome's Developer Tool and clicked the scripts tab and reloaded the page. Then I selected the src.php and this is what I found:

```
/* "let_me_in" */
alert('the password is at the same place as this alert');
```

There you have the password. "let_me_in".