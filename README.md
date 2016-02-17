# Ansible LAMP setup

Allows to setup a LAMP server using Ansible. This is for development machine (on vagrant for example) only.

It will install:

- Apache2
- MySql
- Postfix
- Php
- Composer

A bunch of packages:

- tmux (terminal multiplexer)
- mosh  (mobile shell)
- git (Version control)
- vim (File editor)
- libssl-dev (SSL development libraries, header files and documentation)
- curl (command line tool for transferring data with URL syntax)
- wget (command line tool for retrieving files using HTTP, HTTPS and FTP)
- htop (interactive process viewer for Linux)
- tree  (recursive directory listing program)
- python-software-properties
- unzip (command line tool for listing, testing, or extracting files from a ZIP archive)
- ack-grep (grep, optimized for programmers)
- command-not-found (suggest installation of packages in interactive bash sessions)
- dstat (tool for generating system resource statistics)
- debconf (utility for performing system-wide configuration tasks on Unix-like operating systems)
- dmidecode (reports information about your system's hardware as described in your system BIOS according to the SMBIOS/DMI standard)
- ethtool (display or change ethernet card settings)
- iftop (display bandwidth usage on an interface)
- iotop (display io usage on behalf of which process on an interface)
- iperf (TCP/UDP bandwidth measurement tool)
- ltrace (library call tracer)
- nmap (Security Scanner For Network Exploration & Hacking)
- mtr (a network diagnostic tool)
- multitail (interactively tail multiple files)
- ncdu (interactive console disk usage visualizer)
- netcat (reads and writes data across network)
- pstack (attaches to the active processes named by the pids on the command line , and prints out an execution stack trace)
- pv (see the progress of data through a pipeline)
- smem (provides numerous reports on memory usage)
- socat (establishes two bidirectional byte streams and transfers data between them)
- sysstat (utility comprised of several tools that offers advanced system performance monitoring)
- tshark (dump and analyze network traffic)
- whois (command line tool for retrieving WHOIS information of domains)
- rwho (tool to list all users logged in on your network)
- finger (system info about a user)

It will also set the timezone, locales and configure ntp (Network Time Protocol).

This is WIP.

## Dependencies
- [Ansible] (http://www.ansible.com/)

## Installation

1. Clone the repo

	```
	$ git clone git@github.com:davidlonjon/ansible-quick-lamp.git
	```

2. Install ansible roles

	```
	$ ansible-galaxy install -r playbook-requirements.yml -p ./roles/vendors/
	```

3. Create the host file

	```
	$ cp inventory/hosts.dist inventory/hosts
	```

	and uncomment the first line of the `dev` host and set the correct IP as well as if required the `ansible_ssh_user` and the `ansible_ssh_private_key_file`.

4. Create the host var file for the `dev` host

	```
	$ cp host_vars/dev/main.yml.dist host_vars/dev/main.yml
	```

	and setup the variable accordingly.

## Usage

```
$ ansible-playbook playbooks/lamp.yml
```

## Contributing
1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License
The MIT License (MIT)

Copyright (c) 2016 <copyright holders>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.