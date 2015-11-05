# Version: 0.2.0 - Date: 2007-09-17 #

## Major enhancements ##

  * [Issue 5](https://code.google.com/p/pyftpdlib/issues/detail?id=5): provided a way to configure / limit the number of maximum acceptable connections.
  * [Issue 5](https://code.google.com/p/pyftpdlib/issues/detail?id=5): provided a way to configure / limit the maximum number of clients which may be connected from the same IP address.
  * [Issue 36](https://code.google.com/p/pyftpdlib/issues/detail?id=36): added support for [FXP](http://www.proftpd.org/docs/howto/FXP.html) site-to-site transfer to allow transfers between FTP servers.
  * [Issue 39](https://code.google.com/p/pyftpdlib/issues/detail?id=39): added NAT/Firewall support with PASV (passive) mode connections for FTP servers behind NAT.
  * [Issue 40](https://code.google.com/p/pyftpdlib/issues/detail?id=40): provided new FTPHandler.passive\_ports attribute to control what ports to use for passive data-transfers.

## RFC-related enhancements ##

  * [Issue 6](https://code.google.com/p/pyftpdlib/issues/detail?id=6): accept and process TYPE AN and TYPE L8 commands.
  * [Issue 7](https://code.google.com/p/pyftpdlib/issues/detail?id=7): a new USER command can now be entered at any point to begin the login sequence again.
  * [Issue 8](https://code.google.com/p/pyftpdlib/issues/detail?id=8): be compliant with STOU output format defined in RFC 1123.
  * [Issue 10](https://code.google.com/p/pyftpdlib/issues/detail?id=10): HELP command arguments are now accepted.
  * [Issue 12](https://code.google.com/p/pyftpdlib/issues/detail?id=12): 554 error response is now returned on RETR/STOR if REST fails.
  * [Issue 15](https://code.google.com/p/pyftpdlib/issues/detail?id=15): STAT used with an argument return directory LISTing over the command channel.

## Security enhancements ##

  * [Issue 3](https://code.google.com/p/pyftpdlib/issues/detail?id=3): stop buffering when extremely long lines are received.
  * [Issue 11](https://code.google.com/p/pyftpdlib/issues/detail?id=11): reject data connection when a privileged port is specified on PORT command.
  * [Issue 25](https://code.google.com/p/pyftpdlib/issues/detail?id=25): limit the number of attempts to find a unique filename for STOU command.

## Usability enhancements ##

  * Provided an overridable attribute to easily set number of maximum login attempts before disconnecting.
  * Docstrings are now provided for almost every method and function.
  * [Issue 30](https://code.google.com/p/pyftpdlib/issues/detail?id=30): command help strings quality improved by adding command syntaxes.
  * [Issue 31](https://code.google.com/p/pyftpdlib/issues/detail?id=31): a compact list of recognized commands is now provided on HELP.
  * [Issue 32](https://code.google.com/p/pyftpdlib/issues/detail?id=32): we now provide a detailed error message on connection and file system errors.
  * [Issue 38](https://code.google.com/p/pyftpdlib/issues/detail?id=38): anonymous user write access can now be optionally granted.

## Test suite enhancements ##

  * File creation/removal moved into setUp and tearDown methods to avoid leaving behind orphaned temporary files in the event of a test suite failure.
  * [Issue 7](https://code.google.com/p/pyftpdlib/issues/detail?id=7): added tests for a new USER provided while already authenticated.
  * [Issue 7](https://code.google.com/p/pyftpdlib/issues/detail?id=7): added tests for REIN while a transfer is in progress.
  * [Issue 28](https://code.google.com/p/pyftpdlib/issues/detail?id=28): added tests for ABOR command.

## Bugfixes ##

  * [Issue 4](https://code.google.com/p/pyftpdlib/issues/detail?id=4): socket's "reuse\_address" feature was used after the socket's binding.
  * [Issue 9](https://code.google.com/p/pyftpdlib/issues/detail?id=9): corrected path traversal vulnerability affecting file-system path translations.
  * [Issue 14](https://code.google.com/p/pyftpdlib/issues/detail?id=14): a wrong response code was returned on CDUP.
  * [Issue 17](https://code.google.com/p/pyftpdlib/issues/detail?id=17): reject SIZE if pathname is a directory.
  * [Issue 18](https://code.google.com/p/pyftpdlib/issues/detail?id=18): a wrong ABOR response code type was returned.
  * [Issue 19](https://code.google.com/p/pyftpdlib/issues/detail?id=19): watch for STOU preceded by REST which makes no sense.
  * [Issue 20](https://code.google.com/p/pyftpdlib/issues/detail?id=20): "attempted login" counter wasn't incremented on wrong username.
  * [Issue 21](https://code.google.com/p/pyftpdlib/issues/detail?id=21): STAT wasn't permitted if user wasn't authenticated yet.
  * [Issue 22](https://code.google.com/p/pyftpdlib/issues/detail?id=22): corrected memory leaks occurring on KeyboardInterrupt/SIGTERM.
  * [Issue 23](https://code.google.com/p/pyftpdlib/issues/detail?id=23): PASS wasn't rejected when user was already authenticated.
  * [Issue 24](https://code.google.com/p/pyftpdlib/issues/detail?id=24): can't use os.strerror() on pythonCE.
  * [Issue 24](https://code.google.com/p/pyftpdlib/issues/detail?id=24): problem occurred on Windows when using '\\' as user's home directory.
  * [Issue 26](https://code.google.com/p/pyftpdlib/issues/detail?id=26): used select() by default instead of poll() because of an asyncore module's defect.
  * [Issue 33](https://code.google.com/p/pyftpdlib/issues/detail?id=33): some FTPHandler class attributes wasn't resetted on REIN.
  * [Issue 35](https://code.google.com/p/pyftpdlib/issues/detail?id=35): watch for APPE preceded by REST which makes no sense.






