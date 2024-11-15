# CheckMK2 agent installer
Install, update and remove CheckMK Agent on Windows or Linux with automated scripts.
Furthermore these scripts are adding or removing the client-object in the CheckMK-Server (via API calls).
This implements the same functionality as available on CheckMK2 enterprise edition.

- [Contact](#contact)
- [Licensing](#licensing)
- [Prerequisites](#prerequisites)
- [Run the script](#run-the-script)
  - [Linux](#linux)
  - [Windows](#windows)

<a name="contact"></a>
## Contact
These scripts are maintained by IT.WESER-EMS UG - an ITSM consulting company from Oldenburg, Nothern Germany.
Our focus is implementation, consulting, training and development for
- Znuny ticketing system
- GLPI asset management
- CheckMK2 IT-monitoring

In case of questions, please contact information can be found on https://it-weser-ems.de/.

<a name="licensing"></a>
## Licensing
These scripts originate from Github profile SuitDeer and were slightly changed to optimize them.
Feel free to use them!

<a name="prerequisites"></a>
## Prerequisites
1. No pending changes open in CheckMK instance before running a script.
   - this is to make sure that agent installation does not deploy any other open changes from CheckMK configuration
2. Open web interface from CheckMK server and log-in with an admin account
3. Create a new User (if not already existent) with the following name: `automation`
4. Asign the Role `Administrator` to the `automation`-User.

   ![automation user](images/automation%20user%20(assign%20Administrator%20role).png)

---
<a name="run-the-script"></a>
## Run the script
<a name="linux"></a>
### Linux
1. For all scripts please edit the following variuables:
   - **SERVER_NAME**: IP-Address or DNS name of your CheckMK-Server.
   - **SITE_NAME**: Site where you want to add the host/client-system to.

     More info on "sites" in CheckMK: [https://docs.CheckMK.com/latest/en/intro_setup.html#create_site](https://docs.CheckMK.com/latest/en/intro_setup.html#create_site)

   - **PASSWORD**: Password of the newly created or existent user `automation`

2. After creating or downloading the script please make it executable:

   ```bash
   chmod +x <SCRIPTNAME.sh>
   ```

3. Execute the script with root-rights:

   ```bash
   sudo ./<SCRIPTNAME.sh>
   ```

**All scripts are running about 4 minutes (due to some API calls and further checks.) !!!**

### [install-checkmk.sh](install-checkmk.sh)

### [uninstall-checkmk.sh](uninstall-checkmk.sh)

### [update-checkmk.sh](update-checkmk.sh)

---
<a name="windows"></a>
### Windows

1. For all scripts please edit the following variuables:
   - **SERVER_NAME**: IP-Address or DNS name of your CheckMK-Server.
   - **SITE_NAME**: Site where you want to add the host/client-system to.

     More info on "sites" in  CheckMK: [https://docs.checkmk.com/latest/en/intro_setup.html#create_site](https://docs.checkmk.com/latest/en/intro_setup.html#create_site)

   - **PASSWORD**: Password of the newly created or existent user `automation`

2. Execute the script with administrator-rights:

   ```powershell
   powershell ./<SCRIPTNAME.ps1>
   ```

**All scripts are running about 4 minutes (due to some API calls and further checks.) !!!**

### [install-checkmk.ps1](install-checkmk.ps1)

### [uninstall-checkmk.ps1](uninstall-checkmk.ps1)

### [update-checkmk.ps1](update-checkmk.ps1)

---
