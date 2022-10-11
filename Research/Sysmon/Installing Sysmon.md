# Installing Sysmon

Common usage featuring simple command-line options to install and uninstall Sysmon, as well as to check and modify its configuration:

Install: `sysmon64 -i [<configfile>]`

Update configuration: `sysmon64 -c [<configfile>]`

Install event manifest: `sysmon64 -m`

Print schema: `sysmon64 -s`

Uninstall: `sysmon64 -u [force]`

| Parameter | Description
|----------|-
|-i | Install service and driver. Optionally take a configuration file.
|-c	| Update configuration of an installed Sysmon driver or dump the current configuration if no other argument is provided. Optionally takes a configuration file.
|-m	| Install the event manifest (implicitly done on service install as well).
|-s	| Print configuration schema definition.
|-u	| Uninstall service and driver. Using -u force causes uninstall to proceed even when some components are not installed.

The service logs events immediately and the driver installs as a boot-start driver to capture activity from early in the boot that the service will write to the event log when it starts.

On Vista and higher, events are stored in Applications and Services Logs/Microsoft/Windows/Sysmon/Operational. On older systems, events are written to the System event log.

If you need more information on configuration files, use the `-?` config command.

Specify `-accepteula` to automatically accept the EULA on installation, otherwise you will be interactively prompted to accept it.

Neither install nor uninstall requires a reboot.

There is a basic config file ([here](sysmonconfig-export.xml)), it's a good start but needs a lot of customization before a network-wide deployment