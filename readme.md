# The Sigma Environment

This document seeks to provide a basis for performing a variety of tasks regarding the Sigma environment:

* Introduction to the system
* Practical administration tasks
* Environment design (the "world")
* Extensions to the core engine

## About Sigma

Sigma is an open-ended environmental framework for social and competitive interaction. Utilizing the traditional basis for the MU* family of text-based gaming frameworks, Sigma provides, or aims to provide, a combat system, items, commerce, system-controlled "denizens," and a communication system.

### Design Goals

While some MU* engines have sought to empower the developer or the end-user of the environmental system, Sigma's goal is focused on empowering the game designer, who may or may not be an accomplished programmer, to create a unique atmospheric experience without requiring modifications to the core engine or an involved understanding of its inner workings.

### Licensure

The source code of Sigma is released under the GNU General Public License, Version 2.0. For more information, please consult http://creativecommons.org/licenses/GPL/2.0/. Contributed modules and XML source files may be assumed also under the provisions of GPL 2.0 unless otherwise noted within the relevant files.

## Administration

Sigma is started by executing the sigma.py source file. The code in this file initializes the server and, assuming no errors occurred during startup, enters into the main control loop that handles the processing of socket interactions and game events.

### Connecting and Logging In

By default, Sigma listens on TCP port 4000. If this option has been modified, or specified explicitly in the server configuration, a message similar to the following line will appear in the startup messages:

    CONFIG     | Option [bind_port] set to '4000'

The most straightforward way to connect to Sigma is to use the telnet program. This shell command will establish communication with the server running on the standard port:

    telnet localhost 4000

The standard distribution of Sigma contains a default user account, under the name Alpha, with the password default. This player account will allow you to access the default Sigma installation and inspect its operations.

For obvious security reasons, you should create a new user account for yourself, and you should delete the Alpha account before proceeding. You may do so by using the following command from the base Sigma directory:

    python sigma.py players

The distributed config/players.db file can also simply be deleted, as it will be regenerated upon server startup.

### Shutting Down the Server

Press Ctrl-C from the shell executing sigma.py to perform shutdown tasks and halt the server.