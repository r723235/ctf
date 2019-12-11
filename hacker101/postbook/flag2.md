### hints
* You should definitely use "Inspect Element" on the form when creating a new post


### solution

1. select *Write a new post* in the top menu
2. inspect this page
3. note that there is a hidden `<input>` tag
   * `<input type="hidden" name="user_id" value="2">`
4. change the value to any other integer
5. after selecting **post**, the resulting page will display the flag
