# Campus-Service-Queue-Manager-School-Activity-
Language used is python


**Campus Service Queue Manager**


This is a Campus Service Queue Manager program that manages tickets issued, called, cancelled, and completed.

This code is useful for real life situations such as a busy campus registrar having several service counters. Students take a numbered ticket and the staff calls the next person. This program fulfills the efficiency in queuing the ticket holder fairly and records completed service.


____________________________________________

**Contents**
1. Setup
2. How to Use
3. Import
4. Data Structure of the counters, functions, tickets, etc.
5. Class for the Waiting Ticket Iterator
6. Functions used and created for implementation of the ticket system
7. Menu of the Queue Manager 
8. Inputs and Conditions of each statements

_(In the end of the file is where the Terminal Transcript is found)_

____________________________________________

**1. SETUP**

1. Install an IDE if you do not have one installed. Software preferably used would be Virtual Studio Code for beginners or PyCharm which is built for Python. PyCharm also comes packed with smart refactoring, database tools, and virtual environments ready to go.
2. If you are using VS Code as your IDE, kindly install the recent Python version in the Extension
3. Open a terminal in the folder containing the program. 
4. Run the program

____________________________________________
**2. HOW TO USE**

(a) Issue a Ticket
 - Firstly, enter the purpose of your request. Kindly choose between **Enrollment**, **Records**, or **Payment**.
 - After doing so, kindly select whether your service type is **regular** or **priority**. If you do not enter anything here, the **default service** will become **regular**.
 - After entering, the ticket will successfully be issued whereas the system will give you a unique ticket number.
 - The ticket number given increments in order according to the number of person that requests a service.
   
   **IF THE USER WANTS TO CREATE MORE TICKETS**
   - The system will continue to ask you whether you want to create another ticket or not.
   - If the user declines, then the condition will break and return to the main menu.
   - If the user says Yes or yes, the system will ask the user to fulfill the questions asked from before when issuing a ticket.
   - However, if the user enters random characters or digits instead of answering correctly, the system will ask again to enter yes or no.
  
  **TAKE NOTE, ALL RECENTLY ISSUED TICKETS' STATUS WILL BE ISSUED AS WAITING**


(b) Call the Next Ticket
 - In this choice, the system checks whether all counters are busy or not.
 - If there are vacant counters or both are free, the condition will call the next ticket, prioritizing 2 priority tickets before the regular ticket holders.
 - When tickets are called, their ticket **"Status"** becomes **"In Service"** and their ticket dictionary is presented.
 - Calling tickets are under a priority streak whereas the system will call a regular ticket after two consecutive priority calls when one is in waiting and one is completed. After that, it loops back to calling in two priority ticket holders again and so on. If there is no priority ticket during the loop, it will call the next ticket holder which can be regarded as regular ticket holders. 


(c) Complete a Service
 - When this selection is picked by the user, they may complete any ticket that is being served or was called to the counter. (ANY TICKET WITH THE STATUS "In Service")
 - If tickets called out were either cancelled, non-existing, completed already, or in waiting, the ticket will not be completed and is disregarded by the system, calling it out that no ticket was found in the ones currently being served.


(d) Cancel a Waiting Ticket
 - This choice cancels a ticket when the ticket number is entered.
 - If an invalid or unknown ticket that is not in the waiting list will not be cancelled and be deemed not found.


(e) Show Waiting Tickets
 - In this choice, the Waiting Ticket Iterator was implemented through the WaitingTicketIterator function.
 - This determines the tickets currently waiting to be served.
 - This choice reveals the ticket number, its purpose and its status.
 - If the ticket is called or cancelled, the ticket won't appear among the waiting tickets anymore.
 

(f) Show counter status and completed history
 - In this choice, when you enter 6 in the menu, the system will check and reveal whether there are vacant counters that are ready to call in a next ticket, or all counters are busy
 - When there is a counter currently serving a ticket, the counter status will reveal what ticket number they are serving.
 - If the manager or counter completes a ticket, the completed tickets will be revealed here when desired.


(g) Show a Summary Report
 - Choice number 7 will reveal a complete summary report of the current tickets in waiting, in service, those who were served or completed, tickets that were cancelled, and how many counters are free.
 - This is the overall data without giving out extensive data for each ticket, simply put, this reveals the count for how many has been in that category.


(h) Exit
 - Lastly, entering 8 in the menu will exit the overall program through the import sys module, using the ```sys.exit``` statement.
 - With this statement, the program will tell the user that they will be exiting the program and greets them with Goodbye.
____________________________________________


**2. IMPORT**

 The ```import sys``` imports the built-in sys module whereas in this program, the sys module was executed for exiting the program by entering choice "8". In the code, exiting the program was done within a function that implements this module by calling out the ```leave_queue(menu)``` function choice "8" that exits the program using ```sys.exit``` which can also be customized by printing a text before exiting.

____________________________________________

**3. DATA STRUCTURE OF THE COUNTERS, FUNCTIONS, TICKETS, ETC.**

 This section explain the data structure outside the functions which resides at the beginning after the import statement. 

These consists of specific variables, default statements, range for the counter, and lists which can add ticket dictionaries when the program is executed.

```
#Next_number variable outside the issue_ticket function to define and vaildate, allowing function to update the variable.
next_number = 1

#for next_ticket to 
waiting_tickets = []
priority_streak = 0
current_ticket = None

#Two Counters for the report and serving tickets
counters = {counter_number: None for counter_number in range(1, 3)}

#Completed Ticket
completed_tickets = []

#Cancelled tickets
cancelled_tickets = []
```
____________________________________________
 









**FULL TERMINAL TRANSCRIPT IN WHICH FULFILLS THE SCENARIO DEMONSTRATION**
```
PS C:\Users\Name of User\Documents\Name of Folder> & "C:\Users\Name of User\AppData\Local\Programs\Python\Python313\python.exe" "c:/Users/Name of User/Documents/Name of Folder/ISYS411- MIDTERM Lab Activity 3"

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 1

Enter the purpose of your service request (Enrollment, Records, or Payment): Enrollment

Enter the type of service (regular or priority): priority

Ticket issued successfully! Your ticket number is: T-0001

Would you want to create another ticket? yes

Enter the purpose of your service request (Enrollment, Records, or Payment): Records

Enter the type of service (regular or priority): regular

Ticket issued successfully! Your ticket number is: T-0002

Would you want to create another ticket? yes

Enter the purpose of your service request (Enrollment, Records, or Payment): Payment

Enter the type of service (regular or priority): priority

Ticket issued successfully! Your ticket number is: T-0003

Would you want to create another ticket? yes

Enter the purpose of your service request (Enrollment, Records, or Payment): Enrollment

Enter the type of service (regular or priority): regular

Ticket issued successfully! Your ticket number is: T-0004

Would you want to create another ticket? yes

Enter the purpose of your service request (Enrollment, Records, or Payment): Records

Enter the type of service (regular or priority): priority

Ticket issued successfully! Your ticket number is: T-0005

Would you want to create another ticket? yes

Enter the purpose of your service request (Enrollment, Records, or Payment): Payment

Enter the type of service (regular or priority): priority

Ticket issued successfully! Your ticket number is: T-0006

Would you want to create another ticket? no

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 2

Counter 1 is Serving Ticket Number: T-0001 | | Enrollment | | priority | | Ticket Status: In Service


==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 2

Counter 2 is Serving Ticket Number: T-0003 | | Payment | | priority | | Ticket Status: In Service


==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 2

Both counters are busy.

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 3
{1: {'Number': 'T-0001', 'Purpose': 'Enrollment', 'Service Type': 'priority', 'Status': 'In Service'}, 2: {'Number': 'T-0003', 'Purpose': 'Payment', 'Service Type': 'priority', 'Status': 'In Service'}}

Which ticket to complete: T-0001
Ticket T-0001 Completed.

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 4

Enter the ticket number to cancel: T-0002

Ticket T-0002 cancelled.

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 5
1. T-0004 - Enrollment
2. T-0005 - Records
3. T-0006 - Payment

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 2

Counter 1 is Serving Ticket Number: T-0004 | | Enrollment | | regular | | Ticket Status: In Service


==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 3
{1: {'Number': 'T-0004', 'Purpose': 'Enrollment', 'Service Type': 'regular', 'Status': 'In Service'}, 2: {'Number': 'T-0003', 'Purpose': 'Payment', 'Service Type': 'priority', 'Status': 'In Service'}}

Which ticket to complete: T-0010

Ticket number T-0010 was not found in the data being served.

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: T-0001

Invalid choice. Please enter a number from 1 to 8.



==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 3
{1: {'Number': 'T-0004', 'Purpose': 'Enrollment', 'Service Type': 'regular', 'Status': 'In Service'}, 2: {'Number': 'T-0003', 'Purpose': 'Payment', 'Service Type': 'priority', 'Status': 'In Service'}}

Which ticket to complete: T-0001

Ticket number T-0001 was not found in the data being served.

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 6

Counter 1 is serving ticket number T-0004

Counter 2 is serving ticket number T-0003
Here are the list of Completed Tickets: 
[{'Number': 'T-0001', 'Purpose': 'Enrollment', 'Service Type': 'priority', 'Status': 'Completed'}]

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 7


waiting: 2
in_service: 2
served: 1
cancelled: 1
free_counters: 0

==============================
 CAMPUS SERVICE QUEUE MANAGER
==============================

1 Issue a ticket
2 Call the next ticket
3 Complete a service
4 Cancel a waiting ticket
5 Show waiting tickets
6 Show counter status and completed history
7 Show a summary report
8 Exit

Enter your choice: 8

Exiting the Campus Service Queue Manager. Goodbye!

PS C:\Users\Name of User\Documents\Name of Folder>
```
