How to Set Up an OpenWrt Guest Isolated Network

In this tutorial, you will learn how to create a guest network on your OpenWrt router that is isolated from your main network. This can be useful for providing internet access to your visitors without compromising your security or privacy.
Step 1: Create a Bridge Device

    Go to Network > Interfaces > Devices and click on Add Device.
    In the Device configuration section, select Bridge device as the Device type.
    Enter br-guest as the Device name.
    Check the box next to Bring up empty bridge.
    Click on Save and then Save & Apply.

Step 2: Add a New Interface

    Go back to the Interfaces tab and click on Add new interface.
    Enter guest as the Name of the new interface.
    Select Static address as the Protocol of the new interface.
    Select br-guest as the Device of the new interface.
    Enter 192.168.0.1 as the IPv4 address and 255.255.255.0 as the IPv4 netmask of the new interface.
    Remove the default gateway check from the advanced settings
    Go to the Firewall Settings tab and click on the dialogue box next to Create / Assign firewall-zone. Type guest and hit Enter.
    goto DHCP server and click on set up DHCP server
    Click on Save and then Save & Apply.

Step 3: Configure Firewall Zone

    Go to Network > Firewall (Zones) and click on Edit next to the guest zone.
    make it look like this
![image](https://github.com/potatosips/openwrt-guest-SSID/assets/118026260/f099f969-0a52-40e1-bf08-1d32a3afc917)

    Click on Save and then Save & Apply.

Step 5: Add a Traffic Rule

    Go to Network > Firewall > Traffic Rules and click on Add.
    make it look like this
![image](https://github.com/potatosips/openwrt-guest-SSID/assets/118026260/60ace02a-707f-42a1-8366-71116ac13cf6)


    Click on Save and then Save & Apply.

Step 6: Edit a Wireless AP

    Go to Network > Wireless and click on Edit next to the wireless AP that you want to use for the guest network. You can also create a new wireless AP by clicking on Add.
![image](https://github.com/potatosips/openwrt-guest-SSID/assets/118026260/8c9b54c6-f727-48bf-b4f4-c82344253dcc)

    Click on Save and then Save & Apply.

Step 7: Isolate Clients

    Go to Network > Wireless and click on Advanced Settings next to the wireless AP that you are using for the guest network.
    Check the box next to Isolate Clients. This will prevent the guest devices from communicating with each other on the same wireless network.
    It should look like this:
![image](https://github.com/potatosips/openwrt-guest-SSID/assets/118026260/1907e0f8-21d0-4df1-aeb9-cd1044bb6e6e)

    Click on Save and then Save & Apply.

Step 8: Test Your Guest Network

    You have successfully set up an OpenWrt guest isolated network. You can now connect your guest devices to the wireless AP that you configured and test the internet access and the isolation from the main network.
    You can also check the status of your guest network by going to Status > Overview and looking at the guest interface and the br-guest device.
