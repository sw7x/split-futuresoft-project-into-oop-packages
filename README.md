## description
what we going to do and .....

two methods 
1. draw overall class diagram for the poroject and divide it into modules
2. draw seperate class diagrams for each module


## Requirments

### project management module
    owner--> Create project profile with Client information
    owner--> Add project Details to project profile
    owner--> Add Scheduled Dates to project profile such as Delivery Date, deadline
    owner--> Categorize Projects as local or foreign.
    owner--> managing project profile.
    manager, pm, assigned Dev --> can view project profile   
    project statuses: Initiated, In Progress, On Hold, Completed, Cancelled.

    #### project timeline
        set,Display Scheduled Milestones for the project
        set,Display Actual Duration of Milestones for the project
        mark complete for Actual Milestones of the project


    #### Project Costing
        manager,owner,A.pm --> Add costing factors and cost.
        manager,owner,A.pm --> Calculate Employee cost (Employee cost  = employee cost rate* time)
        manager,owner,A.pm --> Calculate total Cost.
        manager,owner,A.pm --> Adding incomes to the project cost profile.
        manager,owner,A.pm --> deduct income amount from cost.(Calculating profit)
        list income, costs , filter by (incomes, costs) 

***

### Task Management Module
    assigned PM-->Divide project into sub tasks that consist of maximum three levels.        
    pm-->set Estimate time, Delivery date to the Tasks        
    dev-->Submit task with Spend time and additional comment.(done/cannot done)    
    view task info(including delivery status)
    Add priority levels (High, Medium, Low) and allow sorting/filtering.
    Attach documents, screenshots, or specifications to each task.

### Task Progress Monitoring Module
    project wise => Color-coded Task Status Visualization by progress (e.g., Not Started, In Progress, Done, Blocked).
    show percentages for each progress level
    Project Completion % = (Number of Done tasks/Total number of tasks) * 100%

    project wise => view tasks exceed the deadline/ ontime/before time/near to deadline

    pm,owner,manager,ASSIGEND EMP--> view Project progress in tasks.
    (owner, manager,pm--> calculat and show Project Estimate time.(WHEN ALL TASK EST TIME SET)

    //show  recent tasks that complete
    show  recent tasks that have to complete(near deadline)  
    show  recent tasks that exceed the deadline

    //task => Attach documents, screenshots, or file to each task.

***

### Timesheet management
    pm,emp--> manage time sheets for weekly basis
    manager,owner--> approve all users timesheets  
    manager,owner--> view all users timesheets(monthly,weekly)
    can Mark leave days in timesheet.

***

### User management module	 
    managing General information of the users
    •   Owner can manage manager, Developers and PM’s general information.
    •   Manager can manage Developers and PM’s general information.
    •   Anyone can manage his/her own account general information.

    manager,owner-->Manage Emp. Salary information, Employee hourly rate(monthly salary/22days*8 hours), EPF-ETF details and 
    Education Qualifications
    •   Manager can manage above details of Developers and  PM
    •   Company owner can manage above details of Manager, Developers and  PM’s

    Admin level users can manage other user accounts (CRUD,working/resign manage)
    •   Manager can create, delete and change working status of Developers and PM’s
    •   Company owner can create, delete and change working status of manager, Developers and PM’s.

    developer,PM -  manage skill list.

	//>system shall give Users authenticate
	//>system shall be able given appropriate privileges according to their user role.
        
***

### Designation Management
    owner--> manage designation hierarchy 
    owner-->Manage designation ,sub designation information

    admin level users can manage designations of users
    •   Owner can manage designation of manager, PM’s and Developers.
    •   Manager can manage designation of PM’s and Developers.

***

### Communication module
    Users shall be able pass private messages to other users(Able to upload files with private messages)
    assigned dev, PM, manager and owner => thread to each project. can post and see messages in that thread.
    Task assigned devloper, project assigned Pm, owner and manager =>thread to each Task.can post and see messages in that thread.

    //message                => Attach documents, screenshots, or file to each.
    //project thread message => Attach documents, screenshots, or file to each.
    //task thread message    => Attach documents, screenshots, or file to each.

***

### Reporting module
    PM, manager and owner => view employee(developer/pm) Project wise timing (spend time, schedule time)
    PM, manager and owner => view Designation wise spend time for a project (spend time, schedule time)

    Dashboard page
        show  recent projects that engaged in with deadlines
        show  recent projects that completed
        show  recent projects that delayed with deadlines

        show  recent tasks that complete
        //show  recent tasks that have to complete  
        //show  recent tasks that exceed the deadline  

    Deadline Calendar View
        view of project deadlines in Today, week, Month. 
        view of tasks deadlines in Today, week, Month.  

    Developer monthly efficincy report
        tasks delayed, tasks on time, tasks before time

    yearly calendar - show Planned and actual duration of the projects plotted throughout the year

***

### leave management module
    employees can apply leave
    employees can discard applied leave
    manager can approve/disapprove leave
    show  recent leaves
    show  leaves monthly, given date range

    leave types(medical(15), Casual(10), Annual(10).) and track limits per type.

	leaves filter by month
	Leave Calendar -  Display team availability in calendar view.


	pm,Dev - yearly leaves 30 

***

### Resource Management Module 

    CEO,Manager -->Assign PM for a project.
    When PROJ is assigned to a PM system shall be able to notify it to the assigned PM.
    Before assigning PM to project → check if the PM is already assigned to other projects in the same time frame.

    assigned PM-->Assign Devs for a project.
    When PROJ is assigned to a DEV system shall be able to notify it to the assigned user.
    Before assigning a DEV to a project → check if the DEV is already assigned to another project in the same time frame.

    assigned PM-->Assign Tasks for Dev(project tasks for project assigned Dev)
    Before assigning a task → check if the DEV has a leave request overlapping with delivery date.
    Before assigning a task → check if the Dev is already assigned to other tasks in the same time frame.

    Resource Availability Chart Who is available, busy(task count), or on leave.    PM, Manager

    Developer Workload Report =>  show selected Dev assigned tasks  and their deadlines, estimated times, their statues, already spend time spent.

***

## ER diagram
<img src="./diagrams/erd.png">

## Overall class diagram
<img src="./diagrams/cls.png">


## Process 1 - Overall class diagram diagram split it into modules
- mark each package in overall class diagram
- mention for each module use cases, entity attr, entity behaviours


## Process 2 - Draw seperate class diagrams for each module
- for each module tasks seperate class diagrams
    - module task list
    - module class diagram
- mention for each module use cases, entity attr, entity behaviours


