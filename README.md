# smbrelayz.py
just some dev to work out a few enhancements and possibly get core to pull them in...

Mainly the changes here are small...just wanted to make this listen for connections on 80, 443, 139, and 445 by default instead of just 80 and 445.

Why?

I've run into consective environments where I've had Responder making responses and catching inbound 139 connections...which is a cool NTLMV2 Challenge Response Hash, but not useful when the passwords are strong.

What I really wanted was to relay that connection to the one or two hosts (people are catching on) that don't have smb signing enabled.

Also, I get other random connections that I'd like to try to relay.

So, all I did was setup additional listeners on the HTTPServer and SMBServer listeners.

Also looking to setup some other payloads beyond and executable, command, or secretsdump.py.  It seems that non-admin accounts could be useful for enumeration by accessing shares, or maybe executing a wmiexec or smbexec if psexec not really working.
