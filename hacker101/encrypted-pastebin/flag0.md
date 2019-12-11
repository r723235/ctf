### hints
* What are these encrypted links?
* Encodings like base64 often need to be modified for URLs. Thanks, HTTP
* What is stopping you from modifying the data? Not having the key is no excuse


### solution

1. create new post. values for title and body are irrelevant
2. the resulting page has a base64 encoded param, `?post=`
3. modify the value in any way
   * add characters
   * remove characters
   * even remove the entire value if you want
4. you should see **^FLAG^...$FLAG$** in the body of the error page
