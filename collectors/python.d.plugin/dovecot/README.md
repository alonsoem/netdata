# dovecot

This module provides statistics information from Dovecot server.
Statistics are taken from dovecot socket by executing `EXPORT global` command.
More information about dovecot stats can be found on [project wiki page.](http://wiki2.dovecot.org/Statistics)

**Requirement:**
Dovecot UNIX socket with R/W permissions for user netdata or Dovecot with configured TCP/IP socket.

Module gives information with following charts:

1. **sessions**
 * active sessions

2. **logins**
 * logins

3. **commands** - number of IMAP commands
 * commands

4. **Faults**
 * minor
 * major

5. **Context Switches**
 * volountary
 * involountary

6. **disk** in bytes/s
 * read
 * write

7. **bytes** in bytes/s
 * read
 * write

8. **number of syscalls** in syscalls/s
 * read
 * write

9. **lookups** - number of lookups per second
 * path
 * attr

10. **hits** - number of cache hits
 * hits

11. **attempts** - authorization attempts
 * success
 * failure

12. **cache** - cached authorization hits
 * hit
 * miss

### configuration

Sample:

```yaml
localtcpip:
  name     : 'local'
  host     : '127.0.0.1'
  port     : 24242

localsocket:
  name     : 'local'
  socket   : '/var/run/dovecot/stats'
```

If no configuration is given, module will attempt to connect to dovecot using unix socket localized in `/var/run/dovecot/stats`

---
