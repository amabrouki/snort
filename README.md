# Docker container: Snort in Ubuntu 16.04 with Barnyard2, PulledPork and Snorby
Snort in a Docker Container
(Inspired from this tutorial :
http://www.ubuntu-howtodoit.com/?p=138)

<h2>Building the Snort Docker Image</h2>

Clone the git repo and cd into the "root" directory.

<pre>
  <code>$ git clone https://github.com/amabrouki/snort.git
  $ cd snort</code>
</pre>

Build the container

<pre>
  <code>$ docker build -t snort .</code>
</pre>

<h2>Running the Snort Docker Image</h2>
 To start Snort and set up port forwarding:
<pre>
  <code>$ docker run  --privileged -it -p 3000:3000 -d snort</code>
  Or
  <code> docker run  --privileged -it --net=host -d snort</code>
</pre>

<h2>Passwords</h2>
<div>"Pilote2016" is the password for MYSQL root, snort and snorby. </div>
<div>  user : snorby@example.com  password :snorby    for snorby GUI </div>

<br>

<h4>NB:</h4>
 <div> - You should always verify that Snort, barnyard and Snorby is running, with this command "ps -a" </div>
 <div> - You should run the "Snorby Worker" from the GUI (Administaration --> Worker & Job Queue) </div>
 <div> - You sould modify : </div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; the network addresses you are protecting #ipvar HOME_NET any </div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Put your own Oinkcode in the pulledpork.conf </div>
        <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The passwords of all components </div>
