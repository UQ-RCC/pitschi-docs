# Status
In construction

# Purpose
This technical guide explains the components of Pitschi and how they work together.

# Components
![image](images/pitschi_components.png)

Pitschi relies on the [MeDICI](https://rcc.uq.edu.au/data-storage) for data movement and [UQ RDM](https://research.uq.edu.au/rmbt/uqrdm) for data storage. The booking information is queried from PPMS.

Pitschi consists of the following components:
* **[Clowder](github.com/UQ-RCC/clowder)**: a modified version of the Clowder framework for data management and automatic metadata extraction
* **[XAPI](github.com/UQ-RCC/xapi)**: an API to manage data importation from RDM storage collections. The booking information from PPMS is cached in this XAPI as well. 
* **[Pitschi-cli](github.com/UQ-RCC/pitschi-cli)**: A desktop client residing in the instrument computers for syncing datasets and files to the project's storage collection.  

# Deployment
Pitschi is deployed on a [Docker Swarm Cluster](https://docs.docker.com/engine/swarm/) on top of the [QRISCloud](https://www.qriscloud.org.au/) (OpenStack) research cloud. [Ansible](https://www.ansible.com/) 2.9 is used provision the stack. The deployment code can be found [here](https://github.com/UQ-RCC/ansible-swarm-clowder)




# Data management

# Data ingestion

## Web ingestion
![image](images/webingestion.png)

## RDM ingestion
![image](images/rdm_ingestion.png)