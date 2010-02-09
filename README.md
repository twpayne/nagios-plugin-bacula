check_bacula_client
===================

`check_bacula_client` is a [Nagios](http://www.nagios.org) plugin to check [Bacula](http://www.bacula.org/) client backups.  It will warn or indicate a critical state if the last successful backup for a client is older than a psecified period.  It uses the `bconsole` program to interact with the Bacula Director and therefore is independent of the client and the database used by the Bacula Director.


Dependencies
------------

* [Python](http://www.python.org) version 2.4
* [pexpect](http://pexpect.sourceforge.net/)


Installation
------------

`check_bacula_client` assumes that the `bconsole` program can connect automatically without requiring a username or password.  You may need to edit `bconsole.conf` to acheive this.


Usage
-----

### Example ###

	$ ./check_bacula_client -H isdc1101.isdc.unige.ch -w 12h -c 1d
	WARNING: Incr, 1493 files, 42.20MB, 2010-02-08 23:01:00 (14.4 hours ago)

### Options ###

* `-H CLIENT` client name
* `-w PERIOD` generate warning if last successful backup older than `PERIOD`
* `-c PERIOD` generate critical if last successful backup older than PERIOD
* `-b PATH` path to `bconsole`

`PERIOD` is an floating point number followed by `m` for minutes, `h` for hours, `d` for days, or `w` for weeks.
