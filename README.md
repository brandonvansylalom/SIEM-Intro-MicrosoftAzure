<h1>Vulnerability Management - Introduction/Entry Level Project using Nessus</h1>

<h2>Description</h2>
This is a project/lab aimed at understanding vulnerability management. Vulnerability management is the practice of identifying, analyzing and mitigating any vulnerabilities of software within an IT environment. It is an essential area of focus within cybersecurity for safeguarding computer and networks from potential attackers or threat actors that could leverage vulnerabilities to their advantage. I will be using Josh Madakor's tutorial on YouTube to guide me in this project so I can familiar and hands-on with vulnerability management and the tools used.

<br>
<br/>

<b>ALL CREDITS ON THIS PROJECT GOES TO JOSH MADAKOR. <b> 

<br/>
<img src="https://imgur.com/A348GjI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
<h2>Environments/Tools Used </h2>

- <b>Windows 10 ISO file
- <b>VMware
- <b>Nessus</b>
- <b>Windows OS workstation with at least 8 GB RAM (recommended but it's okay if not)

<h2>Lab walk-through/details:</h2>

<p align="center">

To start, we will need to download VMware workstation, Windows 10 ISO, , and the Nessus scanner.

- https://www.vmware.com/products/workstation-player/workstation-player-evaluation.html.html).
- https://www.microsoft.com/en-us/software-download/windows10ISO.
- https://www.tenable.com/products/nessus/nessus-essentials.
- Use the free versions of each download listed (Register for Nessus Essentials and VMware 17 non-commercial when downloaded).
- Once Nessus is downloaded, it is recommended to save the Nessus link somewhere you can access it easily.
- Nessus will email you an activation code (you'll need it to continue with Nessus install).

<br />
<br />
<img src="https://imgur.com/MGfr6Cv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/0a8zwuQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/V0z34mo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

The ISO and VMware installs are all standard/defaults. Once on Nexus download:

- Connect via SSL
- Continue (skip the register offline page)
- Register for Nessus Essential (the free version)
- Skip to the activation code (it should have been emailed to you during the download. if not, continue with name and email to get one)
- Make a username and password for administrator control, something you won't forget. You should be on the below page at this point, afterwards it'll take a minute to initialize:

<br />
<br />
<img src="https://imgur.com/TkCSjgd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/XQ0ZRdV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

While waiting for Nexus to initialize, we will head to the VMware workstation.

- Open up VMware
- Go the Player drop down, File, and then new
- Find Browse and locate the Windows 10 ISO within your File Explorer to mount the ISO and then hit Next

<br />
<br />
<img src="https://imgur.com/DMAN8Il.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Name the ISO VM whatever you like/appropriately
- Next, for the disk size I kept it at 50 GB and the second option
- Next, Customize hardware. If you don't know how much RAM you have, you can keep it at 2 GB. I set mines to 4 GB because I run 16 GB on my workstation.

<br />
<br />
<img src="https://imgur.com/JLgaHQM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Continuing on Customize Hardware, you can leave the CPU cores (I left it) but if you know how much, feel free to adjust to the appropriate amount
- Go to Network Adapter (NAT), change the Network connection to Bridged. This will allow the VM to be on the same physical network as your workstation/computer, and making Nessus talk to the VM for the purpose of this lab.

<br />
<br />
<img src="https://imgur.com/MOK9StO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/vuDjjIE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Now, we will install Windows 10 on the VM.

- After Finishing, the VM will start. Make sure to press any key as fast as you can or you'll get an error. You'll have to restart the VM and do it again.
- Hit next and keep the defaults
- Install now
- I don't have a product key
- Windows 10 Pro
- Accept the terms/license then next
- Custom install
- Keep the preselected Disk (that's the only one you can do anyways) and hit next. It'll take a moment to install as well

<br />
<br />
<img src="https://imgur.com/Qa3lO4K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Once Windows VM finishes, use the following:

- US Region (or whatever your locality you are based out of it)
- US keyboard (or whatever you like/locality)
- Skip adding a second layout
- Offline account
- Make it admin, any password you can remember
- Security Questions are up to you on your answer
- Accept or uncheck doesn't matter
- Not now for Cortana
- Once done, with both the VM and Nessus setup, you should be here:

<br />
<br />
<img src="https://imgur.com/RVxs3aA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/xsK6oNW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Now we'll get into doing some basic scans first.

- Go the VM
- Go to Command Prompt and type in ipconfig
- Grab the IP from your VM and ping it from YOUR workstation
- x.x.x.x -t

<br />
<br />
<img src="https://imgur.com/ksfQZ6L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- We will go back to the VM and disable some features on the firewall
- Go to your VM, Type here to search on the desktop page task bar, type wf.msc
- Select Windows Defender Firewall Properties
- For the first THREE tabs of that property, turn the firewall state to OFF

<br />
<br />
<img src="https://imgur.com/Rst3PS9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Hit Ok and go back to the command prompt on YOUR workstation
- You will now see replies from the ping due to us turning off the firewall on the VM

<br />
<br />
<img src="https://imgur.com/bBJxtq6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Head to your Nessus scanner webpage.

- We will do basic network scan
- Select create a new scan, basic network scan, and enter the following in:
- Use the IP address of the VM

<br />
<br />
<img src="https://imgur.com/FfeCGQh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Once saved, it'll be on your My Scans page. It won't run unless you schedule it to or press play/run
- Press the play button on the right side to run it
- It will now scan our VM for activities/vulnerabilities and it'll take a moment to finish as well
- Once done you should have something like this:

<br />
<br />
<img src="https://imgur.com/VYmaYvN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- In the vulnerabilities tab, you'll see vulnerabilities identified. Blue is informational, yellow is moderate/medium and orange and higher on the color spectrum indicates high/severe/critical.
- When looking at scans, most organizations would probably focus less on the blue and yellow range and more on the higher end vulnerabilities due to them having more of an impact while and they get so many of them that they don't have time to focus on it.

<br />
<br />
<img src="https://imgur.com/donmyW7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Setting up the VM to accept credentialed scans:

- On your VM, go to Services.msc (search bar on taskbar)
- Find Remote Registry, right click, Properties, on the drop down where it says disabled, switch it to Automatic, apply, then ok
- This will allow Nessus to go further into scans on the VM with the credentialing scan

<br />
<br />
<img src="https://imgur.com/FIsI7zb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Next, go to Advanced sharing settings
- Make sure these settings are ON and match:

<br />
<br />
<img src="https://imgur.com/4y909lt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Go to User Account Control Settings
- Set the tab to the lowest like shown below
- This is a no-go in most normal and personal environments but this is a lab and we want to see more scans

<br />
<br />
<img src="https://imgur.com/E53oxMr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Continuing with the credentialed scan configuration, go registry editor
- Go here (Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System)
- Right click anywhere blank on that page, New -> DWORD Value: LocalAccountTokenFilterPolicy
- Right click on the key you created and set value to 1 and save it
- Restart your VM

<br />
<br />
<img src="https://imgur.com/7EikUtD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Sign back into your VM
- Go back to your Nessus scanner page on your workstation
- Check the first scan you did (the check box)
- Go to More, Configure
- Go to Credentials tab, click Windows then enter the credentials for YOUR VM that you created
- Leave everything as it is and we can come back to troubleshoot as needed
- After saving it, go back to your scans, and run the scan again
- AFter it finishes, we will compare the results of the first scan this scan

<br />
<br />
<img src="https://imgur.com/GWFfrQl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Once the scan finishes, inspect the vulnerabilites
- There should be new ones and a few criticals due to the implementations made to the firewall and settings of our VM; this shows how vulnerable a system could be if there are no measures in place to safeguard them.
- Review them and check out as many scans as you can, on the high level/critical ones.

<br />
<br />
<img src="https://imgur.com/G9CVmFh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Installing old FireFox

- On your VM, go to https://ftp.mozilla.org/pub/firefox/releases/3.6.12/win32/en-US/ and install 3.6.12 version of FireFox
- Pick the defaults when installing
- Head back to your workstation and go to Nessus and run the scan; it should detect old FireFox and yield results

Remediating vulnerabilities

- Go to VM
- Type in appwiz.cpl
- Uninstall FireFox
- Run Windows updates
- After it installs, restart
- Go back into your Nessus scanner and do another scan; most of the vulnerabilities we observe should be removed, comparing previous scans from before and to the current one
- 






