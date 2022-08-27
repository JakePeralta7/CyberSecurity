# Execution of COM object via Xwizard


>About the Rule:

Windows Component Object Model (COM) is an inter-process communication (IPC) component of the native Windows application programming interface (API) that enables interaction between software objects or executable code. Xwizard can be used to run a COM object created in registry to evade defensive counter measures.
 

>Conditions:

and:

- event.type in ("start", "process_started")
- process.pe.original_file_name : "xwizard.exe"
- process.args : "RunWizard"
- process.args : "{*}"
 


>Possible False Positives:

None for now


>Exceptions:

- process.executable != null
