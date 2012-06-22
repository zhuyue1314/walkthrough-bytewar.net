#### Level 12

First we need to bypass that User-Agent check, the easiest way to do this is in Firefox. Write about:config in the address bar.
Now search for  "useragent" and change the value of "general.useragent.extra.firefox" to "bytewar".
Now try to enter level 12 again, and after you are done you can change it back to default by clicking "reset" :)

Okey, we get sent to the website of a hate group and are suppose to crack their site. First thing we check is the admin link, but we need username and password.
The admin folder are protected with htaccess, so we need to get the info from the htpasswd file which htaccess uses.

So how are we suppose to read that file? Well their site uses page including, which we may exploit if the script are not secured enough.
Lets try to include the .htaccess file through the page include script:
http://bytewar.net/levels/12/hate/index.php?page=admin/.htpasswd

Didn't work, but no need to give up yet. The script can add a string at the end like this:

<pre class="brush: php;">
include($_GET['page'] . '.php');
</pre>

We can kill that by adding "?" at the end which will tell php that whats behind the question mark are GET values.
http://bytewar.net/levels/12/hate/index.php?page=admin/.htpasswd?

and the file got included...

```
admin:$apr1$iOOBL...$JfAc7xtWiPh0Mlj.dNS8Y.
```

Now we need to crack the password.
It's a md5 (APR) hash and you can crack it with this program: <a href="http://hashcrack.blogspot.com/">OclHashcat-GUI</a>