<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deploying Active Directory Within Azure</h1>
This tutorial focuses on installing Active Direcotry within the Domain Controller, and making the Client VM a member of the Active Directory Domain.<br />


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
Connect to the Domain Controller VM via Remote Desktop. <br/>
<img src="https://i.imgur.com/LKO5JuF.png" height="80%" width="80%" alt="Open Server Manager"/>
<br />
<br />
Click on Add roles and features then make your way to Server Selection, this should show our DomainController and it's respective IP. <br/>
<img src="https://i.imgur.com/EelYXf6.png" height="80%" width="80%" alt="Add Roles and Features and Select Server"/>
<br />
<br />
Navigate to Server Roles then enable Active Directory Domain Services -> Add Features. <br/>
<img src="https://i.imgur.com/KJZ0Pa1.png" height="80%" width="80%" alt="Enable Active Directory Domain Services"/>
<br />
<br />
Navigate to Confirmation -> Allow Automatic Restarts -> Install
<img src="https://i.imgur.com/80f2cDR.png" height="80%" width="80%" alt="Restart Server and Install"/>
<br />
<br />
Back to the Server Manager at the top right of the application click on the flag with the caution icon and select Promote this server to a domain controller. <br/>
<img src="https://i.imgur.com/NiAD9DZ.png" height="80%" width="80%" alt="Promote Server to a Domain Controller"/>
<br />
<br />
Select the deployment operation: Add a new forest, type in a Root domain name then Next. <br/>
<img src="https://i.imgur.com/pWaKrDT.png" height="80%" width="80%" alt="Add New Forest and Name the Domain"/>
<br />
<br />
Add and confirm a password for the Domain then Next. Make sure to leave Create DNS delegation unchecked in DNS Options. <br/>
<img src="https://i.imgur.com/lAGffaB.png" height="80%" width="80%" alt="Domain Controller Login Credentials"/>
<br />
<br />
Navigate to Prerequisites Check then click Install. The VM should restart once installed, allow a few minutes before continuing. <br/>
<img src="https://i.imgur.com/fCcm1fW.png" height="80%" width="80%" alt="Prerquisites and Install"/>
<br />
<br />
Remote Desktop into our DomainController VM, now that our Domain is active we will need to login with 'mydomain.com\' before our username. <br/>
<img src="https://i.imgur.com/KQIP2vt.png" height="80%" width="80%" alt="Login as Domain User"/>
<br />
<br />
Navigate to Start -> Windows Adminstrative Tools -> Active Directory Users and Computers and Open. <br/>
<img src="https://i.imgur.com/idR0dds.png" height="80%" width="80%" alt="Open Users and Computers"/>
<br />
<br />
Right-click mydomain.com -> New -> Organizational Unit. We will create both _EMPLOYEES and _ADMINS. <br/>
<img src="https://i.imgur.com/q8Daod1.png" height="80%" width="80%" alt="Create New Organizational Unit"/>
<img src="https://i.imgur.com/OtIOXDj.png" height="80%" width="80%" alt="Create _ADMINS and _EMPLOYEES"/>
<br />
<br />
Right-click _ADMINS -> New -> User then fill out the credentials. When setting the password make sure to uncheck 'User must change password at next logon' and check 'Password nevers expires'. <br/>
<img src="https://i.imgur.com/KgeYK1p.png" height="80%" width="80%" alt="Create Admin User"/>
<img src="https://i.imgur.com/oNP1IEq.png" height="80%" width="80%" alt="Set Admin Password"/>
<br />
<br />
Right-click Jane Doe -> Properties -> Member of -> Add -> Type 'Domain Admins' -> Check Names -> OK -> Apply -> OK. <br/>
<img src="https://i.imgur.com/947HP26.png" height="80%" width="80%" alt="Set Member of Domain Admins"/>
<br />
<br />
Remote Desktop into the Client VM. Now right-click Start -> System -> Renamne this PC (advanced). Click 'Change' then under 'Member of' select domain and type in your domain id then 'OK'. It will now ask for an admin login to allow the changes, for this we will use the janeadmin user we just created. <br/>
<img src="https://i.imgur.com/UpLk5Tx.png" height="80%" width="80%" alt="Join Domain on Client VM"/>
<img src="https://i.imgur.com/tfKTwA6.png" height="80%" width="80%" alt="Login to Verify Domain Changes"/>
<br />
<br />
This pop-up should appear, click 'OK' then the VM will attempt to restart. <br/>
<img src="https://i.imgur.com/9KfQauF.png" height="80%" width="80%" alt="Welcome to Domain Message"/>
<br />
<br />
Remote Desktop into the DC and open Active Directory Users and Computers again. Open the mydomain.com dropdown -> Computers, from here you should observe Client-1 is now listed. We now want to create a new OU named _CLIENTS then drag and drop Client-1 into it. <br/>
<img src="https://i.imgur.com/RLSyVKf.png" height="80%" width="80%" alt="Observe Client-1 in Active Directory"/>
<img src="https://i.imgur.com/jMJGVT1.png" height="80%" width="80%" alt="Create OU _CLIENTS and Move Client-1"/>
<br />
<br />
<h2>Active Directory is Now Deployed and Configured!</h2>
