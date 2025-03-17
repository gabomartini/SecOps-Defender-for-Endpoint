<p align="center">
  <img src="https://github.com/user-attachments/assets/ee292cc5-5865-46c1-8425-cbc6da0c73c6" width="150" height="auto">
  <h1 align="center">Security Operations with Microsoft Defender for Endpoint</h1>
</p>

#### *In this tutorial we will:*
*- Gain hands-on experience in configuring and managing Microsoft Defender for Endpoint.*

*- Develop security operations skills, including threat detection and incident response.*

*- Learn how to onboard devices, configure security policies, and analyze security incidents.*

#### Tasks:
1.  Set up and configure Microsoft Defender for Endpoint.
2.  Onboard a device to Defender for Endpoint.
3.  Assign and configure security roles for managing Defender for Endpoint.
4.  Define and configure device group settings for access control.
5.  Verify device connection to Defender for Endpoint and run a detection test.
6.  Analyze security alerts and incidents.
7.  Execute a simulated attack scenario to evaluate threat response.
8.  Review incident details and security responses to the attack scenario.

## Task 1. Set up and configure Microsoft Defender for Endpoint.

In this task, you'll perform the initialization of the Microsoft Defender for Endpoint.
 
1.	Go to the Defender XDR portal at https://security.microsoft.com. On the Defender XDR portal, from the navigation menu on the left, scroll down and expand the System section and select Settings.
2.  On the Settings page, select Device discovery.

<p align="center">
<img src="https://github.com/user-attachments/assets/e67ca9b9-0f1d-453c-bc07-1c359b670337">
</p>

3.	In Discovery setup, make sure Standard discovery (recommended) is selected.

<p align="center">
<img src="https://github.com/user-attachments/assets/ecafdd7a-0248-482a-94d8-f607311d12ce">
</p>

## Task 2. Onboard a device to Defender for Endpoint.

In this task, you'll onboard a device to Microsoft Defender for Endpoint using an onboarding script.
 
1.	In the Defender XDR portal, from the navigation menu on the left, scroll down and expand the System section and select Settings, then from the Settings page select Endpoints.
2.	Select Onboarding in the Device management section.
3.	In the "1. Onboard a device" area make sure "Local Script (for up to 10 devices)" is displayed in the Deployment method drop-down and select the "Download onboarding package button".

<p align="center">
<img src="https://github.com/user-attachments/assets/c9e2913a-0e65-44ed-860c-6faf88ae3304">
</p>

4.	Under the Downloads pop-up, highlight the GatewayWindowsDefenderATPOnboardingPackage.zip file with your mouse and select the folder icon Show in folder.

<p align="center">
<img src="https://github.com/user-attachments/assets/43ace70f-c45c-4f1e-a675-794e80c67aac">
</p>

5.	Right-click the downloaded zip file and select Extract All..., make sure that Show extracted files when complete is checked and select Extract.
6.	Right-click on the extracted file WindowsDefenderATPLocalOnboardingScript.cmd and select Properties. Select the "Unblock" checkbox in the bottom right of the Properties windows and select "OK".
7.	Right-click on the extracted file WindowsDefenderATPLocalOnboardingScript.cmd again and choose Run as Administrator. Hint: If you encounter the Windows SmartScreen window, select on More info, and choose Run anyway.
8.	When the User Account Control window is shown, select "Yes" to allow the script to run and answer Y to the question presented by the script and press Enter. When complete you should see a message in the command screen that says Successfully onboarded machine to Microsoft Defender for Endpoint.
 
<p align="center">
<img src="https://github.com/user-attachments/assets/fc0db161-5240-41e2-8ef3-65b5534e76bb">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/cd4e13df-b0bc-439e-8669-602785aa8818">
</p>

9.	Press any key to continue. This closes the Command Prompt window.

## Task 3. Assign and configure security roles for managing Defender for Endpoint.

In this task, you'll configure roles for use with device groups.
 
1.	In the Microsoft Defender XDR portal left menu bar, scroll down and select "Settings", then select "Endpoints".
2.	Select "Roles" under the Permissions area. Select the "Turn on roles" button, then select "+ Add role".

<p align="center">
<img src="https://github.com/user-attachments/assets/65087c4a-3aec-484f-a6bb-fd9880ebf98b">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/a0088af7-4acd-49dc-84cd-1fc5f1dba6ae">
</p>

3.	In the Add role dialog, enter the following: Role name: "1st Level Support", Permissions:	"Advanced Live Response capabilities". Select "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/452c402a-03e9-449b-b0a2-05c2cb3bf177">
</p>

4.	On the Assigned user groups page, type sg-IT in the Filter user groups form, and then select "Add selected groups". Make sure it appears under Azure AD user groups with this role.

<p align="center">
<img src="https://github.com/user-attachments/assets/5fef1e7a-448c-4e97-a01b-3e39934b032c">
</p>

5.	Select "Submit" and then "Done" when finished.

<p align="center">
<img src="https://github.com/user-attachments/assets/468a0f64-5e7f-4b94-ab1c-7fef148ff8f3">
</p>

## Taks 4. Define and configure device group settings for access control.

In this task, you'll configure device groups that allow for access control and automation configuration.
 
1.	In the Microsoft Defender XDR portal left menu bar, select "Settings", then select "Endpoints". Then select "Device groups" under the "Permissions area".

<p align="center">
<img src="https://github.com/user-attachments/assets/1da2a57a-45d7-4427-af6d-630f6034ae39">
</p>

2.	Select "+ Add device group" icon and enter the following information on the General tab: Device group name: Normal, Remediation level: Full - remediate threats automatically. Select "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/01d8645c-8972-4446-9652-fe032092285a">
</p>

3.	On the Devices tab, for the OS condition select Windows 10 and select "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/0cd91c00-4c7b-44a5-8424-366a6696e649">
</p>

4.	On the Preview devices tab, the Show preview button could show the virtual machine, but most likely the data isn't populated yet. Select "Next" to continue.
 
5.	For the User access tab, select sg-IT and then select "Add selected groups" button. Make sure it appears under Azure AD user groups with access to this device group. Select "Submit" and then "Done" when finished.
 
6.	You're going to have two device groups now; the Normal we've created and the Ungrouped devices (default) with the same remediation level.

<p align="center">
<img src="https://github.com/user-attachments/assets/9e583ff9-90c4-4b68-acd7-7b29d2ce3d44">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/09f1c7ce-7535-4c9e-89c2-4e1f07119e89">
</p>

## Task 5: Verify device connection to Defender for Endpoint and run a detection test.

In this task, you will confirm that the device is onboarded successfully and create a test alert.
 
1.	In the Microsoft Defender XDR portal left menu bar, Scroll down and select the Settings, then from the Settings page select Endpoints.
2.	Select "Onboarding" in the Device management section and make sure Windows 10 and 11 is selected as operating system. The First device onboarded message now shows completed.

<p align="center">
<img src="https://github.com/user-attachments/assets/faf62289-7932-44f1-8ee4-fbad685cfafc">
</p>

3.	Scroll down and under the section 2. Run a detection test, copy the detection test script by selecting the Copy button.

<p align="center">
<img src="https://github.com/user-attachments/assets/f3846ac2-bb11-4d22-a140-6a0215b2e7d2">
</p>

4.	In the windows search bar of the virtual machine, type CMD and choose to Run as Administrator on the right pane for the Command Prompt app.
5.	Paste the script by right-clicking in the Administrator: Command Prompt windows and press Enter to run it. The window closes automatically after successfully running the script, and after a few minutes alerts are generated in the Microsoft Defender XDR portal.

## Task 6: Analyze security alerts and incidents.

In this task, you will investigate the alerts and incidents generated by the onboarding detection test script in the previous task.
 
1.	In the Microsoft Defender XDR portal expand "Incidents & alerts" and select "Alerts".
2.	In the Alerts pane, select the alert named [TestAlert] Suspicious PowerShell commandline to load its details.

<p align="center">
<img src="https://github.com/user-attachments/assets/6d10f915-68f4-46ef-9135-f77e6fca2806">
</p>

3.	Review the Alert story timeline, and then review the Details and Recommendations tabs. Under the alert Details tab you can scroll down to the "Incident details" section and select the "Execution incident on one endpoint" link to open the incident.

<p align="center">
<img src="https://github.com/user-attachments/assets/90e86c3f-a71c-482b-801e-99f74aedf5ae">
</p>

4.	In the Microsoft Defender XDR portal select "Incidents & alerts" from the left menu bar, then select "Incidents". Clear the Alert severity filter by selecting the X on the right of the filter.
5.	A new incident called [TestAlert] Suspicious PowerShell commandline appears in the right pane. Select the incident name to load its details.

<p align="center">
<img src="https://github.com/user-attachments/assets/a96d4683-d0cc-4b13-a721-0db640ba452b">
</p>

6.  Select the "Manage incident" link (with a pencil icon) and a new window blade appears.
7.	Under Incident tags type Simulation and select Simulation (Create new) to create a new tag.

<p align="center">
<img src="https://github.com/user-attachments/assets/9d97346c-fac5-43b6-ba09-547cec0f584f">
</p>

8.	Select the toggle Assign to and add your user account (Me) as owner of the incident. Under Informational, expected activity, select "Security testing". Select Save to update the incident and finish.

<p align="center">
<img src="https://github.com/user-attachments/assets/54c335ba-5703-4997-a5d0-00d5e85b4029">
</p>

## Task 7: Execute a simulated attack scenario to evaluate threat response.

In this task, you will simulate an attack on the virtual machine by running a PowerShell script and verify that the attack is detected and mitigated by Microsoft Defender for Endpoint.
 
1.	On the virtual machine Open Microsoft Edge, navigate to "https://github.com/MicrosoftLearning/SC-200T00A-Microsoft-Security-Operations-Analyst/blob/master/Allfiles/recon.txt" and download the recon.txt file from the page.
 
2.	Type PowerShell into the Search bar, then right-click Windows PowerShell and and choose Run as Administrator.
 
3.	When the User Account Control window is shown, select Yes to allow the app to run.
 
4.	Copy and paste the following simulation script into the PowerShell window and press Enter to run it (This script downloads and reads an encoded file (recon.txt), then decrypts its contents using XOR with a predefined key (WinATP-Intro-Injection). Finally, it executes the decrypted PowerShell code, potentially simulating an attack or performing a security test.):
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;
$xor = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');
$base64String = (Get-Content -Path "C:\Users\Admin\Downloads\recon.txt");
Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) }
$i = 0;
$decryptedBytes = @();
$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
$i++; 
if ($i -eq $xor.Length) {
$i = 0
}
}
Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))

5.	The script will produce several lines of output and a message that it Failed to resolve Domain Controllers in the domain. A few seconds later, the Notepad app will open. A simulated attack code will be injected into Notepad. Keep the automatically generated Notepad instance open to experience the full scenario. The simulated attack code will attempt to communicate to an external IP address (simulating a C2 server).

<p align="center">
<img src="https://github.com/user-attachments/assets/dc48650c-f81d-482f-abe2-b4863487e89a">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/8b8c2d93-f323-4124-acc1-04bcc990d59b">
</p>

## Task 8: Review incident details and security responses to the attack scenario.

In this task, you'll analyze a simulated cyber attack using Microsoft Defender XDR. You'll review the attack timeline, investigate alerts, and assess security responses.

1.	In the Microsoft Defender XDR portal expand "Investigation & response" from the left menu bar, then expand "Incidents & alerts" and select "Incidents".
2.	A new incident called Multi-stage incident involving Defense evasion & Discovery on one endpoint is in the right pane. Select the incident name to load its details.

<p align="center">
<img src="https://github.com/user-attachments/assets/8aefb4c9-1975-4706-9565-0d6312db1133">
</p>

3.	Under the Attack story tab, collapse the Alerts and Incident details panes to view the full Incident graph.

<p align="center">
<img src="https://github.com/user-attachments/assets/24f9bb42-3e7b-41e9-9eda-89eef66d0a01">
</p>

4.	Mouse over and select the Incident graph nodes to review the entities.
5.	Re-expand the Alerts pane (left-side) and select the Play attack story Run icon. This shows the attack timeline alert by alert and dynamically populates the Incident graph.
6.	Review the contents of the Attack story, Alerts, Assets, Investigations, Evidence and Response, and Summary tabs. Devices and Users are under the Assets tab. Hint: Some tabs might be hidden due the size of your display. Select the ellipsis tab (...) to make them appear.
7.	Under the Evidence and Response tab, select IP addresses then select the displayed IP address. In the pop-up window review the IP address details and scroll down and select the Open IP address page button.
8.	Review the contents of the Ip address page Overview, Incidents & alerts and Observed in organizations tabs. Some tabs may not contain and information for the IP address.

<p align="center">
<img src="https://github.com/user-attachments/assets/39ae36dc-31fb-4633-83ad-cbc7651dd9ce">
</p>
