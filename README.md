# PNETLab-Installation-on-GCP
Install PNETLab v.6 on GCP

This installation steps is updated from the PNETLab Platform Group on the Telegram (https://t.me/PNETLab) and also searching from other forum, 
Please join to the telegram group for any update of the PNETLab.

1. Open cloud console in GCP, once you are in the CLI, run below command for the PNETLab version 6.
![image](https://github.com/user-attachments/assets/e4f6fac6-43f7-4c33-b8f7-3e81a8d94a38)


- PNETLab version 6 (Ubuntu 20.04):
'''gcloud compute images create nested-ubuntu-focal --source-image-family=ubuntu-2004-lts --source-image-project=ubuntu-os-cloud --licenses https://www.googleapis.com/compute/v1/projects/vm-options/global/licenses/enable-vmx'''


2. Create a VM instance.

Recommendations:
CPU: Intel CPUs Skylake or Cascade

![image](https://github.com/user-attachments/assets/3364b383-4ef4-44f7-a336-da329a0b62a2)
![image](https://github.com/user-attachments/assets/92932c2d-390e-45c2-bcbc-0813aeb02e43)


Disk: SSD for better performance

![image](https://github.com/user-attachments/assets/9d4ff488-cd81-4c3e-8869-666c65b8a365)


- For the boot disk, select the nested image that you created in step 1
- Allow HTTP and HTTPS traffic
- "Deploy a container image” must be UNCHECKED
- Then Create the VM
- After the VM is created, ssh to it and switch to the root user:

Bash :
  '''sudo -i'''

3. Run the installation script for the PNETLab version 6:

Bash :
'''bash -c "$(curl -sL https://drive.labhub.eu.org/0:/upgrades_pnetlab/Focal/install_pnetlab_v6.sh)" '''


Once installation is completed reboot the VM with this command:
'''reboot'''

Wait for few seconds while the VM reboots and ssh to it again.

When the setup wizard screen appears, press ctrl + c and type the below command to switch to the root user:
'''sudo -i'''

You'll get setup wizard again. When it asks you to enter your new root password, enter it twice, give a hostname of choice, domain name of choice, and select DHCP (don't use static ip ), and leave NTP blank.

And that's it. Enjoy PNETLab!

![image](https://github.com/user-attachments/assets/b0b57d0e-5848-4c1d-baf1-7ef575685932)
