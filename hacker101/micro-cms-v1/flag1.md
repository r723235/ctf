### hints
* Make sure you tamper with every input
* Have you tested for the usual culprits? XSS, SQL injection, path injection
* Bugs often occur when an input should always be one type and turns out to be another
* Remember, form submissions aren't the only inputs that come from browsers

### solution

this is a sql injection flag. on any edit page, simply add a single quote to the end of the url.

.../page/edit/1'
