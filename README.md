# Jenkins Killable Shell Plugin

This plugin proposes two configuration way to terminate a shell script and
its subprocess:

Globally, in jenkins configuration through "Signal sent on abort" textbox, user
can choose the signal to send to all processes started by the shell script, but
the configured signal won't be send to subprocess of these first level process.
After the signal is sent, jenkins will check for the process termination for
"Max second to wait after signal is sent" textbox, 30 seconds if nothing is provided.
If the process didn't terminate, jenkins will kill it the usual way.

This configuration applies globally to all jenkins jobs, but this behavior
can be overridden by job, with the same two textbox.
