<h1>SOC & Honeypot in Azure</h1>

<h2>Description</h2>
Project consists of setting up an instance of Azure Sentinel and a VM also within Azure to display how Sentinel can be utilized show and locate attempted logins from different locations around the globe. The VM was purposely created and configured to be vulnerable to act as a honeypot, which served as a source to collect logs from failed logins. A powershell script was created which utilizes a generated API key from IPGeolocation.io and the function of making a bunch of sample log files that's used to train the Log Analytics workspace. Over time, with the VM made vulnerable, the result are findings of several discoveries and attempts to login to the machine with several different username/password combinations, geographical pin-pointing and what IP's were used to perform the attempts.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Azure Sentinel</b>
- <b>IPGeolocation.io API</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (22H2)
- <b>Microsoft Azure</b>

<h2>Program walk-through:</h2>

<p align="center">
Configure and Launch the VM: <br/>
<img src="https://imgur.com/MJn8fHy.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
RDP into VM and disable Windows Defender: <br/>
<img src="https://imgur.com/91HV6Ru.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
Obtain API key and write script to fetch logins(script must be running in order to obtain logs): <br/>
<img src="https://imgur.com/dyr16g9.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<img src="https://imgur.com/pWY4wzU.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
Create a workspace for log analytics and create queries to parse details from script:  <br/>
<img src="https://imgur.com/VitdeiP.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
Create workbook inside of Sentinel to make adjustments to logs:  <br/>
<img src="https://imgur.com/oSuM8oc.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
Results after 2hrs:  <br/>
<img src="https://imgur.com/amkyy2C.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
<br />
<br />
Results after a full day:  <br/>
<img src="https://imgur.com/360ZB3l.png" height="80%" width="80%" alt="Azure Sentinel Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
