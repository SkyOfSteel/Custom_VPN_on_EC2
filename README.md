# Custom VPN on EC2
*Hosting a custom VPN on an Ubuntu EC2 server.*

This step-by-step guide is intended to show how to host a t2.micro Ubuntu server on EC2 and set up a secure custom VPN using [angristan's script](https://github.com/angristan/openvpn-install).

## Instructions

1. Log into your AWS account and navigate to EC2.
2. Use the [reference](https://github.com/SkyOfSteel/EC2_Tutorial_Documentation) to spin up a Ubuntu instance, allow SSH connections over port 22 in the instance's Security Group and create a pair of security keys for the SSH login.
3. On the left panel of the EC2 menu, click Security Groups to open the settings.
4. In the Security Groups settings, add an inbound rule to allow the traffic from the UDP port 1194:
   - Select Custom UDP in the Type field.
   - In the Port Range field, type 1194.

![Illustration](docs/SG%20example.png "EC2 Security Group - Adding a new rule")

5. Log into your new EC2 instance via SSH by following the [reference](https://github.com/SkyOfSteel/EC2_SSH_Login).
6. In the browser, navigate to the [openvpn-install](https://github.com/angristan/openvpn-install) repository.
7. In the SSH terminal, run the following commands from the Readme in the [openvpn-install](https://github.com/angristan/openvpn-install) repository one by one to install OpenVPN:

   ```
   sudo curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
   sudo chmod +x openvpn-install.sh
   sudo ./openvpn-install.sh
   ```
8. Confirm the default settings for OpenVPN on the Ubuntu server.
9. After the installation is complete, an `.OVPN` file will be created in the current EC2 directory.
10. Copy the `.OVPN` file to your computer.
11. Launch OpenVPN on your computer, right-click the OpenVPN icon in the tray and click Import.
12. Select the `.OVPN` file from your computer and click Open.
    
![Illustration](https://github.com/SkyOfSteel/Custom_VPN_on_EC2/blob/main/docs/OpenVPN%20example.png "Adding an .OVPN file to OpenVPN")

13. Right-click the OpenVPN icon in the tray again, hover the mouse over the name of your VPN server and click Connect.
