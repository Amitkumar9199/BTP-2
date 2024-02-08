# install centos on VM
1. Download Centos 8.4.2105 from "https://www.linuxvmimages.com/images/centos-8/"
	
	DIRECT DOWNLOAD LINK: https://dlconusc1.linuxvmimages.com/046389e06777452db2ccf9a32efa3760:dldatac/VirtualBox/C/8/CentOS_8.4.2105_VBG.7z
	
	1.1 Extract the CentOS_8.4.2105_VBG.7z file

2. install virtual box 

3. add a vm on virtual box. Select file as "CentOS_8.4.2105_VBG_LinuxVMImages.COM.vbox"

4. change settings. go to networks> advanced

	set the network adapter as nat

 	set the port as 2222 and another port as 22 and remove the local host ip.

5. start the vm

6. type the following command in terminal
	`ssh centos@127.0.0.1 -p 2222`

	password  : centos

7. go to file explorer of your machine(not vm) and type: `ctrl+l`

	now type : `sftp://centos@127.0.0.1:2222`
	
8. Download the yum.repos.d.zip file from "https://mail.google.com/chat/u/0/#chat/space/AAAAUsm_F8s" and extract its contents.

9. copy the contents to centos file explorer(home). and from that working directory open a terminal and run the following command:

	`sudo cp yum.repos.d/* /etc/yum.repos.d/`

10. Now sync with the official repository by doing

	`sudo yum update`

11. Now install git by doing

	`sudo yum install git`

12. Now download the repository of antelope.

	`git clone https://github.com/SHINJ2001/antelope.git`
	

