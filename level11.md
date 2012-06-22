#### Level 11

Time for flash! 
The source tells us the location of the flash file:
```html
<embed src="levels/11/hackme2.swf" quality="high" pluginspage="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" width="145" height="75"></embed>
```

view-source:http://bytewar.net/levels/11/hackme2.swf gave us jibberish. So we have to decomile it.
Download the flash file (save page as) and then download Flare (google it). Flare is multiplatform so you can download it for Win, Mac or Linux and it's really easy to use, no worries.

When you have decompiled it you will get a file named hackme2.flr with a lot of code, but the only code we are interested in is this:

```actionscript
  frame 1 {
    function validate() {
      var v1 = _root;
      if (v1.password == (pass.reverse()).join('')) {
        getURL('?page=level22&pw=' + v1.password, '');
      } else {
        v1.gotoAndPlay(2);
      }
    }

    Stage.scaleMode = 'noScale';
    var pass = ['y', 's', 'a', 'e', 's', 'a', 't', 'o', 'n'];
    Key.addListener({'onKeyDown': function () {
      if (Key.getCode() == 13) {
        validate();
      }
    }});
    stop();
  }
```

and we can narrow it down even more...

```actionscript
var pass = ['y', 's', 'a', 'e', 's', 'a', 't', 'o', 'n'];
pass.reverse()).join('')
```

You should see what the password is by now, but to explain whats going on here:
The object "pass" is an array, join('') implodes the array into a string and glues it with nothing which gives us "ysaesaton" and reverse() just... yes, reverses it: notaseasy
