### hints
* Deleting a post seems to take an ID that is not a number. Can you figure out what it is?


### solution

1. in burp suite, make sure that intercept is set to **on**
2. on the browser, delete any post
3. note that the delete request in burp suite is a GET request with two params: `page` and `id`
4. the `id` is another md5 of the page id
5. change this to `c4ca4238a0b923820dcc509a6f75849b` since we know it's the md5 hash for `1`
6. forward through the send and receive requests
7. voila!
