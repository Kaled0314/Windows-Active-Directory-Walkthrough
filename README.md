# Windows-Active-Directory-Walkthrough
This project covers what I learned in TryHackMe's Active Directory Basics room. I explored domain structures, user management, PowerShell, GPOs, and RDP through hands-on exercises, building a solid foundation for administering Windows based network environments.
# Skills Learned
- Active Directory Core Concepts
- User & Account Administration
- Windows System Management
- Group Policy Configuration
- PowerShell AD Automation
# Project Walkthrough
In this task, I deleted an Organizational Unit (OU) by enabling advanced features in Active Directory and turning off the built-in accidental deletion protection. Completing this taught me how to carefully manage protected objects while ensuring critical accounts remain intact throughout the process.
<img width="564" height="630" alt="Screenshot 2026-03-10 at 10 58 38 PM" src="https://github.com/user-attachments/assets/45d26f14-da05-42f6-a2bd-5619070a83c8" />


I also got hands-on experience removing and deactivating user accounts within Active Directory, skills that play a key role in securely offboarding employees and keeping inactive accounts from becoming security risks. Properly executing these actions blocks unauthorized access and guarantees that network resources stay accessible only to verified, currently active users.
<img width="567" height="637" alt="Screenshot 2026-03-10 at 10 59 10 PM" src="https://github.com/user-attachments/assets/a4a4cdd6-bba6-4afa-b27a-53d2c5aaa3ba" />


 I explored the process of delegating control in Active Directory, which lets you grant specific users the ability to carry out certain administrative tasks without handing over full domain access. This becomes particularly valuable in bigger environments where duties are distributed across help desk teams or department leads. Working through this showed me how to assign permissions in a controlled and precise way, a critical skill for keeping security tight while still empowering teams to handle their own resources independently.
<img width="561" height="632" alt="Screenshot 2026-03-10 at 10 59 30 PM" src="https://github.com/user-attachments/assets/9139a429-3f35-49d9-8880-005a379a4e13" />

<img width="566" height="630" alt="Screenshot 2026-03-10 at 10 59 42 PM" src="https://github.com/user-attachments/assets/64eae82a-a7b1-4fc0-9996-9de504d3200a" />

After setting up delegation, I connected to a delegated user account through Remote Desktop Protocol and verified the assigned permissions by resetting and updating another user's password. Successfully completing this confirmed that the delegation was configured properly and gave me a clearer picture of how permission changes play out in a real environment. Knowing how to test and verify access rights this way is essential for making sure delegated roles hold the right level of control without granting more access than necessary.
<img width="558" height="622" alt="Screenshot 2026-03-10 at 11 00 06 PM" src="https://github.com/user-attachments/assets/c52d0527-67fe-456b-ac7f-3dd6b51b0e76" />

<img width="560" height="640" alt="Screenshot 2026-03-10 at 11 00 22 PM" src="https://github.com/user-attachments/assets/91f8fad8-7ece-422a-a3e6-023bcb87ea50" />


To better organize computer objects within Active Directory, I built two new OUs named Workstations and Servers. All PCs and laptops were moved into the Workstations OU while the servers were placed into their own dedicated container. Structuring the directory this way makes large scale device management much more straightforward, allows group policies to be applied based on specific device roles, and keeps everything arranged in a clean and logical order.
<img width="554" height="621" alt="Screenshot 2026-03-10 at 11 00 57 PM" src="https://github.com/user-attachments/assets/2552db18-41ef-4cf8-9dce-5d5a5a19ba7f" />

<img width="559" height="623" alt="Screenshot 2026-03-10 at 11 01 10 PM" src="https://github.com/user-attachments/assets/cda3fd6e-55cd-4790-8174-51f04ce27be6" />


I took a closer look at the existing Group Policy Objects and made changes to the Default Domain Policy to tighten up password requirements across the domain, bumping the minimum password length from 7 to 11 characters. Enforcing a longer password requirement like this raises the security bar for every user account in the domain and reflects real world best practices for protecting credentials.
<img width="563" height="631" alt="Screenshot 2026-03-10 at 11 01 27 PM" src="https://github.com/user-attachments/assets/3f041c19-e4b0-4021-95d4-ec260cf27840" />

To prevent non-IT users from reaching the Control Panel, I created a brand new GPO and configured the appropriate restriction settings within it. Once the policy was set up, I linked it to the relevant OUs so it would only take effect for the intended group of users. Walking through this process showed me how precisely targeted policies can be used to enforce security boundaries and limit what users can do, which is a fundamental skill for managing permissions and maintaining tight control across an enterprise environment.
<img width="560" height="621" alt="Screenshot 2026-03-10 at 11 01 57 PM" src="https://github.com/user-attachments/assets/125dff8d-e1e4-453e-8cca-c9093ecf9ac6" />

<img width="556" height="618" alt="Screenshot 2026-03-10 at 11 02 13 PM" src="https://github.com/user-attachments/assets/8e425e85-5790-4fb7-b9f7-a1745ad6fad6" />

To protect against unattended sessions being exploited, I set up automatic screen locking on all workstations and servers after 5 minutes of inactivity. This involved creating a new GPO, dialing in the security settings to enforce the timeout, and linking it to the root domain so every machine in the environment would be covered. Going through this process reinforced how something as straightforward as an inactivity timeout can meaningfully reduce the risk of unauthorized access and strengthen the overall security posture of a corporate environment.
<img width="554" height="620" alt="Screenshot 2026-03-10 at 11 02 30 PM" src="https://github.com/user-attachments/assets/0ba21e62-bcf9-4688-b934-9b131850404c" />

<img width="558" height="621" alt="Screenshot 2026-03-10 at 11 02 41 PM" src="https://github.com/user-attachments/assets/ce8b5d4a-6d4e-4f51-a5c8-980c036dd92b" />

Working through this lab gave me a much deeper understanding of what it actually takes to manage a domain environment securely and efficiently. From removing protected objects and handling user offboarding to assigning delegated permissions and verifying them through RDP, every task reinforced how deliberate and structured AD management needs to be. Organizing machines into dedicated OUs and rolling out Group Policies across the domain showed me firsthand how the right configurations can dramatically improve both security and day to day operations in an enterprise setting.


