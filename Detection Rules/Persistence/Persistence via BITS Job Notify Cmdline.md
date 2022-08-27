# Persistence via BITS Job Notify Cmdline


>About the Rule:

An adversary can use the Background Intelligent Transfer Service (BITS) SetNotifyCmdLine method to execute a program that runs after a job finishes transferring data or after a job enters a specified state in order to persist on a system.
 

>Conditions:

and:

- event.type == "start"
- process.parent.name : "svchost.exe"
- process.parent.args : "BITS"
 


>Possible False Positives:

- Regular usage by thr operating system


>Exceptions:

- process.executable : "?:\\Windows\\System32\\WerFaultSecure.exe"
- process.executable : "?:\\Windows\\System32\\WerFault.exe"
- process.executable : "?:\\Windows\\System32\\wermgr.exe"
- process.executable : "?:\\WINDOWS\\system32\\directxdatabaseupdater.exe"
