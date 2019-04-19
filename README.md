# multithreading
This project explores multithreading by simulating a hotel using threads to model customer and employee behavior.  

The following rules apply:
The hotel to be simulated has two employees at the front desk to register guests and two bellhops to handle guests’ bags.  A guest will first visit the front desk to get a room number.  The front desk employee will find an available room and assign it to the guest.  If the guest has less than 3 bags, the guest proceeds directly to the room.  Otherwise, the guest visits the bellhop to drop off the bags.  The guest will later meet the bellhop in the room to get the bags, at which time a tip is given.

### Threads:

#### Guest:
1)	25 guests visit the hotel (1 thread per guest created at start of simulation).
2)	Each guest has a random number of bags (0-5).
3)	A guest must check in to the hotel at the front desk.
4)	Upon check in, a guest gets a room number from the front desk employee.
5)	A guest with more than 2 bags requires a bellhop.
6)	The guest enters the assigned room.
7)	Receives bags from bellhop and gives tip (if more than 2 bags).
8)	Retires for the evening.

#### Front Desk:
1)	Two employees at the front desk (1 thread each).
2)	Checks in a guest, finds available room, and gives room number to guest.
3)	A guest must receive their room key before the front desk employee can register the next guest.

#### Bellhop:
1)	Two bellhops (1 thread each).
2)	Gets bags from guest.
3)	The same bellhop that took the bags delivers the bags to the guest after the guest is in the room.
4)	Accepts tip from guest.
 

Other rules:
1)	All mutual exclusion and coordination must be achieved with semaphores.  
2)	A thread may not use sleeping as a means of coordination.  
3)	Busy waiting (polling) is not allowed. 
4)	Mutual exclusion should be kept to a minimum to allow the most concurrency.
5)	Each thread should print when it is created, and main should print when it joins the customer threads.
6)	Each thread should only print its own activities.  The guest threads print guest actions and the employee threads print their own actions.  
7)	Your output must include the same information, same wording, and the same set of steps as the sample output.  Of course, each run can be different depending on the order of thread execution and the random assignments made.
