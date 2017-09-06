## General info

* Cloudman console: http://public_DNS/cloud/# => access galaxy and add worker nodes.
* Actual Galaxy instance: http://public_DNS/
* Add admin guide: https://galaxyproject.org/admin/. Add user to ```admin users``` line in /home/ubuntu/galaxy-app/config/galaxy.ini and remember to reboot instance from AWS console
* Customise Galaxy instance guide: https://galaxyproject.org/cloudman/customizing/. For example, to add tools or access toolsheds. Remember to persist changes after you make them
* Manually restart Galaxy instance: 
```sudo su galaxy
cd /mnt/galaxy/galaxy-app
sh run.sh --pid-file=main.pid --log-file=main.log --stop-daemon
sh run.sh --pid-file=main.pid --log-file=main.log --daemon
```

## How to install a tool in the Galaxy instance (temporary, until instance is stopped)

1. Create a user from the galaxy instance web interface
2. Add user to ```admin users``` line in /home/ubuntu/galaxy-app/config/galaxy.ini and remember to reboot instance from AWS console
3. Once you are an admin, log in and click on the Admin tab on the top bar of Galaxy
4. If the desired tool is inluded in either Main or Test toolsheds, navigate ```Tools and Tool Shed``` -> ```Search Tool Shed```, click the one you want and search through the search bar to find the install it.

If the desired tool is custom then follow https://galaxyproject.org/admin/tools/add-tool-tutorial/

## How to install a tool in the Galaxy instance (permanently, persisting through reboots)

[start from https://galaxyproject.org/cloudman/customizing/ and https://galaxyproject.org/admin/tools/add-tool-from-toolshed-tutorial/]

1. SSH to ubuntu@<current_ip_from_AWS> (ask me for pass) to access the file system of the galaxy instance
2. Next, perform the desired changes to the system. The changes supported at this level of instance customization include modifications to the file systems managed by CloudMan. The available file systems are listed on the CloudMan Admin console under entry Persist changes to file system and are mounted on the underlying system under /mnt (e.g., /mnt/galaxy). Modifying contents of these file systems allows you to customize your instance of Galaxy, install or modify tools, as well as modify reference genomes used by Galaxy tools. As you perform the changes, you should respect the ownership of the directories; currently all of these are owned by galaxy user. **Note that if you plan on modifying the Galaxy application, stop the process first from the CloudMan Admin console**.
3.
