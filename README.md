# check_snmp_apc_ups.pl - Nagios plugin to test APC UPS's.

## History

I could not find the original owner of this script, so I forked a copy
and made my own modifications here.

Original coder: Unknown (Altinity Limited)
Modified by: Roderick Derks <roderick@r71.nl>
Modified by: Jason E. Murray <jemurray@zweck.net>


## Overview

Nagios plugin to monitor/report on APC UPS's for:
* Device type
* Battery capacity
* Temperature
* Runtime
* Input/Output voltage
* Frequency
* Self test status
* Last Event


## Usage

/usr/lib/nagios/plugins/check_snmp_apc_ups.pl version [unknown] calling Getopt::Std::getopts (version 1.07 [paranoid]),
running under Perl version 5.18.2.

Usage: check_snmp_apc_ups.pl [-OPTIONS [-MORE_OPTIONS]] [--] [PROGRAM_ARG1 ...]

The following single-character options are accepted:
    With arguments: -h -H -C -w -c -L -T

Options may be merged together.  -- stops processing of options.
Space is not required between options and their arguments.
  [Now continuing due to backward compatibility and excessive paranoia.
   See 'perldoc Getopt::Std' about $Getopt::Std::STANDARD_HELP_VERSION.]
No hostname specified
-----------------------------------------------------------------
check_snmp_apcups v2.1.0

Monitors APC SmartUPS via AP9617 SNMP management card.

Usage: check_snmp_apcups -H <hostname> -c <community> [...]

Options: -H     Hostname or IP address
         -C     Community (default is public)

-----------------------------------------------------------------
Copyright 2004 Altinity Limited

This program is free software; you can redistribute it or modify
it under the terms of the GNU General Public License
-----------------------------------------------------------------



## Examples

jemurray@nagios:~$ /usr/lib/nagios/plugins/check_snmp_apc_ups.pl -H 192.168.6.34 -C public
Status is OK - Smart-UPS RT 6000 XL - BATTERY:(capacity 100%, temperature 28 C, runtime 19 minutes, 00.00) INPUT:(voltage 213 V, frequency 60 Hz) OUTPUT:(voltage 208 V, frequency 60 Hz, load 46%) SELF TEST:(Passed on 10/31/2014) LAST EVENT:(UPS self test)|capacity=100%;50;25;0;100 load=46%;80;90;0;100 temp=28 runtime=19  iv=213 ov=208


