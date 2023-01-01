Maildir browser
===============

Small docker-compose file which let you browse your maildir archives. Eg those extracted
from backup. 

How to use it:

Prepare maildir archive:
------------------------

* create directory, let's say `/tmp/maildir-archive`
* create `Maildir` subdirectory there
* put all your maildir files into `/tmp/maildir-archive/Maildir` in such way that files
  free may look like that:

```
  └── Maildir
    ├── .attic
    │   ├── cur
    │   ├── dovecot.index
    │   ├── dovecot.index.cache
    │   ├── dovecot.index.log
    │   ├── dovecot-uidlist
    │   ├── new
    │   └── tmp
    ├── .attic.adas
    │   ├── cur
    │   │   ├── 1356137991.P3919Q16.my.mailhost.com:2,RSa
    │   │   ├── 1356137991.P3919Q17.my.mailhost.com:2,S
    │   │   ├── 1356137991.P3919Q18.my.mailhost.com:2,RSa
    │   │   ├── 1356137991.P3919Q19.my.mailhost.com:2,S
    │   │   ├── 1356137991.P3919Q20.my.mailhost.com:2,RSa
    │   │   ├── 1356137991.P3919Q21.my.mailhost.com:2,S
    [... lot of other files and directories ..]
```


## Run dovecot and roundcube


```
 MAILDIR_BROWSER_DOVECOT_PASSWORD=foobar \
 MAILDIR_ARCHIVE_DIR=/tmp/maildir-to-browse \
    docker-compose up
```

## Open roundcube in browser


* go to http://localhost:9091/
* authenticate u:app p:foobar (or whatever you specify as
  `MAILDIR_BROWSER_DOVECOT_PASSWORD`)
* go to folders settings and subscribe to all possible folders

Happy browsing


