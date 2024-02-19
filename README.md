# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```

chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```



cat < file2
## OUTPUT
...

anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
...

# Comparing Files
cmp file1 file2
## OUTPUT
...

 file1 file2 differ: byte 1, line 1
comm file1 file2
...
 ## OUTPUT
 ...
 
	anil aggarwal
	barun sengupta
chanchal singhvi
		c.k. shukla
	lalit chowdury
		s.n. dasgupta
sumit chakrobarty
...
 
diff file1 file2
## OUTPUT
...

1c1,2
< chanchal singhvi
---
> anil aggarwal
> barun sengupta
2a4
> lalit chowdury
4d5
< sumit chakrobarty
...

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
...

Hel
Thi
...



cut -d "|" -f 1 file22
## OUTPUT
...

1001 
1002 
1003 
...


cut -d "|" -f 2 file22
## OUTPUT
...

 Ram 
 tom 
 Joe 
...

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Hello</b></font> world
</pre>


grep hello newfile 
## OUTPUT
<pre><font color="#C01C28"><b>hello</b></font> world
</pre>



grep -v hello newfile 
## OUTPUT
Hello world



cat newfile | grep -i "hello"
## OUTPUT

<pre>Hello world
<font color="#C01C28"><b>hello</b></font> world
</pre>


cat newfile | grep -i -c "hello"
## OUTPUT
1




grep -R ubuntu /etc
## OUTPUT
<pre><font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-email</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-email</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-email</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-feed-readers</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-feed-readers</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-feed-readers</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-feed-readers.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-bittorrent-clients.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-xterm</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-xterm.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gvfs-open</font><font color="#2AA1B3">:</font>#   # needed for <font color="#C01C28"><b>ubuntu</b></font>-* abstractions
<font color="#A347BA">/etc/apparmor.d/abstractions/gvfs-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gvfs-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gvfs-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/productivity</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/productivity</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-media-players&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-bittorrent-clients&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-feed-readers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/plugins-common</font><font color="#2AA1B3">:</font>  # Since all the <font color="#C01C28"><b>ubuntu</b></font>-browsers.d abstractions need this, just include it
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/plugins-common</font><font color="#2AA1B3">:</font>  include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/plugins-common&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/mailto&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/multimedia&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/productivity&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/java&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/kde&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/text-editors&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/<font color="#C01C28"><b>ubuntu</b></font>-integration&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser</font><font color="#2AA1B3">:</font>include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers.d/user-files&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/text-editors</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/text-editors</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration</font><font color="#2AA1B3">:</font>  # K<font color="#C01C28"><b>ubuntu</b></font>
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/kde</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-browsers.d/kde</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-konsole</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-konsole.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-unity7-base</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-unity7-base.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gio-open</font><font color="#2AA1B3">:</font>#   # needed for <font color="#C01C28"><b>ubuntu</b></font>-* abstractions
<font color="#A347BA">/etc/apparmor.d/abstractions/gio-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gio-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/gio-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-unity7-launcher</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-unity7-launcher.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-unity7-messaging</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-unity7-messaging.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-browsers</font><font color="#2AA1B3">:</font># include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-browsers</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-browsers</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-browsers</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-browsers.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-media-players</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-media-players</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-media-players</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-media-players.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-gnome-terminal</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/evince</font><font color="#2AA1B3">:</font>  # L<font color="#C01C28"><b>ubuntu</b></font>
<font color="#A347BA">/etc/apparmor.d/abstractions/evince</font><font color="#2AA1B3">:</font>  /etc/xdg/l<font color="#C01C28"><b>ubuntu</b></font>/applications/defaults.list r,
<font color="#A347BA">/etc/apparmor.d/abstractions/exo-open</font><font color="#2AA1B3">:</font>#   # needed for <font color="#C01C28"><b>ubuntu</b></font>-* abstractions
<font color="#A347BA">/etc/apparmor.d/abstractions/exo-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/exo-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/exo-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/exo-open</font><font color="#2AA1B3">:</font>  /usr/share/{xfce{,4},x<font color="#C01C28"><b>ubuntu</b></font>}/applications/{,*.list} r,
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-email</font><font color="#2AA1B3">:</font># include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-email</font><font color="#2AA1B3">:</font># Users of this abstraction need to include the <font color="#C01C28"><b>ubuntu</b></font>-helpers abstraction
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-email</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/ubuntu-console-email</font><font color="#2AA1B3">:</font>  include if exists &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-email.d&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/xdg-open</font><font color="#2AA1B3">:</font>#   # needed for <font color="#C01C28"><b>ubuntu</b></font>-* abstractions
<font color="#A347BA">/etc/apparmor.d/abstractions/xdg-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/xdg-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/xdg-open</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/kde</font><font color="#2AA1B3">:</font>/usr/share/k<font color="#C01C28"><b>ubuntu</b></font>-default-settings/kf5-settings/* r,
<font color="#A347BA">/etc/apparmor.d/abstractions/kde-open5</font><font color="#2AA1B3">:</font>#   # needed for <font color="#C01C28"><b>ubuntu</b></font>-* abstractions
<font color="#A347BA">/etc/apparmor.d/abstractions/kde-open5</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-helpers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/kde-open5</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/kde-open5</font><font color="#2AA1B3">:</font>#   include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/abstractions/kde-open5</font><font color="#2AA1B3">:</font>  # see: https://lists.<font color="#C01C28"><b>ubuntu</b></font>.com/archives/apparmor/2019-January/011925.html
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-email&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-media-players&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  ##include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-xterm&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  ##include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-konsole&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  # For X<font color="#C01C28"><b>ubuntu</b></font> to launch the browser
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-browsers&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-email&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-console-email&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-media-players&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  #include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-gnome-terminal&gt;
<font color="#A347BA">/etc/apparmor.d/usr.bin.evince</font><font color="#2AA1B3">:</font>  ##include &lt;abstractions/<font color="#C01C28"><b>ubuntu</b></font>-xterm&gt;
<font color="#A347BA">/etc/apparmor.d/usr.sbin.cupsd</font><font color="#2AA1B3">:</font># Author: Martin Pitt &lt;martin.pitt@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
grep: /etc/shadow-: Permission denied
<font color="#A347BA">/etc/rc1.d/K01whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
grep: /etc/ppp/chap-secrets: Permission denied
grep: /etc/ppp/pap-secrets: Permission denied
<font color="#A347BA">/etc/speech-dispatcher/speechd.conf</font><font color="#2AA1B3">:</font># Copyright (C) 2014-2016 Luke Yelavich &lt;themuso@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
<font color="#A347BA">/etc/speech-dispatcher/modules/espeak-ng-mbrola-generic.conf</font><font color="#2AA1B3">:</font># Copyright (C) 2014 Luke Yelavich &lt;themuso@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
<font color="#A347BA">/etc/speech-dispatcher/modules/espeak-mbrola-generic.conf</font><font color="#2AA1B3">:</font># Copyright (C) 2014 Luke Yelavich &lt;themuso@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
grep: /etc/ssl/private: Permission denied
<font color="#A347BA">/etc/grub.d/10_linux</font><font color="#2AA1B3">:</font><font color="#C01C28"><b>ubuntu</b></font>_recovery=&quot;1&quot;
<font color="#A347BA">/etc/grub.d/10_linux</font><font color="#2AA1B3">:</font>    Ubuntu|K<font color="#C01C28"><b>ubuntu</b></font>)
<font color="#A347BA">/etc/grub.d/10_linux</font><font color="#2AA1B3">:</font>if [ &quot;$<font color="#C01C28"><b>ubuntu</b></font>_recovery&quot; = 1 ]; then
<font color="#A347BA">/etc/grub.d/10_linux</font><font color="#2AA1B3">:</font>  if ([ &quot;$<font color="#C01C28"><b>ubuntu</b></font>_recovery&quot; = 0 ] || [ x$type != xrecovery ]) &amp;&amp; \
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font><font color="#C01C28"><b>ubuntu</b></font>_recovery=&quot;1&quot;
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>        # on <font color="#C01C28"><b>ubuntu</b></font>, loaded by the shim.
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>    last_booted_kernel=$(zfs get -H com.<font color="#C01C28"><b>ubuntu</b></font>.zsys:last-booted-kernel &quot;${dataset}&quot; | awk -v FS=&apos;\t&apos; &apos;{print $3}&apos;)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>            last_used=$(zfs get -H com.<font color="#C01C28"><b>ubuntu</b></font>.zsys:last-used &quot;${dataset}&quot; | awk &apos;{print $3}&apos;)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>    is_zsys=$(zfs get -H com.<font color="#C01C28"><b>ubuntu</b></font>.zsys:bootfs &quot;${base_dataset}&quot; | awk &apos;{print $3}&apos;)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>    if ([ &quot;${<font color="#C01C28"><b>ubuntu</b></font>_recovery}&quot; = 0 ] || [ &quot;${type}&quot; != &quot;recovery&quot; ]) &amp;&amp; \
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>            Ubuntu|K<font color="#C01C28"><b>ubuntu</b></font>)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>    if [ &quot;${<font color="#C01C28"><b>ubuntu</b></font>_recovery}&quot; = 1 ]; then
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>	# $1: root dataset (eg rpool/ROOT/<font color="#C01C28"><b>ubuntu</b></font>_2zhm07@autozsys_k56fr6)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>	# $3: initrd (eg /BOOT/<font color="#C01C28"><b>ubuntu</b></font>_2zhm07@autozsys_k56fr6/initrd.img-5.4.0-21-generic)
<font color="#A347BA">/etc/grub.d/10_linux_zfs</font><font color="#2AA1B3">:</font>	# $4: kernel (eg /BOOT/<font color="#C01C28"><b>ubuntu</b></font>_2zhm07@autozsys_k56fr6/vmlinuz-5.4.0-21-generic)
<font color="#A347BA">/etc/grub.d/05_debian_theme</font><font color="#2AA1B3">:</font>		Tanglu|Ubuntu|K<font color="#C01C28"><b>ubuntu</b></font>)
<font color="#A347BA">/etc/grub.d/05_debian_theme</font><font color="#2AA1B3">:</font>	Ubuntu|K<font color="#C01C28"><b>ubuntu</b></font>)
grep: /etc/gshadow: Permission denied
<font color="#A347BA">/etc/init.d/whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
<font color="#A347BA">/etc/init.d/apparmor</font><font color="#2AA1B3">:</font>#  Kees Cook &lt;kees@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
<font color="#A347BA">/etc/init.d/acpid</font><font color="#2AA1B3">:</font>        MODULES=&quot;$(sed -rn &apos;s#^(/lib/modules/[^/]+/)?kernel/(drivers|<font color="#C01C28"><b>ubuntu</b></font>)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p&apos; &quot;/lib/modules/$(uname -r)/modules.dep&quot;)&quot;
<font color="#A347BA">/etc/rcS.d/S01apparmor</font><font color="#2AA1B3">:</font>#  Kees Cook &lt;kees@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
<font color="#A347BA">/etc/rc2.d/S01acpid</font><font color="#2AA1B3">:</font>        MODULES=&quot;$(sed -rn &apos;s#^(/lib/modules/[^/]+/)?kernel/(drivers|<font color="#C01C28"><b>ubuntu</b></font>)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p&apos; &quot;/lib/modules/$(uname -r)/modules.dep&quot;)&quot;
<font color="#A347BA">/etc/rc2.d/S01whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
<font color="#A347BA">/etc/init/whoopsie.conf</font><font color="#2AA1B3">:</font>env CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>default = &apos;<font color="#C01C28"><b>ubuntu</b></font>&apos;
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>        dcd = open(&apos;/var/lib/<font color="#C01C28"><b>ubuntu</b></font>_dist_channel&apos;).read()
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>    &apos;<font color="#C01C28"><b>ubuntu</b></font>&apos;: {
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>        &apos;bug_pattern_url&apos;: &apos;http://people.canonical.com/~<font color="#C01C28"><b>ubuntu</b></font>-archive/bugpatterns/bugpatterns.xml&apos;,
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>        &apos;dupdb_url&apos;: &apos;http://people.canonical.com/~<font color="#C01C28"><b>ubuntu</b></font>-archive/apport-duplicates&apos;,
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>        &apos;distro&apos;: &apos;<font color="#C01C28"><b>ubuntu</b></font>&apos;,
<font color="#A347BA">/etc/apport/crashdb.conf</font><font color="#2AA1B3">:</font>        &apos;bug_pattern_url&apos;: &apos;http://people.canonical.com/~<font color="#C01C28"><b>ubuntu</b></font>-archive/bugpatterns/bugpatterns.xml&apos;,
<font color="#A347BA">/etc/apport/native-origins.d/thunderbird</font><font color="#2AA1B3">:</font>LP-PPA-<font color="#C01C28"><b>ubuntu</b></font>-mozilla-daily
<font color="#A347BA">/etc/apport/native-origins.d/thunderbird</font><font color="#2AA1B3">:</font>LP-PPA-<font color="#C01C28"><b>ubuntu</b></font>-mozilla-daily-thunderbird-aurora
grep: /etc/security/opasswd: Permission denied
grep: /etc/sudoers: Permission denied
<font color="#A347BA">/etc/u-d-c-nvidia-runtimepm-override</font><font color="#2AA1B3">:</font># File created by <font color="#C01C28"><b>ubuntu</b></font>-drivers
<font color="#A347BA">/etc/rc3.d/S01acpid</font><font color="#2AA1B3">:</font>        MODULES=&quot;$(sed -rn &apos;s#^(/lib/modules/[^/]+/)?kernel/(drivers|<font color="#C01C28"><b>ubuntu</b></font>)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p&apos; &quot;/lib/modules/$(uname -r)/modules.dep&quot;)&quot;
<font color="#A347BA">/etc/rc3.d/S01whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
<font color="#A347BA">/etc/bash_completion.d/apport_completion</font><font color="#2AA1B3">:</font># apport-bug <font color="#C01C28"><b>ubuntu</b></font>-bug completion
<font color="#A347BA">/etc/bash_completion.d/apport_completion</font><font color="#2AA1B3">:</font>    <font color="#C01C28"><b>ubuntu</b></font>-bug | apport-bug)
<font color="#A347BA">/etc/bash_completion.d/apport_completion</font><font color="#2AA1B3">:</font>complete -F _apport-bug -o filenames -o dirnames <font color="#C01C28"><b>ubuntu</b></font>-bug
<font color="#A347BA">/etc/PackageKit/Vendor.conf</font><font color="#2AA1B3">:</font>DefaultUrl=https://help.<font color="#C01C28"><b>ubuntu</b></font>.com/community/Repositories/
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>                &lt;allow own=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>		&lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>		       send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>		&lt;allow receive_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>   		       receive_sender=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>		&lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf</font><font color="#2AA1B3">:</font>		&lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.LanguageSelector&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>        &lt;allow own=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>        &lt;allow send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>        &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>           send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>        &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntukylin.softwarecenter.conf</font><font color="#2AA1B3">:</font>        &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>kylin.softwarecenter&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf</font><font color="#2AA1B3">:</font>    &lt;allow own=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.WhoopsiePreferences&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.WhoopsiePreferences&quot; 
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf</font><font color="#2AA1B3">:</font>           send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.WhoopsiePreferences&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.WhoopsiePreferences&quot; 
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.WhoopsiePreferences&quot; 
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf</font><font color="#2AA1B3">:</font>    &lt;allow own=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.SoftwareProperties&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.SoftwareProperties&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf</font><font color="#2AA1B3">:</font>           send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.SoftwareProperties&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.SoftwareProperties&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.DeviceDriver&quot;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf</font><font color="#2AA1B3">:</font>    &lt;allow own=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.USBCreator&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.USBCreator&quot; 
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf</font><font color="#2AA1B3">:</font>           send_interface=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.USBCreator&quot;/&gt;
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.USBCreator&quot; 
<font color="#A347BA">/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf</font><font color="#2AA1B3">:</font>    &lt;allow send_destination=&quot;com.<font color="#C01C28"><b>ubuntu</b></font>.USBCreator&quot; 
<font color="#A347BA">/etc/rc4.d/S01acpid</font><font color="#2AA1B3">:</font>        MODULES=&quot;$(sed -rn &apos;s#^(/lib/modules/[^/]+/)?kernel/(drivers|<font color="#C01C28"><b>ubuntu</b></font>)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p&apos; &quot;/lib/modules/$(uname -r)/modules.dep&quot;)&quot;
<font color="#A347BA">/etc/rc4.d/S01whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
<font color="#A347BA">/etc/xdg/autostart/ubuntu-advantage-notification.desktop</font><font color="#2AA1B3">:</font>Exec=/usr/lib/update-notifier/<font color="#C01C28"><b>ubuntu</b></font>-advantage-notification
<font color="#A347BA">/etc/xdg/autostart/ubuntu-report-on-upgrade.desktop</font><font color="#2AA1B3">:</font>Exec=/usr/bin/<font color="#C01C28"><b>ubuntu</b></font>-report send upgrade
<font color="#A347BA">/etc/xdg/systemd/user/default.target.wants/ubuntu-report.path</font><font color="#2AA1B3">:</font>PathExists=%h/.cache/<font color="#C01C28"><b>ubuntu</b></font>-report/pending
grep: /etc/apt/trusted.gpg.d/ubuntu-keyring-2012-cdimage.gpg: binary file matches
grep: /etc/apt/trusted.gpg.d/ubuntu-keyring-2018-archive.gpg: binary file matches
grep: /etc/apt/trusted.gpg.d/ubuntukylin-archive-keyring.gpg: binary file matches
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># See http://help.<font color="#C01C28"><b>ubuntu</b></font>.com/community/UpgradeNotes for how to upgrade to
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy main restricted
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy main restricted
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates main restricted
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy universe
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy universe
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates universe
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy multiverse
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy multiverse
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates multiverse
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-backports main restricted universe multiverse
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security main restricted
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security main restricted
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security universe
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security universe
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security multiverse
<font color="#A347BA">/etc/apt/sources.list</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security multiverse
<font color="#A347BA">/etc/apt/apt.conf.d/20apt-esm-hook.conf</font><font color="#2AA1B3">:</font>	&quot;[ ! -f /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/apt-esm-json-hook ] || /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/apt-esm-json-hook || true&quot;;
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># See http://help.<font color="#C01C28"><b>ubuntu</b></font>.com/community/UpgradeNotes for how to upgrade to
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy main restricted
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy main restricted
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates main restricted
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy universe
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy universe
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates universe
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy multiverse
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy multiverse
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-updates multiverse
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://in.archive.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font>/ jammy-backports main restricted universe multiverse
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security main restricted
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security main restricted
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security universe
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security universe
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font>deb http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security multiverse
<font color="#A347BA">/etc/apt/sources.list.save</font><font color="#2AA1B3">:</font># deb-src http://security.<font color="#C01C28"><b>ubuntu</b></font>.com/<font color="#C01C28"><b>ubuntu</b></font> jammy-security multiverse
<font color="#A347BA">/etc/update-motd.d/91-contract-ua-esm-status</font><font color="#2AA1B3">:</font>contract_status_stamp=&quot;/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/messages/motd-contract-status&quot;
<font color="#A347BA">/etc/update-motd.d/91-contract-ua-esm-status</font><font color="#2AA1B3">:</font>auto_attach_stamp=&quot;/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/messages/motd-auto-attach-status&quot;
<font color="#A347BA">/etc/update-motd.d/91-release-upgrade</font><font color="#2AA1B3">:</font>if [ -x /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-release-upgrader/release-upgrade-motd ]; then
<font color="#A347BA">/etc/update-motd.d/91-release-upgrade</font><font color="#2AA1B3">:</font>    exec /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-release-upgrader/release-upgrade-motd
<font color="#A347BA">/etc/update-motd.d/10-help-text</font><font color="#2AA1B3">:</font>printf &quot; * Documentation:  https://help.<font color="#C01C28"><b>ubuntu</b></font>.com\n&quot;
<font color="#A347BA">/etc/update-motd.d/10-help-text</font><font color="#2AA1B3">:</font>printf &quot; * Support:        https://<font color="#C01C28"><b>ubuntu</b></font>.com/advantage\n&quot;
<font color="#A347BA">/etc/update-motd.d/50-motd-news</font><font color="#2AA1B3">:</font>[ -n &quot;$URLS&quot; ] || URLS=&quot;https://motd.<font color="#C01C28"><b>ubuntu</b></font>.com&quot;
<font color="#A347BA">/etc/update-motd.d/50-motd-news</font><font color="#2AA1B3">:</font>		https://motd.<font color="#C01C28"><b>ubuntu</b></font>.com)
<font color="#A347BA">/etc/logrotate.d/ubuntu-advantage-tools</font><font color="#2AA1B3">:</font># of /var/log/<font color="#C01C28"><b>ubuntu</b></font>-advantage*.log files.
<font color="#A347BA">/etc/logrotate.d/ubuntu-advantage-tools</font><font color="#2AA1B3">:</font>/var/log/<font color="#C01C28"><b>ubuntu</b></font>-advantage*.log {
<font color="#A347BA">/etc/sysctl.d/10-ptrace.conf</font><font color="#2AA1B3">:</font># https://wiki.<font color="#C01C28"><b>ubuntu</b></font>.com/SecurityTeam/Roadmap/KernelHardening#ptrace
grep: /etc/polkit-1/localauthority: Permission denied
<font color="#A347BA">/etc/update-manager/meta-release</font><font color="#2AA1B3">:</font>URI = https://changelogs.<font color="#C01C28"><b>ubuntu</b></font>.com/meta-release
<font color="#A347BA">/etc/update-manager/meta-release</font><font color="#2AA1B3">:</font>URI_LTS = https://changelogs.<font color="#C01C28"><b>ubuntu</b></font>.com/meta-release-lts
<font color="#A347BA">/etc/update-manager/release-upgrades.d/ubuntu-advantage-upgrades.cfg</font><font color="#2AA1B3">:</font>PostInstallScripts=./xorg_fix_proprietary.py, /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/upgrade_lts_contract.py
grep: /etc/sudoers.d/README: Permission denied
grep: /etc/NetworkManager/system-connections/AndroidAP148E.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/SEC EEE 5F WIFI.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/vivo Y73.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/Galaxy M0101ea.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/PCB Design Lab.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/Test.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/J7 prime.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/ECE 3F IW LH1.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/vivo V29e.nmconnection: Permission denied
grep: /etc/ld.so.cache: binary file matches
grep: /etc/ufw/before.init: Permission denied
grep: /etc/ufw/before.rules: Permission denied
grep: /etc/ufw/before6.rules: Permission denied
grep: /etc/ufw/after.init: Permission denied
grep: /etc/ufw/user6.rules: Permission denied
grep: /etc/ufw/after6.rules: Permission denied
grep: /etc/ufw/after.rules: Permission denied
grep: /etc/ufw/user.rules: Permission denied
grep: /etc/shadow: Permission denied
grep: /etc/pulse/client.conf.d/01-enable-autospawn.conf: No such file or directory
<font color="#A347BA">/etc/depmod.d/ubuntu.conf</font><font color="#2AA1B3">:</font>search updates <font color="#C01C28"><b>ubuntu</b></font> built-in
grep: /etc/brlapi.key: Permission denied
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;dma_buf_te&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;galcore&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;mali[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;nvhost-*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;nvmap&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;pvr_sync&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;renderD[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;tegra_dc_[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;tegra_dc_ctrl&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;vchiq&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;vcsm-cma&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;dma_heap&quot;, KERNEL==&quot;linux,cma&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;dma_heap&quot;, KERNEL==&quot;system&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;drm&quot;, KERNEL==&quot;card[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>TAG==&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software&quot;, SUBSYSTEM!=&quot;module&quot;, SUBSYSTEM!=&quot;subsystem&quot;, RUN+=&quot;/usr/lib/snapd/snap-device-helper $env{ACTION} snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software $devpath $major:$minor&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;dma_buf_te&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;galcore&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;mali[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;nvhost-*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;nvmap&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;pvr_sync&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;renderD[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;tegra_dc_[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;tegra_dc_ctrl&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;vchiq&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>KERNEL==&quot;vcsm-cma&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;dma_heap&quot;, KERNEL==&quot;linux,cma&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;dma_heap&quot;, KERNEL==&quot;system&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>SUBSYSTEM==&quot;drm&quot;, KERNEL==&quot;card[0-9]*&quot;, TAG+=&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;
<font color="#A347BA">/etc/udev/rules.d/70-snap.snap-store.rules</font><font color="#2AA1B3">:</font>TAG==&quot;snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file&quot;, SUBSYSTEM!=&quot;module&quot;, SUBSYSTEM!=&quot;subsystem&quot;, RUN+=&quot;/usr/lib/snapd/snap-device-helper $env{ACTION} snap_snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file $devpath $major:$minor&quot;
<font color="#A347BA">/etc/appstream.conf</font><font color="#2AA1B3">:</font>[<font color="#C01C28"><b>ubuntu</b></font>]
<font color="#A347BA">/etc/appstream.conf</font><font color="#2AA1B3">:</font>ScreenshotUrl=http://screenshots.<font color="#C01C28"><b>ubuntu</b></font>.com
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>      https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/certifications/docs/usg
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>      https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/esm
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>     the service at https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/esm
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>      https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/certifications#fips
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>      You can find out more at https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/certifications#fips.
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>      https://<font color="#C01C28"><b>ubuntu</b></font>.com/security/livepatch
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>    ROS ESM service at https://<font color="#C01C28"><b>ubuntu</b></font>.com/robotics/ros-esm
<font color="#A347BA">/etc/ubuntu-advantage/help_data.yaml</font><font color="#2AA1B3">:</font>    https://<font color="#C01C28"><b>ubuntu</b></font>.com/robotics/ros-esm
<font color="#A347BA">/etc/gdm3/config-error-dialog.sh</font><font color="#2AA1B3">:</font># Author: Gunnar Hjalmarsson &lt;gunnarhj@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/vnd.debian.binary-package=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/vnd.ms-cab-compressed=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/x-cab=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/x-ms-cab-compressed=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/x-deb=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>application/x-debian-package=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software-local-file.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>text/x-c++hdr=<font color="#C01C28"><b>ubuntu</b></font>sdk.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>text/x-c++src=<font color="#C01C28"><b>ubuntu</b></font>sdk.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>text/x-xsrc=<font color="#C01C28"><b>ubuntu</b></font>sdk.desktop
<font color="#A347BA">/etc/gnome/defaults.list</font><font color="#2AA1B3">:</font>x-scheme-handler/snap=snap-store_<font color="#C01C28"><b>ubuntu</b></font>-software.desktop
grep: /etc/cups/ssl: Permission denied
grep: /etc/cups/subscriptions.conf.O: Permission denied
grep: /etc/cups/printers.conf.O: Permission denied
grep: /etc/cups/printers.conf: Permission denied
grep: /etc/cups/subscriptions.conf: Permission denied
grep: /etc/.pwd.lock: Permission denied
<font color="#A347BA">/etc/os-release</font><font color="#2AA1B3">:</font>ID=<font color="#C01C28"><b>ubuntu</b></font>
<font color="#A347BA">/etc/os-release</font><font color="#2AA1B3">:</font>HOME_URL=&quot;https://www.<font color="#C01C28"><b>ubuntu</b></font>.com/&quot;
<font color="#A347BA">/etc/os-release</font><font color="#2AA1B3">:</font>SUPPORT_URL=&quot;https://help.<font color="#C01C28"><b>ubuntu</b></font>.com/&quot;
<font color="#A347BA">/etc/os-release</font><font color="#2AA1B3">:</font>BUG_REPORT_URL=&quot;https://bugs.launchpad.net/<font color="#C01C28"><b>ubuntu</b></font>/&quot;
<font color="#A347BA">/etc/os-release</font><font color="#2AA1B3">:</font>PRIVACY_POLICY_URL=&quot;https://www.<font color="#C01C28"><b>ubuntu</b></font>.com/legal/terms-and-policies/privacy-policy&quot;
<font color="#A347BA">/etc/dpkg/origins/ubuntu</font><font color="#2AA1B3">:</font>Vendor-URL: http://www.<font color="#C01C28"><b>ubuntu</b></font>.com/
<font color="#A347BA">/etc/dpkg/origins/ubuntu</font><font color="#2AA1B3">:</font>Bugs: https://bugs.launchpad.net/<font color="#C01C28"><b>ubuntu</b></font>/+filebug
<font color="#A347BA">/etc/dpkg/origins/default</font><font color="#2AA1B3">:</font>Vendor-URL: http://www.<font color="#C01C28"><b>ubuntu</b></font>.com/
<font color="#A347BA">/etc/dpkg/origins/default</font><font color="#2AA1B3">:</font>Bugs: https://bugs.launchpad.net/<font color="#C01C28"><b>ubuntu</b></font>/+filebug
<font color="#A347BA">/etc/rc5.d/S01acpid</font><font color="#2AA1B3">:</font>        MODULES=&quot;$(sed -rn &apos;s#^(/lib/modules/[^/]+/)?kernel/(drivers|<font color="#C01C28"><b>ubuntu</b></font>)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p&apos; &quot;/lib/modules/$(uname -r)/modules.dep&quot;)&quot;
<font color="#A347BA">/etc/rc5.d/S01whoopsie</font><font color="#2AA1B3">:</font>DAEMON=/bin/sh -c &apos;export CRASH_DB_URL=https://daisy.<font color="#C01C28"><b>ubuntu</b></font>.com; exec whoopsie -f&apos;
<font color="#A347BA">/etc/systemd/system/timers.target.wants/ua-timer.timer</font><font color="#2AA1B3">:</font>ConditionPathExists=/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/private/machine-token.json
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service</font><font color="#2AA1B3">:</font>ConditionPathExists=/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/marker-reboot-cmds-required
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service</font><font color="#2AA1B3">:</font>ConditionPathExists=/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/private/machine-token.json
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service</font><font color="#2AA1B3">:</font>ExecStart=/usr/bin/python3 /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/reboot_cmds.py
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font># sudo systemctl stop <font color="#C01C28"><b>ubuntu</b></font>-advantage.service
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font># sudo systemctl disable <font color="#C01C28"><b>ubuntu</b></font>-advantage.service
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>Documentation=man:<font color="#C01C28"><b>ubuntu</b></font>-advantage https://<font color="#C01C28"><b>ubuntu</b></font>.com/advantage
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>After=network.target network-online.target systemd-networkd.service ua-auto-attach.service cloud-config.service <font color="#C01C28"><b>ubuntu</b></font>-advantage-cloud-id-shim.service
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>ConditionPathExists=!/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/private/machine-token.json
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>ConditionPathExists=|/run/<font color="#C01C28"><b>ubuntu</b></font>-advantage/flags/auto-attach-failed
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>ExecStart=/usr/bin/python3 /usr/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/daemon.py
<font color="#A347BA">/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service</font><font color="#2AA1B3">:</font>WorkingDirectory=/var/lib/<font color="#C01C28"><b>ubuntu</b></font>-advantage/
<font color="#A347BA">/etc/systemd/user/default.target.wants/ubuntu-report.path</font><font color="#2AA1B3">:</font>PathExists=%h/.cache/<font color="#C01C28"><b>ubuntu</b></font>-report/pending
<font color="#A347BA">/etc/systemd/timesyncd.conf</font><font color="#2AA1B3">:</font>#FallbackNTP=ntp.<font color="#C01C28"><b>ubuntu</b></font>.com
<font color="#A347BA">/etc/profile.d/cedilla-portuguese.sh</font><font color="#2AA1B3">:</font># Author: Gunnar Hjalmarsson &lt;gunnarhj@<font color="#C01C28"><b>ubuntu</b></font>.com&gt;
grep: /etc/profile.d/debuginfod.sh: Permission denied
grep: /etc/profile.d/debuginfod.csh: Permission denied
grep: /etc/gshadow-: Permission denied
grep: /etc/alternatives/cpp: binary file matches
grep: /etc/alternatives/rsh: binary file matches
grep: /etc/alternatives/rlogin: binary file matches
grep: /etc/alternatives/shimx64.efi.signed: binary file matches
<font color="#A347BA">/etc/alternatives/open</font><font color="#2AA1B3">:</font>         LXDE|L<font color="#C01C28"><b>ubuntu</b></font>)
grep: /etc/alternatives/netcat: binary file matches
<font color="#A347BA">/etc/alternatives/text.plymouth</font><font color="#2AA1B3">:</font>Description=Text mode theme based on <font color="#C01C28"><b>ubuntu</b></font>-logo theme
<font color="#A347BA">/etc/alternatives/text.plymouth</font><font color="#2AA1B3">:</font>ModuleName=<font color="#C01C28"><b>ubuntu</b></font>-text
<font color="#A347BA">/etc/alternatives/text.plymouth</font><font color="#2AA1B3">:</font>[<font color="#C01C28"><b>ubuntu</b></font>-text]
grep: /etc/alternatives/gdm-theme.gresource: binary file matches
grep: /etc/alternatives/nc: binary file matches
</pre>


grep -w -n world newfile   
## OUTPUT
<pre><font color="#26A269">1</font><font color="#2AA1B3">:</font>Hello <font color="#C01C28"><b>world</b></font>
<font color="#26A269">2</font><font color="#2AA1B3">:</font>hello <font color="#C01C28"><b>world</b></font>
</pre>

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Hello</b></font> world
<font color="#C01C28"><b>hello</b></font> world
</pre>


egrep -w '(H|h)ello' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Hello</b></font> world
<font color="#C01C28"><b>hello</b></font> world
</pre>


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Hello</b></font> world
<font color="#C01C28"><b>hello</b></font> world
</pre>



egrep '(^hello)' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>hello</b></font> world
</pre>


egrep '(world$)' newfile 
## OUTPUT
<pre>Hello <font color="#C01C28"><b>world</b></font>
hello <font color="#C01C28"><b>world</b></font>
Linux is best in this <font color="#C01C28"><b>world</b></font>
</pre>


egrep '(World$)' newfile 
## OUTPUT
<pre>Hello <font color="#C01C28"><b>world</b></font>
hello <font color="#C01C28"><b>world</b></font>
Linux is best in this <font color="#C01C28"><b>world</b></font>
</pre>

egrep '((W|w)orld$)' newfile 
## OUTPUT
<pre>Hello <font color="#C01C28"><b>world</b></font>
hello <font color="#C01C28"><b>world</b></font>
Linux is best in this <font color="#C01C28"><b>world</b></font>
</pre>


egrep '[1-9]' newfile 
## OUTPUT
<pre>Linux is world number <font color="#C01C28"><b>1</b></font>
</pre>


egrep 'Linux.*world' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Linux is world</b></font> number 1
<font color="#C01C28"><b>Linux is best in this world</b></font>
</pre>

egrep 'Linux.*World' newfile 
## OUTPUT
<pre><font color="#C01C28"><b>Linux is world</b></font> number 1
<font color="#C01C28"><b>Linux is best in this world</b></font>
</pre>

egrep l{2} newfile
## OUTPUT
<pre>He<font color="#C01C28"><b>ll</b></font>o world
he<font color="#C01C28"><b>ll</b></font>o world
</pre>


egrep 's{1,2}' newfile
## OUTPUT 
<pre>Linux i<font color="#C01C28"><b>s</b></font> world number 1
Unix i<font color="#C01C28"><b>s</b></font> predece<font color="#C01C28"><b>ss</b></font>or
Linux i<font color="#C01C28"><b>s</b></font> be<font color="#C01C28"><b>s</b></font>t in thi<font color="#C01C28"><b>s</b></font> world
</pre>

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
1002 | tom |  5000 | Admin



sed -n -e '$p' file23
## OUTPUT
1001 | Ram | 10000 | HR



sed  -e 's/Ram/Sita/' file23
## OUTPUT
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR



sed  -e '2s/Ram/Sita/' file23
## OUTPUT
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR



sed  '/tom/s/5000/6000/' file23
## OUTPUT
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR



sed -n -e '1,5p' file23
## OUTPUT
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR



sed -n -e '2,/Joe/p' file23
## OUTPUT
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer




sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer



seq 10 
## OUTPUT
1
2
3
4
5
6
7
8
9
10



seq 10 | sed -n '4,6p'
## OUTPUT
4
5
6



seq 10 | sed -n '2,~4p'
## OUTPUT
2
3
4



seq 3 | sed '2a hello'
## OUTPUT
1
2
hello
3



seq 2 | sed '2i hello'
## OUTPUT
1
hello
2


seq 10 | sed '2,9c hello'
## OUTPUT
1
hello
10


sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
$1003 | Joe |  7000 | Developer



sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
1001 | Ram | 10000 | HR*
1002 | tom |  5000 | Admin*
1003 | Joe |  7000 | Developer*


#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR


cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev



#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
www.yahoo.com
www.google.com
www.mrcet....com


 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
www.yahoo.com
www.google.com
www.mrcet.com



#Backup commands
tar -cvf backup.tar *
## OUTPUT


mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT


tar -xvf backup.tar
## OUTPUT

gzip backup.tar

ls .gz
## OUTPUT
 
gunzip backup.tar.gz
## OUTPUT

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT


cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT

 
ls file1
## OUTPUT

echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
 
abcd
 
echo $?
 ## OUTPUT


 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT



chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT


# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT



# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
##OUTPUT

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
 
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT

 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT

$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT



$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 

 
 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 
 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 


# RESULT:
The Commands are executed successfully.
