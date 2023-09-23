<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>

In the modern era of cloud computing, businesses are increasingly leveraging the power of the cloud to enhance their IT infrastructure. On-Premises Active Directory, a staple in enterprise identity management, is no exception to this transformation. With Azure, Microsoft's cloud platform, organizations can seamlessly extend and deploy their existing on-premises Active Directory services to the cloud. This migration to Azure provides numerous advantages, including enhanced scalability, flexibility, and accessibility for remote users. By blending the robustness of on-premises AD with the capabilities of Azure, companies can efficiently manage user identities, access controls, and device policies while embracing the agility and cost-effectiveness of the cloud, ultimately empowering their workforce in the digital age.
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.






<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Microsoft Azure VM Enviornment
- Configure Domain Controller
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

**Step 1: Verify Azure VM Typology**


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/64d43699-5a3a-48ac-916d-0e0128d32c07)











Two VM Networks are shown in the same resource group.  Client-1 and DC-1 are shown below.  Client one will host windows 10 and DC-1 will host the Domain Controller.




![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/669ddb35-0b26-406f-b09a-381c61a15999)










**Step 2:  Set the Domain Controller's NIC Private IP address to be static**

Select DC-1 from the home page


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/6b2ae01f-2fb7-48bd-b53e-196412a0f781)








Select Networking


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/03a25e05-525b-42f0-8d20-dd660ee94a45)






Select Network Interface


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/b7aa3f2e-e58c-44dd-b4df-c091bf637092)





Select IP configurations


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/c6fb005b-6bde-4bba-8db1-71fc3eac76e3)



Select IP config

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/5cc44eae-5c7e-48ec-8fdc-7d027753e59c)








Change the assignment to Static and do not forget to save ;)

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/95465be4-b757-415b-a64c-9be772532f59)































<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Step one we confirm that our Microsoft Azure enviornment is set up correctly.
</p>
<br />


