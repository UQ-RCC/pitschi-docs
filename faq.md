# What is the difference between Clowder, 4ceed and Pitschi?

**[Clowder](https://clowderframework.org/)** is a customizable and scalable data management framework to support any data format and multiple research domains. 

**[4ceed](https://4ceed.github.io/)** is a modified version of Clowder, focusing on material sciences. 

**[Pitschi](pitschi.rcc.uq.edu.au/)** is also an instance of Clowder, customised for UQ infrastructure. Pitschi also consists of components to capture data from the instrument computer. 

# How do PPMS and Pitschi behave in these scenarios ?
1) 

  Client A is booked in PPMS from 9am to 11am.
  
  Client A logs into tracker at 9:30am
  
  Client A finishes their experiment and logs out of tracker at 10:30am

>PPMS: The real usage time (9.30 to 10.30) is logged into PPMS backend.

>Pitschi:
>> If the project has an RDM in PPMS, then data is then copied to the project RDM.

>> If the project does not have an RDM in PPMS, nothing is changed

2)
  Client A is booked in PPMS from 9am to 11am

  Client B logs into tracker at 9am and logs out at 11am

>PPMS: PPMS tracker logs client B's usage time in PPMS tracker.

>Pitschi:
>> If the project has an RDM in PPMS, Pitschi will notify client B that he/she has no booking, and thus Pitschi will not capture any data.

>> If the project has no RDM in PPMS, nothing is changed.

3)
  Client A is booked in PPMS from 9am to 11am

  Client B is booked in PPMS from 11am to 1pm

  Client A logs into tracker at 9am and does not log out till 12:30pm

>PPMS: Client A's usage time is recorded in PPMS from 9am till 12.30pm.

> Pitschi
>> If the project has an RDM in PPMS, Pitschi captures data regardless.

>> If the project has no RDM in PPMS, nothing is changed.

4)
  Nobody is booked in PPMS

  Client A logs into tracker at 9am and logs out at 11am

> PPMS: Client A's usage is recorded from 9 am to 11 am.

> Pitschi:
>> If the project has an RDM in PPMS, Pitschi will notify client A that he/she has no booking, and thus Pitschi will not capture any data.

>> If the project has no RDM in PPMS, nothing is changed. 

5) 
  Client A uses an instrument for 10 hours, but only book it for the first and the last hour. The client only logs into PPMS Tracker for the first to setup the experiment and last hour for collecting data. 

> PPMS: PPMS only charges the client for the first and last hour, even though the client uses the machine for 10 hours. 

> Pitschi: 
>> If the project has an RDM in PPMS, Pitschi still captures data generated, However, this is **very risky** as the client might **lose data**. As an example, the experiment will be stopped if there is another session in between the bookings. Also, we will not guarantee that the data are synced properlly to RDM in this particular case.  

>> If the project has no RDM in PPMS, nothing is changed. 
6)
  How do I support maintenance ? 

> When you log into PPMS, please use backup code for maintenance purposes. This will stop PPMS from logging usage data and Pitschi from capturing any data. The backup code can also be used for users without PPMS accounts.



# How do I create an account in the [Pitschi](pitschi.rcc.uq.edu.au) website ?
Pitschi does not support manual account creation. 

Instead, it syncs projects from PPMS with valid RDMs to its database. So if you want to have an account in the [Pitschi](pitschi.rcc.uq.edu.au) website, make sure you are in a PPMS project with valid RDM. 

# I have an existing project in PPMS with an existing RDM. How do I ingest data to Pitschi ?
The current phase of Pitschi rollout does not support existing projects. It means you keep doing what you have been doing. 

We decided to not touch the existing projects to minimise service interruptions. Once pitschi is in all the instruments, we will help users ingest existing data into Pitschi. 