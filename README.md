# Campus-Service-Queue-Manager-School-Activity-
Language used is python


**Campus Service Queue Manager**


This is a Campus Service Queue Manager program that manages tickets issued, called, cancelled, and completed.

This code is useful for real life situations such as a busy campus registrar having several service counters. Students take a numbered ticket and the staff calls the next person. This program fulfills the efficiency in queuing the ticket holder fairly and records completed service.


____________________________________________

**Contents**
1. Import
2. Data Structure of the counters, functions, tickets, etc.
3. Class for the Waiting Ticket Iterator
4. Functions used and created for implementation of the ticket system
5. Menu of the Queue Manager 
6. Inputs and Conditions of each statements

____________________________________________


**1. IMPORT**

 The ```import sys``` imports the built-in sys module whereas in this program, the sys module was executed for exiting the program by entering choice "8". In the code, exiting the program was done within a function that implements this module by calling out the ```leave_queue(menu)``` function choice "8" that exits the program using ```sys.exit``` which can also be customized by printing a text before exiting.

____________________________________________

**2. DATA STRUCTURE OF THE COUNTERS, FUNCTIONS, TICKETS, ETC.**

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
