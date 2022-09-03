# Hosts File Modified


>About the Rule:

The hosts file on endpoints is used to control manual IP address to hostname resolutions. The hosts file is the first point of lookup for DNS hostname resolution so if adversaries can modify the endpoint hosts file, they can route traffic to malicious infrastructure. This rule detects modifications to the hosts file on Microsoft Windows, Linux (Ubuntu or RHEL) and macOS systems.
 

>Conditions:

or:

- (event.category == "file" and 
  event.type in ("change", "creation") and
  file.path: ("/private/etc/hosts", "/etc/hosts", "?:\\Windows\\System32\\drivers\\etc\\hosts"))
- (event.category == "process" and event.type in ("start") and
  process.name in ("nano", "vim", "vi", "emacs", "echo", "sed") and
  process.args: ("/etc/hosts"))
 


>Possible False Positives:

None for Now


>Exceptions:

None for now
