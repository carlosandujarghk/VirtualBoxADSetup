<p align="center">
<img width="300" height="168" alt="68747470733a2f2f692e696d6775722e636f6d2f705535413538532e706e67" src="https://github.com/user-attachments/assets/2c6a3bc8-fc6b-4efd-94e6-4dcae76e7b68" />
</p>

<h1>Introduction</h1>
Jobs ask for Active Directory experience. Virtual Box let’s you practice at home. This lab simulates a small business environment.<br />
<br />
Even though there are a lot of options for starting a networking lab I noticed a plenty of jobs looking for experience in Active Directory. But how can you as an IT Support Specialist in training practice these skills in your personal virtual machine? This project describes the method I used to build a simple, practical Active Directory lab in VirtualBox. It’s easy to set up and a great way to get started with real-world IT concepts.<br />

<h2>Environments and Technologies Used</h2>

- Virtual Box software (FOSS)
- Windows Server 2019/2022 ISO which can be downloaded from Microsoft’s website. Comes with an 180-day trial.

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

1.  Open VirtualBox -> New
2.  Name: DC1 (short for Domain Controller) or whatever you want
3.	Folder: Where the VM machines files will be located
4.	ISO image: The downloaded Windows 2022 Server image
5.	Edition: Windows Server Standard 2022 (Desktop Experience)
6.	Type: Microsoft Windows<br />
7.	Version: Microsoft Windows Server 2022
8.  Uncheck Skip Unattended Installation
9.  Unattended Install → Username: Admin Password: Password123!
10.	Hardware → At least 4GB Ram, 1 CPU core
11.	Hard Disk → 40GB-50GB
12.	Finish

As for the actual VM settings I left everything at default. The most important part is the Video Memory in the Display section. Make sure it’s at 128MB and that the ISO is attached Under Settings → Storage, mount the Windows Server ISO.
<p>
<img width="780" height="548" alt="VM Settings" src="https://github.com/user-attachments/assets/584fecb6-c32f-4c36-a379-293716e61966" />
</p>

You should reach the Server Manager Screen:
<br />
<p>
<img width="1426" height="775" alt="Server Manager screen" src="https://github.com/user-attachments/assets/baf4c775-3409-4aec-bc15-e1263527b2af" />
</p>

<h2>Install Active Directory Domain Services (AD DS)</h2>

1. Open Server Manager (auto-launches)
2. Click Add roles and features
3. Installation Type → Role-based or feature-based installation
4. Server Selection → Select a server from the server pool → DC1
5. Server roles → Check Active Directory Domain Services
- Click Add Features → Next → Install
6. After installation, click the yellow flag and promote this server to a domain controller

<p>
<img width="1426" height="775" alt="AD features summary" src="https://github.com/user-attachments/assets/eb4ad4f0-6356-4001-87fd-f2018f1cd824" />
</p>
</ br>
<p>
<img width="1426" height="775" alt="Promoted Domain Controller" src="https://github.com/user-attachments/assets/2327c72f-1f31-4758-ba19-82e1890c78dd" />
</p>

<h2>Create Your Domain</h2>

1.	Select Add a new forest
2.	Root domain name: lab.test
3.	Set a DSRM password (use same Password123! for simplicity)
4.	Accept defaults → Install → VM reboots

<h2>Verify Domain Controller</h2>

After reboot:
1.	Log in as Lab \administrator with your password
2.	Open Active Directory Users and Computers (ADUC)
- You should see your lab.test domain.
3.	Right-click lab.test → New → Organizational Unit
- Name it TestOU → Confirm
4.	Right-click TestOU → New → User
5.	First Name: Test
6.	Last Name: User
7.	User logon name: testuser → testuser@lab.test
8.	Click Next, set a password: Lab123! (uncheck “User must change password at next logon” if you want quick login)
9.	Click Finish

Your TestOU now contains testuser.
You can use this account to log in from a Windows 10 client once it’s joined to the domain.

<p>
<img width="788" height="502" alt="DC online" src="https://github.com/user-attachments/assets/af4c5d54-1b90-47a6-b5d9-8f3921786a35" />
</p>

<h2>Configuring Network</h2>

Control panel -> Network and Internet -> Under Network and Sharing Center click View network status and tasks  -> Change adapter settings

You will see the first Network adapter called Ethernet leave it as it is.
Rename the second NIC to LAN right-click adapter -> Rename. This step is optional, but it helps differentiate between the two.

<p>
<img width="698" height="398" alt="lan2" src="https://github.com/user-attachments/assets/b36072bd-6942-46fb-8b5e-1223b2e71d3e" />
</p>

Right click NIC -> Properties -> Internet Protocol Version 4 (TCP/IPv4) -> Properties

Set a static IP (example):
- IP: 192.168.56.10
- Subnet: 255.255.255.0
- Gateway: leave blank (or your host if bridging).
- DNS: 192.168.56.10 (self, once DC is configured)

<p>
<img width="2010" height="597" alt="networkexample" src="https://github.com/user-attachments/assets/863aa582-9cb8-4230-8abd-1cdea5b08f39" />
</p>

