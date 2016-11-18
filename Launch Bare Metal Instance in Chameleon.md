LAUNCHING A NEW BAREMETAL INSTANCE IN CHAMELEON CLOUD (GUI):
============================================================

1.	Navigate to Project List on the top of the left-hand panel.

2.	Under the Compute tab, click “Instances”. This will bring up the list of current instances running in the project.

3.	Click on the “Launch Instance” button above the list of current instances.

4.	This will bring up the Launce Instance form.

5.	Choose a Reservation lease that you own, if you do not have a lease, obtain one.

6.	Decide on a practical Instance Name.

7.	Select the Flavor “baremetal”.

8.	Input the desired number of Instances.

9.	Select the option to “Boot from image” as the Boot Source.

10.	Select the desired Image Name. 

    a.	This is where a user made snapshot would be located.

11.	Next, select the Access & Security tab and select the appropriate Key Pair.

    a.	If you do not have a current key pair, obtain one.

    b.	This should be your public key.

12.	Click the Launch button at the bottom right hand corner of the form. 

13.	Once this is done, the instance will show up in the list of instances and have a Status that shows it is being created.

14.	At this time, the user can Associate a Floating IP Address.

    a.	This allows the user to access the instance easily.

    b.	Select the “Associate Floating IP” from the tab of the newly created instance’s Action section. 

        i.	Choose from the available addresses

15.	This will create an instance that the user can access and utilize.
