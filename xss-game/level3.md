# Level 3: That sinking feeling...

### hints
* To locate the cause of the bug, review the JavaScript to see where it handles user-supplied input.
* Data in the **window.location** object can be influenced by an attacker.
* When you've identified the injection point, think about what you need to do to sneak in a new HTML element.
* As before, using `<script> ..`. as a payload won't work because the browser won't execute scripts added after the page has loaded.

### solution

* update url to something like:
   * `#1.jpg'/><script>alert(123)</script><--`
