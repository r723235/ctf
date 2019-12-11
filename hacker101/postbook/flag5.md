### hints
* The cookie allows you to stay signed in. Can you figure out how they work so you can sign in to user with ID 1?


### solution

1. investigate the session cookie
2. note that the `id` value is `c81e728d9d4c2f636f067f89cc14862c`. the md5 hash for the value `2`
3. update this to `c4ca4238a0b923820dcc509a6f75849b` which is the md5 hash for `1`
4. you should now be logged in as **admin**
