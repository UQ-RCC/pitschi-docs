# Frequently asked questions
1) What is the difference between Clowder, 4ceed and Pitschi?

    **Clowder** is a customizable and scalable data management framework to support any data format and multiple research domains. 

    **4ceed** is an instance of Clowder, that focuses on material sciences. 

    **Pitschi** is also an instance of Clowder, customised for UQ infrastructure. Pitschi also consists of components to capture data from the instrument computer. 

2) Different scenarios

 1.

Client A is booked in PPMS from 9am to 11am

Client A logs into tracker at 9:30am

Client A finishes their experiment and logs out of tracker at 10:30am

 

--->

PPMS: The real usage time (9.30 to 10.30) is logged into PPMS backend.

Pitschi: If the project is new i.e. has an RDM, then data is then copied to the project RDM.

 

2.

Client A is booked in PPMS from 9am to 11am

Client B logs into tracker at 9am and logs out at 11am

 

--->

PPMS: PPMS tracker logs client B's usage time in PPMS tracker.

Pitschi: If the project is new, i.e. has an RDM, Pitschi will notify client B that he/she has no booking, and thus Pitschi will not capture any data.

If the project is an existing one, nothing is changed.

 

 

3.

Client A is booked in PPMS from 9am to 11am

Client B is booked in PPMS from 11am to 1pm

Client A logs into tracker at 9am and does not log out till 12:30pm

 

--->

PPMS: Client A's usage time is recorded in PPMS from 9am till 12.30pm.

Pitschi:

If the project is new, i.e. has an RDM, Pitschi captures data regardless.

If the project is an existing one, nothing is changed.

 

 

4.

Nobody is booked in PPMS

Client A logs into tracker at 9am and logs out at 11am

---->

PPMS: Client A's usage is recorded from 9 am to 11 am.

Pitschi:

If the project is new, i.e. has an RDM, Pitschi will notify client A that he/she has no booking, and thus Pitschi will not capture any data.

If the project is an existing one, nothing is changed. 
