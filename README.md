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
- Active Directory User and Groups
- Step 4

<h2>Deployment and Configuration Steps</h2>


**Step 1: Set up Microsoft Azure enviornment**



![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/64d43699-5a3a-48ac-916d-0e0128d32c07)










    Verify Typology of the Microsoft Enviornment.
    Two VM Networks are shown in the same resource group.  Client-1 and DC-1 are shown below. 
    Client one will host windows 10 and DC-1 will host the Domain Controller.





![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/669ddb35-0b26-406f-b09a-381c61a15999)










**Step 2:  Configure Domain Controller**
  
    2.1 Select DC-1 from the home page

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/6b2ae01f-2fb7-48bd-b53e-196412a0f781)








    2.3 Select Networking

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/03a25e05-525b-42f0-8d20-dd660ee94a45)






    2.4 Select Network Interface

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/b7aa3f2e-e58c-44dd-b4df-c091bf637092)





    2.5 Select IP configurations

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/c6fb005b-6bde-4bba-8db1-71fc3eac76e3)



    2.6 Select IP config

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/5cc44eae-5c7e-48ec-8fdc-7d027753e59c)








    2.7 Change the allocation to Static and do not forget to save ;)

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/95465be4-b757-415b-a64c-9be772532f59)










</p>
<br />

    2.8  Echo request to confirm connection


      A. Configure DC-1 Firewall inbound rules set to YES and allow ICMPv4 protocol Echo request

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/0577b08b-7ed6-43f9-a660-9cf0b406020f)











      B. Ping DC-1 from Client-1 remote desktop using the command ping -t followed by the IP address. 

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/11a32cc4-0183-4bfb-87a2-a0f6584d7285)







      C. After confirmation of ping is complete simply input ctrl+c.

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/720bda4b-6dd6-4932-8f66-0f85c9629975)







**Step 3: Active Directory Users and Groups**

     3.1 Login to DC-1 and install Active Directory Domain Services

        From Manage, select roles and Features.  Then on server selection chose Active Directory Domain
        

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/d4e20c9d-adc1-4f71-a2de-94737fe8ba5a)







    3.2 Promote as a DC: Set up a new forest as mydomain.com



            A. Promote
            

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/8e628819-0c0e-4e36-a215-266e03bd6775)









            B. Set up Forest

            

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/b254b747-3951-401d-b253-413c00782d75)











            C. Install and Restart



![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/25d30a93-d463-45a9-964d-fec9232c1ba5)













    
            D. Login to the DC as mydomain.com\Labuser



![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/cc01484a-4c9e-46aa-ba02-d5357bac64e4)


        3.3 Users and Computers
            
            A. Select Tools and then active Directory Users and Computers.

            

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/9ae63276-eaa3-49f2-abb3-33738e49fac3)







            B. Create organizational Unit

                Slecet mydomain.com and right click new Organizational Unit



![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/0652eb7d-aef5-4489-a758-2d7c3916f80e)






            C. Create _EMPLOYEES and _ADMIN units

            

_EMPLOYEES


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/9c76924f-35bf-4f55-8c99-499f2398bfc4)






_ADMIN


![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/88cc27a7-3b22-4558-a6f4-ca480e02c5b3)







            D. Now we will create Users

            Right Click _ADMINS and select New Users

            
![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/2f2a2cb6-87dd-4433-8765-9695e1f6731b)





            E. FIll in the appropriate informations and select next

![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/cee1344c-c7d6-4eeb-a4c2-53042ae91b2c)








            F. Inout password and select options appropriate to your organization
                Select next review and finish.



![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/ac8cc12c-41f0-4c3d-b956-173882418d26)





![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/e0a464cf-c923-437b-bd55-84847dc8093b)














In "member of" tab then select Add... and enter Check names.  Select Domain Admins.




![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/66d805f1-114a-45e7-9a10-88c416ab02ce)







![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/95a16c85-9978-49f5-bcc7-578bbca64db2)







![image](https://github.com/Forevermorewon/configure-ad/assets/145600604/60b1e837-eba4-43f3-a9d8-945acd640383)























    




































































<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Step one we confirm that our Microsoft Azure enviornment is set up correctly.
</p>
<br />


