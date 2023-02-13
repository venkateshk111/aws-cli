# AWS Command Line Interface Cheat Sheet

## 3 Ways to Access or interact with AWS Services

1. AWS Management Console = GUI
2. AWS CLI = Command Line Interface
3. AWS SDK = Software Development Kit
## What is AWS CLI ?  
* AWS CLI is a unified tool to **manage your AWS services**. 
* AWS CLI enables you to **interact with AWS services using commands** from your terminal  
* With AWS CLI you can control multiple AWS services from the command line and **automate them through scripts**.

## Supported Terminals
* Linux/Mac shells  – bash, zsh, and tcsh to run commands
* Windows           – GitBash, Command prompt (cmd) or PowerShell.
* Remotely(AWS EC2) – PuTTY, MobaXterm, or AWS Systems Manager.

## Prerequisites
1. AWS Account
2. IAM user with Programmatic Access (Access key and secret key)
3. Install and Configure AWS CLI

## AWS CLI Installation

* Linux
    ```
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    unzip awscliv2.zip
    sudo ./aws/install
    ```
* Mac
    ```
    curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
    sudo installer -pkg AWSCLIV2.pkg -target /
    ```
* Windows
    ```
    msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
    ```
* Verify the installation by running  
    ```
    aws --version
    ```
* Offline Installation file  
    * Linux : https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip  
    * Mac : https://awscli.amazonaws.com/AWSCLIV2.pkg  
    * Windows : https://awscli.amazonaws.com/AWSCLIV2.msi

More Details : [AWS CLI Installation Instructions](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions)
## AWS CLI by Services
1. [IAM](/01-IAM/)
2. [EC2](/02-EC2/)
3. [S3](/03-S3/)
4. [SSM](/04-SSM/)
## AWS Reference links
* [AWS CLI Getting Started](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)
* [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/reference)
* [AWS CLI GitHub Project](https://github.com/aws/aws-cli)
* [AWS CLI Return Codes](https://docs.aws.amazon.com/cli/latest/topic/return-codes.html)
