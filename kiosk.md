# Setting Up a Windows 10 Machine to Only Run Horizon View for EIED Engineers

This guide provides detailed instructions for configuring a Windows 10 machine to run exclusively the VMware Horizon View Client for EIED Engineers. This setup ensures a secure and controlled environment, allowing users to access their virtual desktops without any distractions or unnecessary access to system settings. The configuration involves creating dedicated user accounts, renaming the local administrator account, setting up auto-login, configuring kiosk mode, and applying group policies to restrict access to non-essential features. This guide is tailored for EIED Engineers and specifies that the PC should not be joined to the EIED domain and should operate locally.

## Requirements:
- The PC should not be joined to the EIED domain and should operate locally.
- Create a local user named **EIED** with the password **Ask for Password**.
- Rename the local administrator account to **support** with the password **Ask for Password**.
- Install the VMware Horizon Client.

# Steps:

## 1. **Install Horizon View Client:**
   - Download and install the VMware Horizon Client from the [VMware website](https://www.vmware.com/go/viewclients).

## 2. **Create a Dedicated User Account:**
   - Create a new local user account named **EIED** with the password **Ask for Password**.
     1. Open **Settings** > **Accounts** > **Family & other users**.
     2. Click **Add someone else to this PC**.
     3. Select **I don't have this person's sign-in information**.
     4. Select **Add a user without a Microsoft account**.
     5. Enter the username **EIED** and password **Ask for Password**.
     6. Click **Next** to create the account.

## 3. **Rename Local Administrator Account:**
   - Rename the local administrator account to **support** and set the password to **Ask for Password**.
     1. Press `Win + X` and select **Computer Management**.
     2. In the **Computer Management** window, navigate to **System Tools** > **Local Users and Groups** > **Users**.
     3. Right-click on the **Administrator** account and select **Rename**. Change the name to **support**.
     4. Right-click on the **support** account and select **Set Password**. Enter the new password **Ask for Password** and confirm it.

## 4. **Set Up Auto-Login:**
   - Configure the system to automatically log in to the **EIED** account.
     1. Press `Win + R`, type `netplwiz`, and press Enter.
     2. Select the **EIED** user account, uncheck **Users must enter a user name and password to use this computer**, and click **Apply**.
     3. Enter **Ask for Password** in the password fields and click **OK**.

## 5. **Set Up the Horizon Client to Launch at Startup:**
   - Place a shortcut to the Horizon Client in the startup folder.
     1. Press `Win + R`, type `shell:startup`, and press Enter.
     2. Copy the Horizon Client shortcut from the desktop or Start menu and paste it into the startup folder.

## 6. **Configure Kiosk Mode:**
   - Use the built-in kiosk mode in Windows 10 to restrict the account to run only the Horizon Client.
     1. Open **Settings** > **Accounts** > **Family & other users**.
     2. Under **Set up a kiosk** (also known as Assigned Access), click **Get started**.
     3. Choose the **EIED** account.
     4. Select the Horizon Client from the list of apps to run in kiosk mode.

## 7. **Configure Group Policies:**

## A. **Open Group Policy Editor:**
1. Press `Win + R`, type `gpedit.msc`, and press Enter. This will open the Local Group Policy Editor.

## B. **Disable Access to the Control Panel and Settings:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Control Panel**.
2. Double-click **Prohibit access to Control Panel and PC settings**.
3. Set it to **Enabled** and click **OK**.

## C. **Restrict Access to Command Prompt:**
1. Navigate to **User Configuration** > **Administrative Templates** > **System**.
2. Double-click **Prevent access to the command prompt**.
3. Set it to **Enabled** and click **OK**.

## D. **Disable Access to the Registry Editor:**
1. Navigate to **User Configuration** > **Administrative Templates** > **System**.
2. Double-click **Prevent access to registry editing tools**.
3. Set it to **Enabled** and click **OK**.

## E. **Remove Run Command from Start Menu:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Start Menu and Taskbar**.
2. Double-click **Remove Run menu from Start Menu**.
3. Set it to **Enabled** and click **OK**.

## F. **Disable Taskbar Context Menus:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Start Menu and Taskbar**.
2. Double-click **Disable context menus in the taskbar**.
3. Set it to **Enabled** and click **OK**.

## G. **Disable Right-Click Context Menu on Desktop:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Desktop**.
2. Double-click **Remove Desktop context menu**.
3. Set it to **Enabled** and click **OK**.

## H. **Remove Notifications and Action Center:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Start Menu and Taskbar**.
2. Double-click **Remove Notifications and Action Center**.
3. Set it to **Enabled** and click **OK**.

## I. **Prevent Access to Administrative Tools:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Windows Components** > **File Explorer**.
2. Double-click **Prevent access to drives from My Computer**.
3. Set it to **Enabled**.
4. In the **Options** section, select the drives you want to restrict (for example, restrict access to all drives) and click **OK**.

## J. **Hide Specified Control Panel Items:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Control Panel**.
2. Double-click **Hide specified Control Panel items**.
3. Set it to **Enabled**.
4. Click **Show** under **List of disallowed Control Panel items**.
5. Add items such as **System**, **Devices and Printers**, **Network and Sharing Center**, and any other Control Panel items you want to hide.
6. Click **OK** twice.

## K. **Disable Changing Proxy Settings:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.
2. Double-click **Disable changing proxy settings**.
3. Set it to **Enabled** and click **OK**.

## L. **Limit Network Settings Modifications:**
1. Navigate to **User Configuration** > **Administrative Templates** > **Network** > **Network Connections**.
2. Double-click **Prohibit access to properties of a LAN connection**.
3. Set it to **Enabled** and click **OK**.
4. Double-click **Prohibit access to properties of a VPN connection**.
5. Set it to **Enabled** and click **OK**.

## 8. **Set Up Automatic Reconnection:**
   - Configure the Horizon Client to automatically reconnect if the connection is lost.
     1. Open the Horizon Client and connect to the Horizon server.
     2. In the connection settings, enable options such as **Auto-connect to this server** and **Reconnect automatically**.

## 9. **Remove Unnecessary Software:**
   - Uninstall or disable any software or services that are not required for running the Horizon Client to reduce potential distractions or security risks.

By following these steps, you can create a dedicated Windows 10 environment for EIED Engineers that runs only the VMware Horizon View Client, ensuring a controlled and simplified user experience.
