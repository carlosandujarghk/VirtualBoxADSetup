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

Make sure to select the correct edition which is Windows Server 2022 Standard Evaluation (Desktop Experience) so you have a GUI to work with. If not, only a terminal will be available. You can do everything from the GUI in the terminal but it’s not recommended for beginners.<br />
<br />
<b>Attended installation</b> versus <b>unattended installation:</b><br />
An attended installation requires the user to be present and actively interact with the installation process, such as responding to prompts, accepting the user agreement, or configuring disk partitions. In contrast, an unattended installation is a hands-free process that requires no user input, as all installation steps are executed automatically based on predefined settings. I recommend unattended for now since it's easier and faster.
<br />


<h2>Installing Windows Server 2022 (Unattended)</h2>

<p>
<img width="780" height="456" alt="Create Virtual Machine options" src="https://github.com/user-attachments/assets/d0d95a6c-4cd1-4234-a937-df51bd9ed7a7" />
</p>
<p>
1.  Open VirtualBox -> New<br />
2.  Name: DC1 (short for Domain Controller) or whatever you want.<br />
3.	Folder: Where the VM machines files will be located<br />
4.	ISO image: The downloaded Windows 2022 Server image<br />
5.	Edition: Windows Server Standard 2022 (Desktop Experience)**<br />
6.	Type: Microsoft Windows<br />
7.	Version: Microsoft Windows Server 2022<br />
8.  Uncheck Skip Unattended Installation<br />
9.  Unattended Install → Username: Admin Password: Password123!<br />
10.	Hardware → At least 4GB Ram, 1 CPU core<br />
11.	Hard Disk → 40GB-50GB<br />
12.	Finish<br />
</p>

You should reach the Server Manager Screen:
<p>
<img width="1426" height="775" alt="Server Manager screen" src="https://github.com/user-attachments/assets/baf4c775-3409-4aec-bc15-e1263527b2af" />
</p>

<p>
<img width="1426" height="775" alt="AD features summary" src="https://github.com/user-attachments/assets/eb4ad4f0-6356-4001-87fd-f2018f1cd824" />
</p>
<p>
<img width="1426" height="775" alt="Promoted Domain Controller" src="https://github.com/user-attachments/assets/2327c72f-1f31-4758-ba19-82e1890c78dd" />
</p>
<br />

<h2>Create Your Domain</h2>
<p>
1.	Select Add a new forest.<br />
2.	Root domain name: example.labt<br />
3.	Set a DSRM password (use same Password123! for simplicity).<br />
4.	Accept defaults → Install → VM reboots.<br />
</p>

<p>
<img width="1426" height="775" alt="AD Config Wizard summary" src="https://github.com/user-attachments/assets/90da1af3-9bd2-49d6-b4c6-88bfea39a860" />
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
