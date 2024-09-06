# Steps for installation

## 1. Prepare the VPS for installation

- Purchase a new Ubuntu VPS
- Log in to the Host user panel and navigate to the "Your services" section.
- On your VPS click the "Manage" button and select "Rescue System".
- Choose "Debian 10 - Live" from the "Rescue System Version" dropdown menu.
- Set a password and start the Rescue System.
- From the control panel go to "VPS control".
- Click the "Manage" button and select "VNC password".
- Set the VNC password. It must be 8 characters long, containing at least one uppercase, one lowercase character, and one number. Avoid using any special characters.

## 2. Connect to the VPS via SSH

- Open Terminal on MacOS or PuTTY on Windows.
- Log in with the command `ssh root@<MACHINE-IP>` and enter your Rescue System password.
- Replace `20XX` with the version of Windows Server you want to install.
- Now the script supports `[2016][2019][2022]`.
#### step 1
    apt install git -y
#### step 2
    git clone https://github.com/abdulrhman-top/Windows-Server-VPS.git
#### step 3
    cd Windows-Server-VPS
#### step 4
    chmod +x windows-server-20XX-install.sh
#### step 5
    ./windows-server-20XX-install.sh
#
- The process takes approximately 15 minutes and completes when the ssh session disconnects due to the machine rebooting.

## 3. Connnect to the VPS with VNC to install Windows
- Open your VNC app and create a new connection using the IP and PORT found on the VPS control page. Hover over "Manage" and click on "VNC Information"
- Upon connecting, you will see a screen as shown in the image. Press Enter.
  
   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f6a38436b6230782f77696e646f77732d696e7374616c6c65722e706e67" src="https://github.com/user-attachments/assets/ab75fc16-92f1-457a-9dfa-d292356a7efd">

- Follow the on-screen prompts to install Windows.
- Install the virtIO drivers as shown in the following images.
- Click on "Browse"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f7832533562727a2f62726f777365722e706e67" src="https://github.com/user-attachments/assets/a00406ec-a833-4f20-9bcd-7310dcdc16c2">

- From Boot select `virtio_drivers`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f4d67684853786d2f76697274696f2e706e67" src="https://github.com/user-attachments/assets/2141708f-1c53-4178-bc44-e17f02d7fcc0">

- Select `amd64\w10` and click on "Ok"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f6a546d6235374a2f7731302e706e67" src="https://github.com/user-attachments/assets/0200987b-dd30-4808-8ff7-952dab48f860">

- Click on "Next"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f4c5333737134372f6e6578742e706e67" src="https://github.com/user-attachments/assets/bff19a69-ffad-4726-865e-13e8faea914c">

- Click on "Custom: Install Windows Only (advanced)"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f583773776236432f637573746f6d2d696e7374616c6c2e706e67" src="https://github.com/user-attachments/assets/02783a80-9b4f-4414-8585-abf290c7d417">

- For the installation, select the partition `Drive 0 Partition 1`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f6d5371394b6a522f73656c6563742d706172746974696f6e2e706e67" src="https://github.com/user-attachments/assets/42867f18-1f96-4d53-8ce4-863b09f61c60">

- Choose the operating system and then click on "Next"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f324646385737622f6f732d73656c6563742e706e67" src="https://github.com/user-attachments/assets/a87f6f1a-c783-4929-8382-4371ded1ddb1">

## 4. Install the Ethernet adapter for internet connection
- Open the `Device Manager`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f5078475139527a2f6465766963652d6d616e616765722e706e67" src="https://github.com/user-attachments/assets/338cff9c-694b-42e3-925c-9123b36f977e">

- Right-click on `Ethernet Controller` and select `Update Driver`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f59636a663362342f7570646174652d6472697665722e706e67" src="https://github.com/user-attachments/assets/b5348cbb-647c-49ac-93b1-ed1fb178ec0b">

- Choose `Browse my computer for drivers`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f583776687438762f62726f7773652d636f6d70757465722d647269766572732e706e67" src="https://github.com/user-attachments/assets/aa71072d-40d8-42a4-9c87-e155e6171231">

- Click on `Browse` and select the path `C:\sources\virtio`, and click "Next"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f37574a587978572f6472697665722d706174682e706e67" src="https://github.com/user-attachments/assets/116faad6-f122-4bba-b62a-800d2e289869">

- Click on `Install`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f306e71527a4a472f696e7374616c6c2d6472697665722e706e67" src="https://github.com/user-attachments/assets/d259a944-994b-499b-b9cc-1c686b9a9bc6">

## 5. Allow Remote Access Connection for RDP
- Search for `allow remote connections to this computer` and select the first option.

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f586234687751702f616c6c6f772d72656d6f74652e706e67" src="https://github.com/user-attachments/assets/f0469de1-a3b7-48e7-a032-b302fb7d2685">

- In the Remote Desktop section, click on `Show settings`

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f6b4434744e32502f73686f772d73657474696e67732e706e67" src="https://github.com/user-attachments/assets/0f7936c3-a935-4173-99d4-e479e3d66d71">

- Choose `Allow remote connections to this computer`, click "Apply" and then "Ok"

   <img width="600" height="auto" alt="68747470733a2f2f692e6962622e636f2f52763052354c312f616c6c6f772d72656d6f74652d636f6e6e656374696f6e732e706e67" src="https://github.com/user-attachments/assets/5f8d2784-db48-4ed7-b254-f52b6cbce6f1">


- Now, connect remotely using your Remote Desktop Connection program with the credentials created during the Windows installation.


## Conclusions

Congratulations! You should now have a fully operational Windows Server installation on your VPS. 
Remember to proceed with these instructions at your own risk and ensure that all software and applications used are legal and compliant with the respective licenses.




