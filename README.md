#Official Release October 20, 2014

## Get Started



###Installing the Cookbooks

1. Log in to the appropriate VM as the root user
>ssh root@<ip-address> -i server-cert-key.pem

2. Update Vm and install telnet, wget, and unzip and dependencies
>[root@server ~]# yum update –y
>
>[root@server ~]# yum install -y vim telnet unzip wget git

3. Go to http://gettingstartedwithchef.com/first-steps-with-chef.html and follow the instructions to install Chef on your VM.
>Thank you for installing Chef!

4. Using the instructions on http://gettingstartedwithchef.com/first-steps-with-chef.html, create a cookbook.

5. Install the Marketplace, ServiceMix, or ManageIQ cookbook
>[root@server ~/chef-repo]# knife cookbook site install bah-marketplace
>
or
>
>[root@server ~/chef-repo]# knife cookbook site install servicemix
>
or
>
>[root@server ~/chef-repo]# knife cookbook site install manageiq

6. Run Chef-solo (this could take up to 10 or 15 minutes)
>[root@server ~/chef-repo]# chef-solo –c solo.rb –j roles/bahmarketplace.json
>
>or
>
>[root@server ~/chef-repo]# chef-solo –c solo.rb –j roles/servicemix.json
>
>or
>
>[root@server ~/chef-repo]# chef-solo –c solo.rb –j roles/manageiq.json
>
>Chef Client finished

###Configuring the Cloud Engine
1. Use your favorite command-line accessible text editor to edit the Cloud Engine configruration file:
/opt/cloudengine/servicemix/etc/com.bah.cloudengine.cfg

2. Make the following changes to the file, then write+exit:
 - Insert the Cloud Portal, Engine, or Gateway IP addresses where they are referenced
 - Set "marketplace.restKey" to the Receive-API Key from the Broker Order Communications Page in the Cloud Portal

3. Restart the Cloud Engine
>service servicemix-service restart


## Learn more

Coming Soon

## List of our Repos

 - Cloud Engine
 - ManageIQ
 - Marketplace
 - Cookbooks
 - ?
 - ??

## License

See [LICENSE.txt](LICENSE.txt)

## Export Notice

See [EXPORTNOTICE.txt](EXPORTNOTICE.txt)
