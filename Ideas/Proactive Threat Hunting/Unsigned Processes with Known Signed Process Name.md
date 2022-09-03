# Unsigned Processes with Known Signed Process Name

An adversary would like to masquerade itself as a known process in order to evade detection / impersonate to get the user to execute his payload.

Suggestions:
- Export a list of all the unsigned processes
- Look for a known process (cmd.exe, explorer.exe, etc.)
- Check his hash in virustotal