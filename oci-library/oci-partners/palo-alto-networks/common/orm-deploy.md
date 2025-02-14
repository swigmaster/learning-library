# Deploy Lab using Oracle Resource Manager

## Introduction

In this lab you will be using Oracle Resource Manager to deploy required virtual cloud networks (VCNs), subnets in each VCN, dynamic routing gateways (DRG), route tables, compute instances and VM Series Firewall instances to support traffic between VCNs.

**PLEASE READ**: If you wish to deploy the configuration manually, please skip **Lab0** and continue from **Lab1** onwards.

Estimated Lab Time: 10 minutes.

### Objectives

   - Create Stack using Oracle Resource Manager
   - Validate Terraform Plan and Apply
   - Connect to Instances

### Prerequisites

- Oracle Cloud Infrastructure paid account credentials (User, Password, Tenant, and Compartment)
- Oracle Marketplace Listings Access
    - **VM Series Firewall** paid listing access required for this **Lab0** 

## **STEP 1: Login and Create Stack using Resource Manager**

You will be using Terraform to create your lab environment.

1.  Click on the link below to download the zip file which you need to build your environment.  

    - Click here: [palo-alto-live-labs.zip](https://objectstorage.us-ashburn-1.oraclecloud.com/p/7o-YPWfKuZFdC05tMiccOiCsskMWOSHw28nHKmJThqPacm0dKNlAKOKwxjBBaNnO/n/partners/b/files/o/palo-alto-live-labs.zip) 
        - Packaged terraform **Palo Alto Networks High Availability** use-case.

2.  Save in your local machine's downloads folder.

3.  Open up the hamburger menu in the left-hand corner.  Choose **Developer Services > Stacks**. Click on **Stacks**: 

    ![](./images/92-ORM-Home-Page.png " ")

4. Choose the right compartment from left hand side drop-down and appropriate region from top right drop-down and click the **Create Stack** button

    ![](./images/93-Create-Stack-Page.png " ")

4.  Select **My Configuration**, choose the **.ZIP FILE** button, click the **Browse** link and select the zip file (palo-alto-live-labs.zip) that you downloaded. Click **Select**.

    ![](./images/94-MyConfiguration-Step1.png " ")

    Enter the following information and accept all the defaults

    - **Name**: Enter a user-friendly name for your **stack** 

    - **Compartment**: Select the Compartment where you want to create your stack. 

    - **Terraform Version**: Validated version for this stack is **0.14.x**

5.  Click **Next**.

    ![](./images/95-MyConfiguration-Step2.png " ")

    Enter/Select the following minimum information. Some information may already be pre-populated. Do not change the pre-populated info.

    **Compute Compartment**: Select Compute Compartment from drop-down where you would like to create compute instances.  **Please Note**: This use-case recommends selecting either your root compartment or your own compartment which is one level below root to support HA failover on VM Series Firewall instances. 

    **Availability Domain:** Select Appropriate AD from drop-down. 

    **Public SSH Key**: Paste the public key string which you would like to use to connect VMs via your private-key.

    **Network Compartment**: Select Network Compartment from drop-down where you would like to create networking components i.e. VCN, subnets, route tables, DRG etc.  

    **Note:**: Keep the Network Strategy as **Create New VCN and Subnet** as default value, if you chose to modify the code you can do so to support existing VCN/Subnet values. 

6. Click **Create** to create your stack. Now you can move next steps to create your environment.

    ![](./images/97-Final-Create-Stack.png " ")

## **Step 2: Terraform Plan and Apply**

When using Resource Manager to deploy an environment, you need to execute a terraform **plan** and **apply**. Let's do that now.

1.  [OPTIONAL] Click **Plan** to validate your configuration. This takes about a minute, please be patient.

    ![](./images/98-Terraform-Plan.png " ")

2.  At the top of your page, click on **Stack Details**.  Click the button, **Apply**. This will create your instances and required configuration.

    ![](./images/99-Terraform-Apply.png " ")

3.  Once this job succeeds, your environment is created! Time to login to your instance to finish the configuration.

    ![](./images/101-Terraform-Apply-Success.png " ")

    **Note**: Stack will deploy **Palo Alto Networks VM-Series Bundle2 - 4 OCPUs** paid listing instances to support this use-case.

## **Step 3: Connect to your instances**

1. Based on your laptop config, choose the appropriate steps to connect to your instances. 

   ![](./images/100-Final-Instances.png " ")

**NOTE**: It will take few minutes before you can connect to ssh-daemon becomes available. If you are unable to connect then make sure you have a valid key, wait a few minutes, and try again.

***Congratulations! You have successfully completed the lab.***

**PLEASE READ**: You must skip **Lab 1 to Lab2** now and proceed to **Lab 3** i.e. **Configure VM Series Firewalls**. 

You may now [proceed to the next lab](#next).

## Learn More
1. [OCI Training](https://cloud.oracle.com/en_US/iaas/training)
2. [Familiarity with OCI console](https://docs.us-phoenix-1.oraclecloud.com/Content/GSG/Concepts/console.htm)
3. [Overview of Networking](https://docs.us-phoenix-1.oraclecloud.com/Content/Network/Concepts/overview.htm)
4. [Familiarity with Compartment](https://docs.us-phoenix-1.oraclecloud.com/Content/GSG/Concepts/concepts.htm)
5. [Connecting to a compute instance](https://docs.us-phoenix-1.oraclecloud.com/Content/Compute/Tasks/accessinginstance.htm)
6. [OCI VM Series Firewall Administration Guide](https://docs.paloaltonetworks.com/vm-series/10-0/vm-series-deployment/set-up-the-vm-series-firewall-on-oracle-cloud-infrastructure.html)

## Acknowledgements

- **Author** - Arun Poonia, Senior Solutions Architect
- **Adapted by** - Palo Alto Networks
- **Contributors** - N/A
- **Last Updated By/Date** - Arun Poonia, July 2021