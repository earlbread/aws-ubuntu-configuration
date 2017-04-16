# AWS Ubuntu Configuration

This is my AWS free tier configuration.

## How to setup server

### Basic security configuration

Connect to ssh as a ubuntu.

    ssh -i ~/.ssh/aws-key.pem ubuntu@aws-ip-address

Set up locale.

    sudo sh -c "echo LC_ALL=en_US.UTF-8 >> /etc/environment"
    source /etc/environment
    export LC_ALL

Download and run [setup script][].

    wget https://raw.githubusercontent.com/earlbread/aws-ubuntu-configuration/master/config_server.sh
    chmod +x ./config_server.sh
    sudo ./config_server.sh

This script changes ssh port to 2200, you need to add inbound rule to AWS security group.

[setup script]: https://github.com/earlbread/aws-ubuntu-configuration/blob/master/config_server.sh

Before install other softwares, upgrade softwares currently installed.

    sudo apt -qy update && sudo apt -qy upgrade
