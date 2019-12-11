### hints
* Sometimes a given input will affect more than one page
* The bug you are looking for doesn't exist in the most obvious place this input is shown

### solution

1. edit or create a page
2. in the title, inject xss script
   * ```<script>alert`xss`</script>```
3. navigate back home
4. the flag will pop up
