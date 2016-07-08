Synchronization, Archival, Validation, and IP Exchange (Save)
=============================================================

Save is a framework for implementing highly available network-accessible
services.  Save consists of a command-line utility and a small set of
extensions for the existing Mon monitoring utility.  Mon is a flexible
command scheduler that has the ability to take various actions (called
"alerts") depending on the exit conditions of the periodic commands
(called "monitors") it executes.  Save provides a set of monitors and
alerts that execute within the Mon scheduler.  The core monitor of Save
provides heartbeat functionality so that passive servers can detect if
the active server is still available.  The core alert of Save provides
the ability to give and take the service IP address using gratuitous
ARP.

In addition to the Mon extensions, the Save command-line tool has a
number of features.  This tool provides an interface to control IP
failover.  In particular, the administrator can force the active node to
yield the failover IP address, force the backup node to take over the
failover IP address, or label a node as down so that it will not
attempt to take over the failover IP address under any condition.

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

For installation details, see "INSTALL".  For usage details, see
"doc/usage.txt".  For details of Save configuration, see
"doc/saverc.txt".  For details of Save-specific Mon alerts and monitors,
see "doc/alerts.txt" and "doc/monitors.txt", respectively.

Questions, comments, fixes, and/or enhancements welcome.

--Paul Kolano <paul.kolano@nasa.gov>

