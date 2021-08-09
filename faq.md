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



# How do I support maintenance ? 

When you log into PPMS, please use backup code for maintenance purposes. This will stop PPMS from logging usage data and Pitschi from capturing any data. 

The backup code can also be used for users without PPMS accounts.

The backup code will be provided to lab managers and instrument custodians. 


# How do I create an account in the [Pitschi](pitschi.rcc.uq.edu.au) website ?
Pitschi does not support manual account creation. 

Instead, it syncs projects from PPMS with valid RDMs to its database. So if you want to have an account in the [Pitschi](pitschi.rcc.uq.edu.au) website, make sure you are in a PPMS project with valid RDM. 

# Ming's ( Hawken) comments

Test scenarios of PPMS tracker & Pitschi in Hawken lab – Hitachi SU3500B
1.	People forget to log out when they finish the sessions:
Suggestion: It would be great if Tracker interface has more reminding message. At the same time, the trainers will give more education of the clients.
2.	There is no log out confirmation when logging out:
Suggestion: People like me get paranoid if I did not log out properly. Can we give a “log-out confirmation” message when logging out? Yes, UQ login interface does not have a log out confirmation. But it is not money related. People like me prefer there is a proper confirmation message on of log-out. 
3.	More explicit explanation of FAQ:
Suggestion: Clients will worry about their data flow. Can we be more specific about how pitschi handle the data, instead of just using the verb “capture”?
4.	Client A booked session from 3:00 to 5:00 PM. Around 5:00 PM he/she decided to carry on the characterisation till 6:00 PM. Later, he added the “make-up” booking “5:00 PM - 6:00 PM” around 6:00 PM. The row “not booked” of PPMS system did not be overruled by the later “make-up” booking.
Question: will his data from 5:00 to 6:00 PM safely store in the local computer and his own project RDM? How will Pitschi response and how will billing work in this scenario? 
5.	EBSD and probe will have a long-time data acquisition scenario (overnight), no CMM staff will monitor. if a client logged in and set up the parameters and log out. After a couple of hours, he/she came back to log in again and turn off the beam and log out. The real usage time will not be monitored.
Comment: Tracker does not have a solution for this scenario. Can we improve it?
6.	Large dataset transferring: A and B had a back-to-back booking. When A need to log out at the end of session for B, how can we make sure if the data of A has been full transferred to A’s project RDM before switching to B’s RDM?
Suggestion: The data-transfer speed need to be more explained. Some data can be TBs.
Overall Comment:
I believe our centre is meant to provide a robust system and to help the clients to acquire useful data.
1.	Probably only 1% CMM clients would make cheeky booking. But 99% CMM clients are general very nice clients. But they do make silly booking mistakes. The Tracker/ Pitschi need to be more tolerate and forgivable to different scenarios.
2.	Clients care about their data more than the bills. How to make sure their data will be safely handled is very critical for pitschi development.


# I have an existing project in PPMS with an existing RDM. How do I ingest data to Pitschi ?

![Screen Shot 2021-08-09 at 12 05 50 pm](https://user-images.githubusercontent.com/42192079/128654167-7400e2b8-f11b-46bb-be10-70b8b1f50202.png)

![Screen Shot 2021-08-09 at 12 07 26 pm](https://user-images.githubusercontent.com/42192079/128654176-8400fdab-c8ad-4e59-8fac-a346f1176f5d.png)


The current phase of Pitschi rollout does not support existing projects. It means you keep doing what you have been doing. 

# Fee for service - booking

<img width="700" alt="image" src="https://user-images.githubusercontent.com/42192079/123127393-9332f680-d48d-11eb-9aee-673bdfd03299.png">

We decided to not touch the existing projects to minimise service interruptions. Once pitschi is in all the instruments, we will help users ingest existing data into Pitschi. 
