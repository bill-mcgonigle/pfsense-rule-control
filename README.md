# pfsense-rule-control
A command-line tool that enables/disables pfSense rules.

## Introduction
This script serves to automate enabling and disabling of pfSense rules, from another host.

## Requirements
### Script Host
It requires the pip3 pfsense-fauxapi python module and a version of python3.  This has been tested on Debian 10 and the upstream version ran on python3 on HomeBrew on MacOS X.  It is expected to run wherever python3 runs.  Adjust the shebang to suit.

Adjust the variables to specify your hostname and credentials and your preferred rule prefix.  Add a unique name with the rule prefix to the description of every rule you want to control with this script.

For example if you have a rule that has a description "Block Bob's PC", edit the rule and set the description to "Block Bob's PC - auto_block_bob".

### pfSense Firewall
Requires:
- pfSense 2.3 or greater (tested in 2020 on 2.4.5)
- FauxAPI pfSense package (https://github.com/ndejong/pfsense_fauxapi)

## Usage
Examples of usage:

`pfsense-rule-control <list|enable|disable> rule_name`

`list` will tell you which rules are controlable (based on finding the prefix).

`enable` and `disable` take a rule name, with or without the prefix and enable or disable it.  If the state changes it reloads the firewall (that is if you enable an enabled rule, or disable a disabled rule it will just do nothing.

For example:

`pfsense-rule-control enable block_bob`

If you provide too few parameters it will print some usage help (with the current prefix).

## TODO

Error handling!

Config file!