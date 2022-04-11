![image](images/pitschiLogoWithCopyright.png)

Pitschi (Particle Imaging depoT using Storage caCHing Infrastructure) is a data repository that is built on top of [Clowder data management framework](https://github.com/clowder-framework/). 

Pitschi aims to:
* provide an end-to-end process: from capturing, transferring raw data to storage collections and indexing the data
* use one storage collection per project
* harvest as much metadata as possible
* provide simple ways for users to deposit data

Pitschi is quite unique in that:
* It is integrated with the [PPMS booking system](https://www.stratocore.com/) 
* It is integrated with the [UQ RDM](https://research.uq.edu.au/rmbt/uqrdm) for data movement and ingestion.


Pitschi provides 2 dataflows for syncing data from instrument computers to storage collection:
* [Direct data to storage collection]((userguide-pitschi.md)): for most of instruments. This solution is integrated with PPMS Tracker. 
* [Transfer via an intermediate computer](userguide-pitschi-datamover.md): applicable for ARM200/300. 
