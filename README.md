# Custom VPN on EC2
*Hosting a custom VPN on an Ubuntu EC2 server.*

This step-by-step guide is intended to show how to host a t2.micro Ubuntu server on EC2 and set up a secure custom VPN using [angristan's script](https://github.com/angristan/openvpn-install).

## Instructions

1. Log into your AWS account and navigate to EC2.
2. Use the [reference](https://github.com/SkyOfSteel/EC2_Tutorial_Documentation) to spin up an Ubuntu instance.
3. On the left panel, click Security Groups to open the settings.
4. In the Security Groups settings, add an inbound rule to allow the traffic from the UDP port 1194:
   - Select Custom UDP in the Type field.
   - In the Port Range field, type 1194.

![Illustration](docs/SG%20example.png "EC2 Security Group - Adding a new rule")

5. 
