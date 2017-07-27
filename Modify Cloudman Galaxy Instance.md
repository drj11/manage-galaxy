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
