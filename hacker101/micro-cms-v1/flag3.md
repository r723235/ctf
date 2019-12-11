### hint
* Script tags are great, but what other options do you have?

### solution

a shoutout to [kylie stradley](https://git.rsglab.com/kylie-stradley) for sharing this page: https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet

for this flag, the [on error alert](https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet#On_error_alert) test is used

1. edit or create a page
2. in the body, enter `<IMG SRC=/ onerror="alert(String.fromCharCode(88,83,83))"></img>`
3. save page
4. inspect page and you'll see the flag
