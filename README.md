check_sansymphony
=================

A Nagios/Icinga plugin to check the DataCore SANsymphonyV cluster for alerts in
its monitoring.

## Requirements

You will need to enable both the SNMP agent of SANsymphony, as well as the Windows SNMP service.

Also make sure to setup a proper community and ACL in the SNMP service.

## Usage

The plugin can try to access monitoring data via multiple addresses, and will use the first reachable result.

```
check_sansymphony -H 2001::db8::1,2001::db8::2 --community secure --domain udp6 --include disk,pool
```

See `--help` for all arguments.

## External links

* [SANsymphony SNMP support](http://www.datacore.com/SSV-webhelp/SNMP_Support.htm)
