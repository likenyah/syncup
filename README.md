# syncup

## Overview

**syncup** [ **-hv** ] [ **-C** _file_ ] [ **-H** _path_ ] [ **-c** _file_ ]
       _maildir-root_

Use [**mbsync**(1)](https://isync.sourceforge.io/mbsync.html) to synchronise a
local Maildir collection at _maildir-root_ with a remote,
run [**notmuch-new**(1)](https://notmuchmail.org/manpages/notmuch-new-1/) on
the synchronised local store, and run pre– and post-sync hooks as appropriate.

## Dependencies

**syncup** depends mostly on utilities specified by
[POSIX.1-2017](https://pubs.opengroup.org/onlinepubs/9699919799/).

Additionally, we depend on:
* [**date**(1)](https://man.openbsd.org/date.1) implementation that supports
  the `%s` format specifier.
* [**flock**(1)](https://www.man7.org/linux/man-pages/man1/flock.1.html) to
  ensure that only one **syncup** process runs at a time.
* [**mbsync**(1)](https://isync.sourceforge.io/mbsync.html) for the actual
  synchronisation.
* [**notmuch**(1)](https://notmuchmail.org/manpages/notmuch-1/) for indexing
  of the new mail.
