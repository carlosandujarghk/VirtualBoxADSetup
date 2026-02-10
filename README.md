<p align="center">
<img width="300" height="168" alt="68747470733a2f2f692e696d6775722e636f6d2f705535413538532e706e67" src="https://github.com/user-attachments/assets/2c6a3bc8-fc6b-4efd-94e6-4dcae76e7b68" />
</p>

<h1>Introduction</h1>
Jobs ask for Active Directory experience. Virtual Box let’s you practice at home. This lab simulates a small business environment.<br />
<br />
Even though there are a lot of options for starting a networking lab I noticed a plenty of jobs looking for experience in Active Directory. But how can you as an IT Support Specialist in training practice these skills in your personal virtual machine? This project describes the method I used to build a simple, practical Active Directory lab in VirtualBox. It’s easy to set up and a great way to get started with real-world IT concepts.<br />

<h2>Environments and Technologies Used</h2>

- Virtual Box software (FOSS)
- Windows Server 2019/2022 ISO which came be downloaded Microsoft’s website. Comes with an 180-day trial.

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Hardware: At least 16GB RAM, 100GB free disk recommended.
- <b>Attended installation</b> versus <b>unattended installation:</b><br />
An attended installation requires the user to be present and actively interact with the installation process, such as responding to prompts, accepting the user agreement, or configuring disk partitions. In contrast, an unattended installation is a hands-free process that requires no user input, as all installation steps are executed automatically based on predefined settings.
<br />

<h1>Domain Controller Setup</h1>:<br />
<h2>Installating Windows Server 2022</h2>

<p>
<img width="780" height="456" alt="Create Virtual Machine options" src="https://github.com/user-attachments/assets/d0d95a6c-4cd1-4234-a937-df51bd9ed7a7" />
</p>
<p>
1.	Open VirtualBox -> New<br />
2.	Name: DC1 (short for Domain Controller) or whatever you want.<br />
3.	Folder: Where the VM machines files will be located<br />
4.	ISO image: The downloaded Windows 2022 Server image<br />
5.	Edition: Windows Server Standard 2022 (Desktop Experience)**<br />
6.	Type: Microsoft Windows<br />
7.	Version: Microsoft Windows Server 2022<br />
8.	Hardware → At least 4GB Ram, 1 CPU core<br />
9.	Hard Disk → 40GB-50GB<br />
10.	Finish<br />
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
