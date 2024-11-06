<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deploying Active Directory Within Azure</h1>
This tutorial focuses on installing Active Direcotry within the Domain Controller, then making the Client VM a member of the Active Directory Domain.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Remote Desktop Connection
- Active Directory
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server
- Windows 10 Pro

<h2>Installing and Configuring Active Directory</h2>
<p>
<img src="https://i.imgur.com/LKO5JuF.png" height="80%" width="80%" alt="Open Server Manager"/>
<br />
<br />
<img src="https://i.imgur.com/EelYXf6.png" height="80%" width="80%" alt="Add Roles and Features and Select Server"/>
<br />
<br />
<img src="https://i.imgur.com/KJZ0Pa1.png" height="80%" width="80%" alt="Enable Active Directory Domain Services"/>
<br />
<br />
<img src="https://i.imgur.com/80f2cDR.png" height="80%" width="80%" alt="Restart Server and Install"/>
<br />
<br />
<img src="https://i.imgur.com/NiAD9DZ.png" height="80%" width="80%" alt="Promote Server to a Domain Controller"/>
<br />
<br />
<img src="https://i.imgur.com/pWaKrDT.png" height="80%" width="80%" alt="Add New Forest and Name the Domain"/>
<br />
<br />
<img src="https://i.imgur.com/lAGffaB.png" height="80%" width="80%" alt="Domain Controller Login Credentials"/>
<br />
<br />
<img src="https://i.imgur.com/fCcm1fW.png" height="80%" width="80%" alt="Prerquisites and Install"/>
<br />
<br />
<img src="https://i.imgur.com/KQIP2vt.png" height="80%" width="80%" alt="Login as Domain User"/>
<br />
<br />
<img src="https://i.imgur.com/idR0dds.png" height="80%" width="80%" alt="Open Users and Computers"/>
<br />
<br />
<img src="https://i.imgur.com/q8Daod1.png" height="80%" width="80%" alt="Create New Organizational Unit"/>
<br />
<br />
<img src="https://i.imgur.com/OtIOXDj.png" height="80%" width="80%" alt="Create _ADMINS and _EMPLOYEES"/>
<br />
<br />
<img src="https://i.imgur.com/KgeYK1p.png" height="80%" width="80%" alt="Create Admin User"/>
<br />
<br />
<img src="https://i.imgur.com/oNP1IEq.png" height="80%" width="80%" alt="Set Admin Password"/>
<br />
<br />
<img src="https://i.imgur.com/947HP26.png" height="80%" width="80%" alt="Set Member of Domain Admins"/>
<br />
<br />
<img src="https://i.imgur.com/UpLk5Tx.png" height="80%" width="80%" alt="Join Domain on Client VM"/>
<br />
<br />
<img src="https://i.imgur.com/tfKTwA6.png" height="80%" width="80%" alt="Login to Verify Domain Changes"/>
<br />
<br />
<img src="https://i.imgur.com/9KfQauF.png" height="80%" width="80%" alt="Welcome to Domain Message"/>
<br />
<br />
<img src="https://i.imgur.com/RLSyVKf.png" height="80%" width="80%" alt="Observe Client-1 in Active Directory"/>
<br />
<br />
<img src="https://i.imgur.com/jMJGVT1.png" height="80%" width="80%" alt="Create OU _CLIENTS and Move Client-1"/>

