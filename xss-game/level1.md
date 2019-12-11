# Level 1: Hello, world of XSS

### hints
* To see the source of the application you can right-click on the frame and choose *View Frame Source* from the context menu or use your browser's developer tools to inspect network traffic.
* What happens when you enter a presentational tag such as `<h1>`?
* Alright, one last hint: `<script> ... alert ...`

### solution

* enter the following query string
   * `<script>alert(123)</script>`
