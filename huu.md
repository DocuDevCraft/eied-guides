### How to Upgrade UCS C240 M5 Firmware via HUU for EIED

#### Introduction
Upgrading the firmware of a UCS C240 M5 server is crucial for ensuring optimal performance, security, and access to the latest features. The Host Upgrade Utility (HUU) simplifies this process. This guide provides step-by-step instructions to perform the firmware upgrade using HUU specifically for EIED Network Engineers.

#### Prerequisites
- Ensure you have the HUU ISO file for UCS C240 M5.
- Verify that you have administrative access to the Cisco Integrated Management Controller (CIMC).
- Backup all necessary data before starting the upgrade process.

#### Step-by-Step Instructions

1. **Login to CIMC:**
   - Access the CIMC web interface using your browser.
   - Enter your administrative credentials to log in.

2. **Launch KVM Console:**
   - Once logged in, navigate to the **KVM Console** section and launch the KVM.

3. **Activate Virtual Media:**
   - In the KVM console, go to the **Virtual Media** menu.
   - Select **Activate Virtual Devices** to enable virtual media functionalities.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/1fbd1eed-535e-4f8c-b466-c6af21864535)

4. **Map the HUU ISO File:**
   - After activating the virtual devices, again navigate to the **Virtual Media** menu.
   - Select **Map CD/DVD**.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/0ea6d0d8-07db-4f2f-9a16-95969dc65508)
     
   - Browse to locate the HUU ISO file on your local machine and select it.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/ec23e7d7-7401-4906-85ff-55a03230310d)
     
   - Click **Map Drive** to mount the ISO file to the virtual CD/DVD drive.


5. **Reboot the Server:**
   - From the **Power** menu in the KVM console, select **Reset System (Warm Boot)**.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/2c9e427e-303f-4bbb-9f73-443dbe75db4c)
   - Confirm the reboot action when prompted.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/795e130b-a2b1-4fdd-b0fc-00068d584b4b)

6. **Boot from Virtual Media:**
   - As the server reboots and the Cisco logo appears, press **F7** to access the boot menu.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/53c1d8e7-fa31-41b4-9b8a-d17117cf52f2)
   - Choose the option to boot from the virtual media (CD/DVD) where the HUU ISO is mounted.

7. **Accept the License Agreement:**
   - Once the HUU interface appears, read and accept the License Agreement to proceed.

8. **Update and Activate:**
   - In the HUU interface, press **Update and Activate**.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/7cf400a1-6523-4fed-9355-d6725872893b)
   - Confirm by pressing **Update and Activate** again. Ensure that "Exclude Storage Drives" is unchecked and "Power Cycle to Activate" is checked.
   - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/dc0b0e27-7b95-4324-92d0-f97ee28e48f4)


9. **Monitor the Upgrade Process:**
   - You may lose connection to the KVM during the upgrade process. Wait for the CIMC software upgrade to complete. This can take around 10 minutes.
   - After completion, log in to CIMC again and launch the KVM.

10. **Power On the Server:**
    - If the server is powered off, you need to power it on via the KVM.
    - In the KVM console, from the **Power** menu, choose **Power On System**.

11. **Alternative Power On Method:**
    - If after 10 minutes the server does not power on, try to power it on via the CIMC summary page.
    - Go to the **Host Power** menu in the top right corner and choose **Power On**.
    - ![image](https://github.com/DocuDevCraft/eied-guides/assets/40174881/43abfca6-0acf-4450-a2d0-0d23feb13372)


Follow these steps carefully to ensure a successful firmware upgrade for your UCS C240 M5 server.
