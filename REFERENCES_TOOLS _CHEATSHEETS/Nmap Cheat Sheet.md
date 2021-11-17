
<h3>Nmap Target Selection</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 40%;">Scan a single IP</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Scan a host</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap www.testhostname.com</td>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 40%;">Scan a range of IPs</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap 192.168.1.1-20</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Scan a subnet</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap 192.168.1.0/24</td>
</tr>
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 40%;">Scan targets from a text file</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -iL list-of-ips.txt</td>
</tr>
</table>
<p>These are all default scans, which will scan 1000 TCP ports. Host discovery will take place.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="portselection"></a></p>
<h3>Nmap Port Selection</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 50%;">Scan a single Port</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -p 22 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 50%;">Scan a range of ports</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -p 1-100 192.168.1.1</td>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 50%;">Scan 100 most common ports (Fast)</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -F 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Scan all 65535 ports</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -p- 192.168.1.1</td>
</tr>
</table>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="scantypes"></a></p>
<h3>Nmap Port Scan types</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 40%;">Scan using TCP connect</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sT 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Scan using TCP SYN scan (default)</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sS 192.168.1.1</td>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 40%;">Scan UDP ports</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sU -p 123,161,162 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Scan selected ports - ignore discovery</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -Pn -F 192.168.1.1</td>
</tr>
</table>
<p>Privileged access is required to perform the default <code>SYN</code> scans. If privileges are insufficient a TCP connect scan will be used. A TCP connect requires a full TCP connection to be established and therefore is a slower scan. Ignoring discovery is often required as many firewalls or hosts will not respond to <code>PING</code>, so could be missed unless you select the <code>-Pn</code> parameter. Of course this can make scan times much longer as you could end up sending scan probes to hosts that are not there.</p>
<p>Take a look at the <a href="/nmap-tutorial/">Nmap Tutorial</a> for a detailed look at the scan process.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="servicedetection"></a></p>
<h3>Service and OS Detection</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 40%;">Detect OS and Services</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -A 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Standard service detection</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV 192.168.1.1</td>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 40%;">More aggressive Service Detection</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV --version-intensity 5 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 40%;">Lighter banner grabbing detection</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV --version-intensity 0 192.168.1.1</td>
</tr>
</table>
<p>Service and OS detection rely on different methods to determine the operating system or service running on a particular port. The more aggressive service detection is often helpful if there are services running on unusual ports. On the other hand the lighter version of the service will be much faster as it does not really attempt to detect the service simply grabbing the banner of the open service.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="outputformats"></a></p>
<h3>Nmap Output Formats</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 50%;">Save default output to file</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -oN outputfile.txt 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 50%;">Save results as XML</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -oX outputfile.xml 192.168.1.1</td>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 50%;">Save results in a format for grep</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -oG outputfile.txt 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 50%;">Save in all formats</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -oA outputfile 192.168.1.1</td>
</tr>
</table>
<p>The default format could also be saved to a file using a simple file redirect <code>command > file</code>. Using the <code>-oN</code> option allows the results to be saved but also can be monitored in the terminal as the scan is under way. </p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="nmap-csv"></a></p>
<h3>Nmap Output to CSV</h3>
<p>Nmap by default has no <code>csv</code> output format. Use the <code>XML</code> output to extract the relevant fields into <code>csv</code> with <code>python</code>.</p>
<p>Jump over to <strong>github</strong> and grab our sample script that can be easily modified depending on your requirements. With <code>csv</code> files it is easy to convert into <code>xlsx</code> for reporting. This can be done manually or using our <code>python</code> conversion script.</p>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td><a href="https://github.com/hackertarget/nmap-csv-xlsx" title="Nmap XML output to CSV">Nmap XML to CSV</a></td>
</tr>
</table>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="nsescripts"></a></p>
<h3>Digging deeper with NSE Scripts</h3>
<table class="table table-condensed">
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 30%;">Scan using default safe scripts</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV -sC 192.168.1.1</td>
</tr>
<tr>
<td style="color:#3276B1; width: 30%;">Get help for a script</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap --script-help=ssl-heartbleed</td>
</tr>
<tr class="btx-table-body-row btx-s-bg-bg">
<td style="color:#3276B1; width: 30%;">Scan using a specific NSE script</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV -p 443 –script=ssl-heartbleed.nse 192.168.1.1</td>
<tr>
<td  style="color:#3276B1; width: 30%;">Scan with a set of scripts</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV --script=smb* 192.168.1.1</td>
</tr>
</table>
<p>According to my Nmap install there are currently <strong>581 NSE scripts</strong>. The scripts are able to perform a wide range of security related testing and discovery functions. If you are serious about your network scanning you really should take the time to get familiar with some of them.</p>
<p>The option <code>--script-help=$scriptname</code> will display help for the individual scripts. To get an easy list of the installed scripts try <code>locate nse | grep script</code>. </p>
<p>You will notice I have used the <code>-sV</code> service detection parameter. Generally most NSE scripts will be more effective and you will get better coverage by including service detection.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="ddosreflectors"></a></p>
<h3>A scan to search for DDOS reflection UDP services</h3>
<table>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 30%;">Scan for UDP DDOS reflectors</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap –sU –A –PN –n –pU:19,53,123,161 –script=ntp-monlist,dns-recursion,snmp-sysdescr 192.168.1.0/24</td>
</tr>
</table>
<p>UDP based DDOS reflection attacks are a common problem that network defenders come up against. This is a handy Nmap command that will scan a target list for systems with open UDP services that allow these attacks to take place. Full details of the command and the background can be found on the <a href="https://isc.sans.edu/diary/Using+nmap+to+scan+for+DDOS+reflectors/18193">Sans Institute Blog</a> where it was first posted.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="httpinfo"></a></p>
<h3>HTTP Service Information</h3>
<table>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 40%;">Gather page titles from HTTP services</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap --script=http-title 192.168.1.0/24</td>
</tr>
<tr>
<td  style="color:#3276B1; width: 40%;">Get HTTP headers of web services</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap --script=http-headers 192.168.1.0/24</td>
</tr>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 40%;">Find web apps from known paths</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap --script=http-enum 192.168.1.0/24</td>
</tr>
</table>
<p>There are many HTTP information gathering scripts, here are a few that are simple but helpful when examining larger networks. Helps in quickly identifying what the HTTP service that is running on the open port. Note the <code>http-enum</code> script is particularly noisy. It is similar to <a href="/nikto-website-scanner/">Nikto</a> in that it will attempt to enumerate known paths of web applications and scripts. This will inevitably generated hundreds of <code>404 HTTP responses</code> in the web server error and access logs.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="heartbleed"></a></p>
<h3>Detect Heartbleed SSL Vulnerability</h3>
<table>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 30%;">Heartbleed Testing</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap -sV -p 443 --script=ssl-heartbleed 192.168.1.0/24</td>
</tr>
</table>
<p>Heartbleed detection is one of the available SSL scripts. It will detect the presence of the well known Heartbleed vulnerability in SSL services. Specify alternative ports to test SSL on mail and other protocols <em>(Requires Nmap 6.46)</em>.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="ipinfo"></a></p>
<h3>IP Address information</h3>
<table>
<tr class="btx-table-body-row btx-s-bg-bg">
<td  style="color:#3276B1; width: 30%;">Find Information about IP address</td>
<td style='font-family: "Courier 10 Pitch", Courier, monospace;'>nmap --script=asn-query,whois,ip-geolocation-maxmind 192.168.1.0/24</td>
</tr>
</table>
<p>Gather information related to the IP address and netblock owner of the IP address. Uses ASN, whois and geoip location lookups. See the <a href="/ip-tools/" title="IP and Domain Information Tools">IP Tools</a> for more information and similar IP address and DNS lookups.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="remotescanning"></a></p>
<h3>Remote Scanning</h3>
<p>Testing your network perimeter from an external perspective is key when you wish to get the most accurate results. By assessing your exposure from the attackers perspective you can validate firewall rule audits and understand exactly what is allowed into your network. This is the reason we offer a hosted or <a href="/nmap-online-port-scanner/" alt="online namp" title="Online Nmap Scanning" class="tooltips">online version of the Nmap port scanner</a>. To enable remote scanning easily and effectively because anyone who has played with <code>shodan.io</code> knows very well how badly people test their perimeter networks.</p>
<div class="btx-col-12">
<div class="btx-item js-item-divider btx-divider btx-divider--single btx-center-align">
<div class="btx-divider-line btx-p-border-bg btx-p-border-border" style="width:100%; height:1px;"></div>
</div>
</div>
<p><a id="additionalresources"></a></p>
<h3>Additional Resources</h3>
<p>The above commands are just a taste of the power of Nmap.  Check out our <a href="/nmap-tutorial/">Nmap Tutorial</a> that has more information and tips.<br />
You could also view the full set of features by running Nmap with no options. The creator of Nmap, Fyodor, has a <a href="https://nmap.org/book/">book</a> available that covers the tool in depth.</p>

