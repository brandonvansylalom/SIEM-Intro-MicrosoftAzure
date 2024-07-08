<h1>Vulnerability Management - Introduction/Entry Level Project</h1>

<h2>Description</h2>
This is a project/lob aimed at understanding vulnerability management. Vulnerability management is the practice of identifying, analyzing and mitigating any vulnerabilities of software within an IT environment. It is an essential area of focus within cybersecurity for safeguarding computer and networks from potential attackers or threat actors that could leverage vulnerabilities to their advantage. I will be using Josh Madakor's tutorial on YouTube to guide me in this project. 

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
<br />
<br />

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


