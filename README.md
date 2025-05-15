## Table of Contents

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Objective](#objective)
- [Requirements](#requirements)
- [ER diagram](#er-diagram)
- [Overall class diagram](#overall-class-diagram)  
- [Packages](#packages)
	- [Project management package](#project-management-package)
	- [Task management package](#task-management-package)
	- [Task progress Monitoring package](#task-progress-monitoring-package)
	- [Timesheet management package](#timesheet-management-package)
	- [User management package](#user-management-package)
	- [Designation management package](#designation-management-package)
	- [Communication package](#communication-package)
	- [Reporting package](#reporting-package)
	- [Leave management package](#leave-management-package)
	- [Resource management package](#resource-management-package)
- [Single Class Diagram Approach](#single-class-diagram-approach)
- [Package-Wise Class Diagrams Approach](#package-wise-class-diagrams-approach)


## Introduction
This guide outlines the design and development of a custom project management software system for FutureSoft Pvt 
Ltd.system will be structured into logically organized packages using Object-Oriented Analysis and Design (OOAD) 
principles

***

## Project Overview
This Project Management System is a customized software solution designed to help FutureSoft Pvt Ltd efficiently manage 
its internal projects, teams, and workflows

### Key features of the system
- Project creation and management
- Task assignment and tracking
- Role-based access control
- Progress monitoring and reporting

### Target Users
The system will support four user roles within the company:
- Company Owner (Owner)
- Manager
- Project Manager (PM)
- Developer (Dev)

***

## Objective
Objective of this guide is Design the system using Object-Oriented Analysis and Design (OOAD) principles, and organize it into packages.
for that we consider two possible approaches:

1. Single Class Diagram Approach – Create one comprehensive class diagram for the entire system and divide it into packages.
2. Package-Wise Class Diagrams Approach – Create separate class diagrams for each package

In this guide, we will explore both approaches.

***

## Requirements
> Markdown is a lightweight markup language with plain-text-formatting syntax, created in 2004 by John Gruber with Aaron Swartz.
>
>> Markdown is often used to format readme files, for writing messages in online discussion forums, and to create rich text using a plain text editor.  

**[View requirements page](./docs/req.md)**

***

## ER diagram
ER diagram consist most im,portnat attributes only  

<img src="./diagrams/erd.png">  
"All attributes are not shown in the ER diagram to avoid clutter and maintain clarity. Only key 
attribute were include for better readability.


**[Goto ER diagram page to view all attributes of the entities](./docs/er.md)**

***

## Overall class diagram  

<img src="./diagrams/cls.png">  
Attributes and behaviors are not included in the class diagram, as doing so would make the diagram 
overly complex and difficult to read.

**[Goto class diagram page to view all attributes and behaviours of the classes](./docs/cls.md)**

***

## Packages
To develop the project management system for FutureSoft Pvt Ltd, we first gathered key stakeholders to understand their needs. 
Based on the requirements, we defined core system tasks and organized the functionality into structured modules for clarity and 
maintainability. 

### Project management package 
| Authorized | Description |
| --- | --- |
| Owner | Create project profile with Client information |
| Owner | Add project Details to project profile |
| Owner | Add Scheduled Dates to project profile such as Delivery Date, deadline |
| Owner | Categorize Projects as local or foreign |
| Owner | Managing project profile |
| Owner, Manager, PM, Assigned Dev | View project profile |
| | project statuses: Initiated, In Progress, On Hold, Completed, Cancelled. |
| |
| | **Project timeline** |
| | set,Display Scheduled Milestones for the project |
| | set,Display Actual Duration of Milestones for the project |
| | mark complete for Actual Milestones of the project |
| |
| | **Project costing** |
| Manager, Owner, Assigned PM | Add costing factors and cost |
| Manager, Owner, Assigned PM | Calculate Employee cost (Employee cost  = employee cost rate * time) |
| Manager, Owner, Assigned PM | Calculate total Cost |
| Manager, Owner, Assigned PM | Add incomes to the project cost profile |
| Manager, Owner, Assigned PM | deduct income amount from cost.(Calculating profit) |
| Manager, Owner, Assigned PM | list income, costs , filter by (incomes, costs) |

***

### Task management package
| Authorized | Description |
| --- | --- |
| Assigned PM | Divide project into sub tasks that consist of maximum three levels. |
| PM | set Estimate time, Delivery date to the Tasks |
| Dev | Submit task with Spend time and additional comment.(done/cannot done) |
| | view task info(including delivery status) |
| | Add priority levels (High, Medium, Low) and allow sorting/filtering |
| | Attach documents, screenshots, or specifications to each task |

***

### Task progress monitoring package
| Authorized | Description |
| --- | --- |
| | project wise => Color-coded Task Status Visualization by progress (e.g., Not Started, In Progress, Done, Blocked) |
| | show percentages for each progress level |
| | Project Completion % = (Number of Done tasks/Total number of tasks) * 100% |
| | project wise => view tasks exceed the deadline/ ontime/before time/near to deadline |
| PM, Owner, Manager, Assigned Dev | View Project progress in tasks |
| PM, Owner, Manager | calculat and show Project Estimate time.(WHEN ALL TASK EST TIME SET) |
| |
| | ~~show  recent tasks that complete~~ |
| | show  recent tasks that have to complete(near deadline) |
| | show  recent tasks that exceed the deadline |

~~task => Attach documents, screenshots, or file to each task~~  

***

### Timesheet management package
| Authorized | Description |
| --- | --- |
| PM, Dev | submit time sheets by monthly basis |
| Manager, Owner | approve all users timesheets |
| Manager, Owner | view all users previous timesheets(filter by month) |
| | can Mark leave days in timesheet |

***

### User management package	 
| Authorized | Description |
| --- | --- |
| | managing General information of the users |
| Owner | manage manager, Developers and PM’s general information |
| Manager | manage Developers and PM’s general information |
| | Anyone can manage his/her own account general information |
| |
| | Manage Emp. Salary information, Employee hourly rate(monthly salary/22days*8 hours), EPF-ETF details and Education Qualifications |
| Owner | manage above details of Manager, Developers and  PM’s |
| Manager | manage above details of Developers and PM |
| |
| | Admin level users can manage other user accounts (CRUD,working/resign manage) |
| Owner | create, delete and change working status of manager, Developers and PM’s |
| Manager | create, delete and change working status of Developers and PM’s |
| |
| Dev, PM | Manage their skill list |

~~system shall give Users authenticate~~  
~~system shall be able given appropriate privileges according to their user role~~  

***

### Designation management package 
| Authorized | Description |
| --- | --- |
| Owner | Manage designation hierarchy |
| Owner | Manage designation ,sub designation information |
| |
| | admin level users can manage designations of users |
| Owner | Manage designation of manager, PM’s and Developers |
| Manager | Manage designation of PM’s and Developers |

***

### Communication package
| Authorized | Description |
| --- | --- |
| | Users shall be able pass private messages to other users(Able to upload files with private messages) |
| Project assigned dev, PM, Manager, Owner | thread to each project. can post and see messages in that thread |
| Task assigned dev, Project assigned PM, Manager, Owner| thread to each Task.can post and see messages in that thread |

~~message                => Attach documents, screenshots, or file to each~~  
~~project thread message => Attach documents, screenshots, or file to each~~  
~~task thread message    => Attach documents, screenshots, or file to each~~  

***

### Reporting package
| Authorized | Description |
| --- | --- |
| PM, Manager, Owner | view employee(developer/pm) Project wise timing (spend time, schedule time) |
| PM, Manager, Owner | view Designation wise spend time for a project (spend time, schedule time) |
| |
| | Developer monthly efficincy report - tasks delayed, tasks on time, tasks before time |
| | Yearly calendar - show Planned and actual duration of the projects plotted throughout the year |
| |
| | **Dashboard page** |
| | show  recent projects that engaged in with deadlines|
| | show  recent projects that completed|
| | show  recent projects that delayed with deadlines |
| | show  recent tasks that complete |
| | ~~show  recent tasks that have to complete~~ |
| | ~~show  recent tasks that exceed the deadline~~ |
| |
| | **Deadline Calendar View** |
| | view of project deadlines in Today, week, Month |
| | view of tasks deadlines in Today, week, Month |

***

### Leave management package
| Authorized | Description |
| --- | --- |
| | PM,Dev can apply leave |
| | PM,Dev can discard applied leave |
| | Manager can approve/disapprove leave |
| | Show  recent leaves |
| | Show  leaves monthly, given date range |
| | Leave types [medical(15), Casual(10), Annual(10) per year] and track limits per type |
| | Leaves can filter in data ranges for specific DEV/PM |
| | Leaves filter by month |
| | Leave Calendar -  Display team availability in calendar view |

***

### Resource management package 
| Authorized | Description |
| --- | --- |
| Owner, Manager| Assign PM for a project |
| | When PROJ is assigned to a PM system shall be able to notify it to the assigned PM |
| | Before assigning PM to project → check if the PM is already assigned to other projects in the same time frame |
| |
| Project assigned PM | Assign Devs for a project |
| | When PROJ is assigned to a DEV system shall be able to notify it to the assigned user |
| | Before assigning a DEV to a project → check if the DEV is already assigned to another project in the same time frame |
| |
| Project assigned PM | Assign Tasks for Dev(project tasks for project assigned Dev) |
| | Before assigning a task → check if the DEV has a leave request overlapping with delivery date |
| | Before assigning a task → check if the Dev is already assigned to other tasks in the same time frame |
| |
| PM, Manager | Resource Availability Chart Who is available, busy(task count), or on leave |
| PM, Manager | Developer Workload Report =>  show selected Dev assigned tasks  and their deadlines, estimated times, their statues, already spend time spent |

***

## Single Class Diagram Approach 
Overall class diagram diagram split it into packages
- mark each package in overall class diagram
- mention for each package use cases, entity attr, entity behaviours

***

## Package-Wise Class Diagrams Approach
Draw seperate class diagrams for each package
- for each package tasks seperate class diagrams
    - package task list
    - package class diagram
- mention for each package use cases, entity attr, entity behaviours

***



----req page 

--- check packages taks, use roles

------er detailed page

-----class diagram detaild - attr, methods 

----- describe Process 1
----- describe Process 2