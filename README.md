# ovirtctl

**Ovirt control script for manage VMs through REST API[http://ovirt.github.io/ovirt-engine-api-model/4.3/].**

Using this script, for example, you can make autostart of Ovirt VMs when OS started. Ovirt 4.3 not supported VMs autostart "out of the box".

Warning! This script compatible with Ovirt 4.3 and was not test on other versions.

```
Usage:
	vm-list
	vm-start|vm-stop|vm-shutdown|vm-reboot|vm-suspend|vm-get <vmName>
	vm-start-all|vm-stop-all|vm-shutdown-all
```

Before using the script(except vm-list):
1) Set variables in /bin/ovirtctl: **host**, **user**, **password** which using for login to ovirt-engine Web UI.
2) Check path of **cacert variable**. If correct, so no need touch.
3) Change value of **vms_queue_start_timeout** variable if need. Script waiting(in seconds) before start next VM from queue.
4) Registry to **vm_map** variable the VMs which will be managed by the script.
	For example: *vm_map["bar"]="0074d052-283a-44ae-8788-c50e295dde67"*. Where *bar* is VM name and *0074d052-283a-44ae-8788-	c50e295dde67* is VM id.

```
Usage examples:
	PATH=%PATH:/opt/bin/ovirtctl
	ovirtctl vm-start foo
	ovirtctl vm-start bar
	ovirtctl vm-shutdown-all
```
