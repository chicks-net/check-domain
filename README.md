# check-domain

[![GPLv2 license](https://img.shields.io/badge/License-GPLv2-blue.svg)](https://github.com/chicks-net/check-domain/blob/master/LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/chicks-net/check-domain/graphs/commit-activity)

Check a domain for registration and DNS issues

## Usage

	./check_domain <domain>

## "Good" Example

	$ ./check_domain fini.net
	getting root servers...
	checking fini.net in 13 root servers
	getting TLD servers...
	$VAR1 = {
		  'j.gtld-servers.net' => '192.48.79.30',
		  'c.gtld-servers.net' => '192.26.92.30',
		  'a.gtld-servers.net' => '192.5.6.30',
		  'k.gtld-servers.net' => '192.52.178.30',
		  'g.gtld-servers.net' => '192.42.93.30',
		  'e.gtld-servers.net' => '192.12.94.30',
		  'b.gtld-servers.net' => '192.33.14.30',
		  'i.gtld-servers.net' => '192.43.172.30',
		  'm.gtld-servers.net' => '192.55.83.30',
		  'd.gtld-servers.net' => '192.31.80.30',
		  'h.gtld-servers.net' => '192.54.112.30',
		  'f.gtld-servers.net' => '192.35.51.30',
		  'l.gtld-servers.net' => '192.41.162.30'
		};
	getting authoritative servers...
	$VAR1 = {
		  'va1.fini.net' => '198.57.198.36',
		  'va0.fini.net' => '188.166.50.229',
		  'va2.fini.net' => '209.97.161.217',
		  'ca0.fini.net' => '198.57.196.96',
		  'va3.fini.net' => '198.57.196.94',
		  'ca1.fini.net' => '216.120.236.232'
		};
	checking fini.net on ca0.fini.net/198.57.196.96
	checking fini.net on ca1.fini.net/216.120.236.232
	checking fini.net on va0.fini.net/188.166.50.229
	checking fini.net on va1.fini.net/198.57.198.36
	checking fini.net on va2.fini.net/209.97.161.217
	checking fini.net on va3.fini.net/198.57.196.94
	checking www.fini.net on ca0.fini.net/198.57.196.96
	checking www.fini.net on ca1.fini.net/216.120.236.232
	checking www.fini.net on va0.fini.net/188.166.50.229
	checking www.fini.net on va1.fini.net/198.57.198.36
	checking www.fini.net on va2.fini.net/209.97.161.217
	checking www.fini.net on va3.fini.net/198.57.196.94

	No problems found for fini.net



## "Bad" Example

	$ ./check_domain fini.fun
	getting root servers...
	checking fini.fun in 13 root servers
	getting TLD servers...
	$VAR1 = {
		  'a.nic.fun' => '194.169.218.72',
		  'b.nic.fun' => '185.24.64.72',
		  'd.nic.fun' => '108.59.161.12',
		  'c.nic.fun' => '185.38.99.12'
		};
	getting authoritative servers...
	$VAR1 = {
		  'va3.fini.net' => '198.57.196.94',
		  'va1.fini.net' => '198.57.198.36',
		  'ca1.fini.net' => '216.120.236.232',
		  'va2.fini.net' => '209.97.161.217',
		  'ca0.fini.net' => '198.57.196.96',
		  'va0.fini.net' => '188.166.50.229'
		};
	checking fini.fun on ca0.fini.net/198.57.196.96
	checking fini.fun on ca1.fini.net/216.120.236.232
	checking fini.fun on va0.fini.net/188.166.50.229
	checking fini.fun on va1.fini.net/198.57.198.36
	checking fini.fun on va2.fini.net/209.97.161.217
	checking fini.fun on va3.fini.net/198.57.196.94

	Issues:
	- no adddress from ca0.fini.net/198.57.196.96
	- no adddress from ca1.fini.net/216.120.236.232
	- no adddress from va0.fini.net/188.166.50.229
	- no adddress from va1.fini.net/198.57.198.36
	- no adddress from va2.fini.net/209.97.161.217
	- no adddress from va3.fini.net/198.57.196.94
	fix above issues before more checks are attempted at ./check_domain line 95.


## Support

Github issues.
