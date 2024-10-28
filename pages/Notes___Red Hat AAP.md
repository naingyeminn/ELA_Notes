## Installation
- ### Getting Red Hat Developer Subscription
	- Create a Red Hat Developer account at https://developers.redhat.com/register if you don't have one
	- (OR)
	- If you already have a Red Hat account:
		- Go to https://developers.redhat.com
		- Click on Login and type in the username and password or with External SSO (Microsoft, GitHub, or Google)
		- You will get Agreement page to accept everything for signing up as a Developer
	- Your Red Hat account will be eligible for a Developer Subscription in a few minutes
	- You can check it at https://access.redhat.com/management or at the new portal https://console.redhat.com/subscriptions/inventory
- ### Setting up the environment for RHCE
	- Install RHEL 9.0 on VM as a **Server** 
	  > Not Minimal or Server with GUI
	- Register the VM
		- ```shell
		  sudo subscription-manager register
		  username: your-redhat-account
		  password:
		  ```
	- Get the Pool ID of your Red Hat Developer Subscription for Individuals
		- ```shell
		  sudo subscription-manager list --available
		  ```
	- Attach the subscription by using Pool ID
		- ```shell
		  sudo subscription-manager attach --pool <pool-id-of-your-developer-subscription>
		  ```
	- (OR)
	- Attach the subscription automatically
		- ```shell
		  sudo subscription-manager attach --auto
		  ```
	- Lock the release version 9.0 to match with the RHCE Exam Environment
		- ```shell
		  sudo subscription-manager release --set=9.0
		  ```
	- Enable the Ansible Automation Platform 2.2 Repository
		- ```shell
		  sudo subscription-manager repos --enable ansible-automation-platform-2.2-for-rhel-9-x86_64-rpms
		  ```
	- Install Ansible Navigator
		- ```shell
		  sudo dnf install ansible-navigator -y
		  ```
	-
- ## Disclaimer
	- **The Red Hat Developer Subscription for Individuals** is intended for personal use and is not meant for commercial or organizational purposes. This subscription allows an individual to use certain Red Hat Subscription Services for "Individual Development Use" and "Individual Production Use."
	- **Individual Development Use** encompasses activities such as software development (including open-source software), prototyping, quality assurance testing, and demonstration purposes.
	- **Individual Production Use** refers to any use beyond Individual Development Use, including using the software in a production environment, with live data and/or applications, or for backup instances.
	- The Individual Developer Subscription grants the right to run Red Hat Software included in the subscription on a maximum of 16 Physical Nodes or Virtual Nodes, for either Individual Development Use and/or Individual Production Use.
	- Any use of the Individual Developer Subscription that deviates from the defined terms would be a violation of the Red Hat Enterprise Agreement. Examples of such violations include exceeding the 16-node limit or engaging in commercial activities like selling or distributing the subscription services.