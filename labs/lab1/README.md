# Preliminary activities
## Creation of a virtual network infrastructure in AWS
### Creation of a VPC
Following the [video instructions](https://youtu.be/ApGz8tpNLgo), get this [config setup](assets/vpc_config.pdf) on the VPC.

![vpc_preview](assets/vpc_preview.png)

According to the VPC's route table private subnets have access to the internet.

![public_rt](assets/public_rt.png)
### Creation of two elastic IPs
Following this [video instructions](https://youtu.be/5ZJTESbN9lI), create the elastic IP addresses:

![elastic_ips](assets/elastic_ips.png)
## Creation of a GNU/Linux instance
Then create the [instance](assets/ubuntu_config.pdf) and link the elastic IP address.

The command to `ssh` into the EC2 instance goes as follows:
```bash
ssh -i /path/to/key.pem user@instance-public-dns
```

Replace `path/to/key.pem` with the key file's path and `instance-public-dns` with your elastic IP address. Notice that `user` can vary depending on the AMI.
- **Amazon Linux**: `ec2-user`
- **Ubuntu**: `ubuntu`
- **CentOS**: `centos`
- **RHEL**: `ec2-user` or `root`
- **Debian**: `admin` or `root`

Finally, establish the `ssh` connection:

![ubuntu](assets/ubuntu.png)

> To use the private key file it must be restricted to certain permissions. You might need to `chmod 400 key.pem`.

![neofetch](assets/neofetch.png)
## Creation of a Windows Server 2022 instance
Create the [instance](assets/windows_config.pdf) and associate the elastic IP address.

To connect via RDP protocol, I used `remmina` on [Linux](https://archlinux.org/packages/?q=remmina):

![remmina](assets/remmina.png)

Here is the connection being established:

![windows](assets/windows.png)

And here are the instance specs:

![windows_specs](assets/windows_specs.png)

End of the preliminary tasks. The following activities are in the [lab's report](L01.pdf).

----
# References 
- [Access the AWS Academy platform](https://www.youtube.com/watch?v=iI4cG_fi6vg)
- [How to Create an AWS VPC with Public and Private Subnets](https://youtu.be/ApGz8tpNLgo)
- [How to Create and EC2 Instance in AWS in 2023](https://www.youtube.com/watch?v=MmHWh4p2Sqs)
- [How to create Elastic IP and attach with EC2 instance](https://youtu.be/5ZJTESbN9lI)
- [Network address translation - Wikipedia](https://en.wikipedia.org/wiki/Network_address_translation)
- [Visual private network - Wikipedia](https://en.wikipedia.org/wiki/Virtual_private_network)
- [What is a VPN? - kaspersky](https://www.kaspersky.com/resource-center/definitions/what-is-a-vpn)
