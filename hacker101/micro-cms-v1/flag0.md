### hints
* Try creating a new page
* How are pages indexed?
* Look at the sequence of IDs
* If the front door doesn't open, try the window
* In what ways can you retrieve page contents?

### solution

1. create new page. for example, **foo**
2. note the page id. in my case, it's *page 7*
   * .../page/7
3. go back home and inspect page
4. 🤔 note the index of page ids. there are some that are skipped
   * ..."page/1"
   * ..."page/2"
   * ..."page/7" <- newly created page
5. visit other pages not listed until you see the **Forbidden** error
6. finally, change the url directly in order to edit the page
   * .../page/edit/5
7. you should see **^FLAG^...$FLAG$** in the body of the page
