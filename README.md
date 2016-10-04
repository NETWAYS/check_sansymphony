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

Exclude by regex example:
```
check_sansymphony -H 2001::db8::1 --exclude-target-caption "^replica.*" --exclude-type ^VimVirtual.*

Found 2 monitors, 2 CRITICAL
type               monitorTargetCaption monitorState severity   monitorStateMessage
------------------------------------------------------------------------------------
ScsiPortConnection Server iSCSI Port 2  Attention    [CRITICAL] Not connected
ServeriScsiPort    Server iSCSI Port 2  Critical     [CRITICAL] Not present
```

See `--help` for all arguments.

## External links

* [SANsymphony SNMP support](http://www.datacore.com/SSV-webhelp/SNMP_Support.htm)
