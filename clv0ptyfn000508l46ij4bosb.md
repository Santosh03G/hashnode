---
title: "SQL Server 2019 Installation Guide [Developer Edition]"
seoTitle: "Step-by-Step SQL Server 2019 Developer Edition Installation Guide"
seoDescription: "Learn how to properly install SQL Server 2019 Developer Edition through this comprehensive guide. Step-by-step instructions for developers to download, setu"
datePublished: Mon Apr 15 2024 08:51:26 GMT+0000 (Coordinated Universal Time)
cuid: clv0ptyfn000508l46ij4bosb
slug: sql-server-2019-installation-guide-developer-edition
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713170636861/6cdba72b-c094-4ca0-a245-5148d8856dff.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1713170675920/05f50939-392c-4581-a16f-0dae5cefdb7c.png
tags: data-science, databases, data-structures, sql, sqlserver

---

Once you have downloaded the .exe file, follow these steps to install and create an instance of SQL Server :

1. Run the .exe file and choose **"Download Media"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167257675/1acc8d07-85f6-4a1e-a0b9-f21e9df7d80d.png align="center")

2. Select your **Language**, choose the **‘ISO’** package and your preferred **Download Location**. Then, click on **‘Download’**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167288722/7d897caa-8917-45d1-b714-4b385ac650b9.png align="center")

3. The downloading process for the ISO package file begins.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167317533/30833a5a-e14d-4a8a-9627-ff52e741de1e.png align="center")

4. On successful download, click on **‘Open Folder’** to locate the ISO file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167368561/0808b610-4d02-4bd0-bd8f-3898e12d8618.png align="center")

5. Right click on the ISO file and click on **‘Mount’** to access the package files.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167429375/c97744ae-0e3d-472e-942a-b8c7567635fb.png align="center")

6. Locate the installation package and setup file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167502959/003e59ca-7f29-4ea6-a2c7-14f60bf0089d.png align="center")

7. Right click on the setup file, and select **"Run As Administrator"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167546509/53e85b27-e5e1-48cc-9d85-55b1ae33fe8d.png align="center")

8. The SQL Server Installation Center opens.  
    Select the first option:  
    **"New SQL Server stand-alone installation or add features to an existing installation"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167582140/713d2511-9aab-414c-9015-eaaa003d7b73.png align="center")

9. In the "Product Key" section, choose the **"Developer"** edition and click on **"Next"**.  
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167614224/c87b052c-50b5-4f8e-b5fb-e523c7ea0f3c.png align="center")

10. Accept the license terms and click on **"Next"**.  
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167654372/ce69411b-2ca0-4852-a492-260d9f309b23.png align="center")

11. Make sure all **"Global Rules"** pass the test and click **"Next"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167714525/84e73277-dac8-466c-9fda-04044dec84f9.png align="center")

12. In the **"Microsoft Update"** window, enable **"Check for Updates"** to allow the installer to automatically check for possible software updates.  
    Click on **"Next"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167757187/bf53cb34-341f-4d1f-a9ec-3b33ee1975c1.png align="center")

13. The setup files will get installed in the next window - **Install Setup Files**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167784529/78c12d05-e56f-45ea-b9e1-4c593a091fb0.png align="center")

14. The "**Feature Selection**" window allows you to select which SQL Server components will be installed.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167818172/4d0add76-0db0-40f3-80ae-e19fa287f038.png align="center")

15. Select the "**Instance features**" as shown below, as they are mandatory for SQL Server to work with Visual Expert. Then, click "Next".
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713167844740/c6d27833-c9f5-4376-9777-1a8ab7ed62fe.png align="center")

16. In the **"Instance Configuration"** window, create a "**VE\_Server**" Named instance and click **"Next"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168273371/e7489813-aa74-413a-90c1-f3fc4488f34e.png align="center")

17. The **"Server Configuration"** window allows users to configure Service Accounts.  
    Click **"Next"** if no change is required in the default account settings.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168316681/acfb50c1-487d-4ef4-922c-e2132b32a249.png align="center")
    
18. In the **Database Engine Configuration** window, under the **Server Configuration** tab, select "Mixed Mode" authentication.  
    Doing so will allow you to set a password for "**System Administrator (sa)**" user.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168368429/5a76fec9-7e49-4413-8730-49e41db60078.png align="center")

19. Click on **"Add Current User"** to set the current user as Administrator for this SQL Server instance. Then, click **"Next"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168393642/818e1b05-7c59-4502-b635-2f60821da298.png align="center")

20. Arriving at the **'Feature Configuration Rules'** window, make sure all the **Rule(s)** pass the installer scanning test. Then, click **'Next'**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168433093/8095715f-7b6c-4ba5-8805-0340597bd08f.png align="center")

21. All configuration steps have been completed. Click "Install" to start the installation.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168482617/a9e7f56a-87e0-494d-b50f-ed6f9010840d.png align="center")

22. The installation begins.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168563694/6a8a21e7-7c1c-4579-906f-ca7f7f504aa7.png align="center")

23.The installation of SQL Server 2019 Developer Edition is completed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1713168642362/7ed800df-c649-41d8-9e67-3af6eed48109.png align="center")