## General info

* Cloudman console: http://52.23.179.69/cloud/# => access galaxy and add worker nodes.
* Actual Galaxy instance: http://52.23.179.69/
* Add admin guide: https://galaxyproject.org/admin/. Add user to ```admin users``` line in /home/ubuntu/galaxy-app/config/galaxy.ini and remember to reboot instance from AWS console
* SSH to ubuntu@52.23.179.69 (ask me for pass) to access the file system of the galaxy instance
* Customise Galaxy instance guide: https://galaxyproject.org/cloudman/customizing/. For example, to add tools or access toolsheds. Remember to persist changes after you make them
* Manually restart Galaxy instance: 
```sudo su galaxy
cd /mnt/galaxy/galaxy-app
sh run.sh --pid-file=main.pid --log-file=main.log --stop-daemon
sh run.sh --pid-file=main.pid --log-file=main.log --daemon
```
*
## How to install a tool in the Galaxy instance (temporary, until instance is stopped)
1. Create a user from the galaxy instance web interface
2. Add user to ```admin users``` line in /home/ubuntu/galaxy-app/config/galaxy.ini and remember to reboot instance from AWS console
3. Once you are an admin, log in and click on the Admin tab on the top bar of Galaxy
4. If the desired tool is inluded in either Main or Test toolsheds, navigate ```Tools and Tool Shed``` -> ```Search Tool Shed```, click the one you want and search through the search bar to find the install it.
