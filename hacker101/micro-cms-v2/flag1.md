### hints
* What actions could you perform as a regular user on the last level, which you can't now?
* Just because request fails with one method doesn't mean it will fail with a different method
* Different requests often have different required authorization

### solution

the second hint is what gave this one away!

my go-to for these scenarios is curl but it worked with postman as well so seems like any preferred tool will work.

1. GET request redirects to login page:
   * `curl https://ip.addr.ess/some_hash/page/edit/1`
2. POST request gets you the flag:
   * `curl -X POST https://ip.addr.ess/some_hash/page/edit/1`

### revised solution

1. open burp suite and in *Proxy > Intercept* tab, make sure intercept is **on**
2. back on the browser, navigate to an edit page by either selecting the option from a page or by manually updating the url
   * .../page/edit/1
3. there will be a request waiting for you in burp suite in the *Proxy > Intercept* tab
4. change the request from GET to POST and click **Forward**
5. the flag will appear on the browser!
