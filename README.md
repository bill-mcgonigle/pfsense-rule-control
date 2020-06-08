# pfsense-rule-control
A command-line tool that enables/disables pfSense rules.

## Introduction
This script serves to automate enabling and disabling of pfSense rules, from another host.

## Requirements
### Script Host
It requires the pip3 pfsense-fauxapi python module and a version of python3.  This has been tested on Debian 10 and the upstream version ran on python3 on HomeBrew on MacOS X.  It is expected to run wherever python3 runs.  Adjust the shebang to suit.

Adjust the variables to specify your hostname and credentials and your preferred rule prefix.  Add a unique name with the rule prefix to every rule you want to control with this script.

### pfSense Firewall
Requires:
- pfSense 2.3 or greater.
- FauxAPI (https://github.com/ndejong/pfsense_fauxapi)

## Usage
Examples of usage:

`pfsense-firewall-control <list|enable|disable> rule_name`

`list` will tell you which rules are controlable (based on finding the prefix).

`enable` and disable take a rule name, with or with the prefix and enable or disable it.  If the state changes it reloads the firewall.

If you provide too few parameters it will print some usage help (with the current prefix).

## TODO

Error handling!
Config file!