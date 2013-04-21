<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html>

<head>
<title>The Sigma Environment</title>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1" />

<style type="text/css">
body {
  font-family: sans-serif;
}

pre {
  border-left: 2px solid #88d;
  margin-left: 10px;
  padding-left: 10px;
}

strong.important {
  color: #800;
}
</style>

</head>

<body>

<h1>The Sigma Environment</h1>

<p>This document seeks to provide a basis for performing a variety of tasks regarding the Sigma environment:</p>

<ul>
   <li>Introduction to the system</li>
   <li>Practical administration tasks</li>
   <li>Environment design (the "world")</li>
   <li>Extensions to the core engine</li>
</ul>

<h2>About Sigma</h2>

<p>Sigma is an open-ended environmental framework for social and competitive interaction.  Utilizing the traditional basis for the MU* family of text-based gaming frameworks, Sigma provides, or aims to provide, a combat system, items, commerce, system-controlled "denizens," and a communication system.</p>

<h3>Design Goals</h3>

<p>While some MU* engines have sought to empower the developer or the end-user of the environmental system, Sigma's goal is focused on empowering the <em>game designer</em>, who may or may not be an accomplished programmer, to create a unique atmospheric experience without requiring modifications to the core engine or an involved understanding of its inner workings.</p>

<h3>Licensure</h3>

<p>The source code of Sigma is released under the GNU General Public License, Version 2.0.  For more information, please consult <a href="http://creativecommons.org/licenses/GPL/2.0/">http://creativecommons.org/licenses/GPL/2.0/</a>.  Contributed modules and XML source files may be assumed also under the provisions of GPL 2.0 unless otherwise noted within the relevant files.</p>

<h2>Administration</h2>

<p>Sigma is started by executing the <code>sigma.py</code> source file.  The code in this file initializes the server and, assuming no errors occurred during startup, enters into the main control loop that handles the processing of socket interactions and game events.</p>

<h3>Connecting and Logging In</h3>

<p>By default, Sigma listens on TCP port 4000.  If this option has been modified, or specified explicitly in the server configuration, a message similar to the following line will appear in the startup messages:</p>

<pre>
CONFIG     | Option [bind_port] set to '4000'
</pre>

<p>The most straightforward way to connect to Sigma is to use the telnet program.  This shell command will establish communication with the server running on the standard port:</p>

<pre>
telnet localhost 4000
</pre>

<p>The standard distribution of Sigma contains a default user account, under the name <strong>Alpha</strong>, with the password <strong>default</strong>.  This player account will allow you to access the default Sigma installation and inspect its operations.</p>

<p><strong class="important">For obvious security reasons, you should create a new user account for yourself, and you should delete the Alpha account before proceeding.</strong>  You may do so by using the following command from the base Sigma directory:</p>

<pre>
python sigma.py players
</pre>

<p>The distributed <strong>config/players.db</strong> file can also simply be deleted, as it will be regenerated upon server startup.</p>

<h3>Shutting Down the Server</h3>

<p>Press <code>Ctrl-C</code> from the shell executing <code>sigma.py</code> to perform shutdown tasks and halt the server.</p>

</body>

</html>
