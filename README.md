Synchronization, Archival, Validation, and IP Exchange (Save)
=============================================================

Save is a framework for implementing highly available network-accessible
services.  Save sends and monitors SSH-based heartbeats so that passive
servers can detect if the active server is still available.  A common
sevice IPv4 and/or IPv6 address can be given and taken using gratuitous
ARP (IPv4) and/or unsolicited neighbor advertisement (IPv6).

In addition to heartbeat/failover functionality, the Save command-line
tool has a number of features.  This tool provides an interface to
control IP failover.  In particular, the administrator can force the
active node to yield the failover IP address, force the backup node to
take over the failover IP address, or label a node as down so that it
will not attempt to take over the failover IP address under any
condition.

The command-line tool also controls the validation, archival, and
synchronization features of Save.  Validation is used to make sure that
a configuration file conforms to some specified characteristics such as
format before it is installed on other nodes.  Archival is used to save
a copy of the previous configuration if, for some reason, the new
configuration results in errant behavior.  Finally, synchronization
features can be used to keep files consistent between the active and
passive node(s) and/or to execute the same command across all nodes at
once.

The configuration of the Save command-line tool determines what actions
will be taken at which times.  The administrator need only prepend the
"save" command (i.e. the name of the tool) to any command and the
appropriate actions will be taken if they are applicable.  In this
way, administrators can simply perform their normal tasks, such as
editing files (e.g. "save vi /etc/config/ file"), and Save will take
care of checking validity, backing up old versions, and synchronizing
files across systems if required.  For files for which there are no
specific actions defined within the Save configuration, the "save"
command has no effect, which allows the administrator to safely prepend
this to any command.

For installation details, see "INSTALL".  For details of usage and
configuration, see "doc/save.1" and "doc/saverc.5" (via man once
installed or via "nroff -man"), respectively.

Questions, comments, fixes, and/or enhancements welcome.

--Paul Kolano <paul.kolano@nasa.gov>

