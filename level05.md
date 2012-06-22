#### Level 5

In the source we see a comment that says which file to look in, it's called "levels/5/check.php".
Lets take a look (<a href="http://bytewar.net/levels/5/check.php">http://bytewar.net/levels/5/check.php</a>) In the source we see styling, but also some numbers if we look closely.
But why are not the numbers shown on the presentation page? There is a html tag named noscript that will cause this effect.
Copy the source and paste it into a new txt-file. Hit Ctrl+F and remove the noscript-tags. Save the file as .html and open with your browser.
```
011010000110010101111001
```
You can clearly see that this is binary so lets go and decode it: http://www.nickciske.com/tools/binary.php

And there you got the password!