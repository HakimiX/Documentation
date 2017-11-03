# Handover Documentation

## Introduction 

In this documentation we will establish an overview of the Hacker News system and the essentials for the system, and a lead-in to what some of the most fundamental functionality that are present in the system.

## System Overview

The purpose of the system is to enable discussions and opinions for users by letting them create stories, which others may comment on. The users can also up or down vote a story if the user has 500+ karma points. Another important part of the system is that users can use an API that we have build, to post a specific story from their website, and other users will be able to comment on these specific stories. Overall the whole system is like a social network forum similar to Reddit. 

## Objectives and Success Criteria

The Objective & Success Criteria is to develop a clear understanding at a high-level of how functionality is performed in the current system (Hacker News). This also includes an understanding of the various use case scenarios and what functionality is required to complete each use case. “Leverage the information that is already available from HackerNews”.  

* The system must have an uptime of 95% over a period of two months. 
* Even when the system is down, it must be able to retrieve messages continuously.
* The system must be accesable for everyone

## Proposed

Our system will be a clone of the Hacker News website. It will include all of the basic functionalities such as posting stories, commenting on stories, and up/down voting stories. The system will be accesable through a user friendly interface.

## Functional Requirements

* Users can publish a story
* Users can comment a story
* Users can reply a comment
* Users can up-vote/down-vote a story
* Users can read a story
* Users can login
* Guests can read stories 
* Guests can register

## Non-Functional Requirements

### Usability

The usability is the degree to which the interface can be used by specified consumers to achieve objectives with effectiveness, efficiency and satisfaction in a context of use. When it comes to usability, the Hacker News clone will be the same as the current system, and that includes layout, design, buttons, text etc. The system will have a consistent design throughout. The following model shows what we have taken into consideration during the development of the Front-end

![Text](https://github.com/HakimiX/Documentation/blob/master/Models/UsabilityModel.jpg)


### Reliability

Uptime is of foremost importance. Any outage can be seen by users as a frustration, or opportunity to move to another system. We will ensure that the Hacker News system will have an uptime of at least 95%. To prevent loss of data, we will make use of Zero Downtime Deployment. Our application will be able to introduce a new version to production without making the user see that the application went down in the meantime. This is the best possible scenario of deployment since new features can be introduced and bugs can be eliminated without any outage. The following model illustrates Zero Downtime deployment.

![Text](https://github.com/HakimiX/Documentation/blob/master/Models/LBmodel.jpg)


### Performance

The system should be able to work under stress, meaning that there should not occur any problems if the amount of users is increasing rapidly. This can be tested using JMeter, we can do whats called a stress test. Stress test could be done at stress periods, in these stress periods(months) there can special days where the system is extra busy, meaning there is extra load time. We can also compare the current system with the new system, to find out which one of them is performing best, or we can measure what part of the system is performing badly.

### Supportability

The system can be accessed through an API (Application Programming Interface). 
The system will have several types of technical support such as guidelines, FAQ, Email support etc. Other features that facilitate servicability that we could implement include: Documentation, Analyzing, or Event logging/tracing. 

### Implementation

In a software context, implementation is all the post-sale processes involved in operating the software properly in its live environment. The implementation process will be designed with the end user in mind, because the participation of users in the design and implementation of the system, will serve their business objectives and reflect their priorities.

We will start by finding a server to deploy the application. We could possibly negotiate a contract with defined set of guidelines, deadlines and a payment schedule for the entire implementation process. Contract requirements could include system performance criteria, documentation and support in case of problems when the system goes live. 

The key component to any implementation process is testing. We will gradually test the new system until it is ready to fully go live. We will be picking out glitches, shortcomings or problems of the system to further help the implementation process. After the testing phase, we will focus on educating/training users about the new system and how to use it before the system is ready to go live. When the system is about to go live, we will review/revisit the entire implementation process and verify that everything is complete.


### Interface

The system will have three different interfaces:

* __User interfaces__ - The user interface of the software shall be compatible to any browser such as Mozilla, Chrome or Internet Explorer by which user can access to the system.
* __Communication interfaces__ - the system shall use the HTTP protocol for communication over the internet.
* __Application Programming Interface (API)__ - External programs shall be able to publish posts and comments to the system.

![Text](https://github.com/HakimiX/Documentation/blob/master/Models/InterfacesModel.jpg)

## Architecture 

### Subsystems 

The Hacker news system is broken down into three well segmented subsystems with cleanly specified interfaces. The front-end application is implemented using Vue.js JavaScript Framework and is an abstraction, simplifying the underlying component by providing a user-friendly interface. The backend which is an application programming interface that unifies the communication between the application and a database is implemented using PHP 7.0 programming language and Laravel Web Application Framework. The data storage layer consists of a MySQL relational database. 

![Text](https://github.com/HakimiX/Documentation/blob/master/Models/Subsystem.jpg)

The design is separated into different areas of concern, which minimizes the complexity. The user interface, business processing and data access all represent different areas of concern. Within each area, the components focus on that specific area, and does not incorporate code from other areas of concern. For example, the front-end UI processing component does not include code that directly accesses the database, but instead makes use of data access component or business components to retrieve data. 

### Design Principles

While implementing the Hacker news system, we have made use of key design principles, which help us create an architecture that adheres to proven principles, minimizes maintenance requirements and promotes usability and extendibility. The key principles are:
* __Single Responsibility Principle (SRP)__.  Each component is responsible for only a specific feature or functionality. 
* __Principle of Least Knowledge (LOD)__. A component does not know about internal details of other components or objects.
* __Separation of concerns (SOC)__. The application is divided into distinct features with as little overlap in functionality. The focus is on minimizing the interaction points to achieve low coupling and high cohesion. 
* __Don’t Repeat Yourself (DRY)__. Intent is only specified in one place. Specific functionality should be implemented in only one component; the functionality is not duplicated in any other component. 

## Data Flow Process

### Laravel MVC

The Laravel Web Application Framework follows the traditional Model-View-Controller design pattern.
* __Controllers__ handle user requests and retrieve data, by leveraging Models.
* __Models__ interact with the database and retrieve objects’ information. 
* __Views__ render pages. 
* __Routes__ are used to map URLs to designated controller actions 

![Text](https://github.com/HakimiX/Documentation/blob/master/Models/MVCModel.jpg)

1. A request is made, when a user enters a URL associated with the application
2. A Route associated with that URL maps that URL to a Controller action
3. That Controller action leverages the necessary Models to retrieve information from the database, and the passes that data off to a View
4. And that View renders the final page 


## Bug Reports & Issues

The objective of writing a bug report is to enable us to visualize the problem. We should be able to understand the defect from the bug report. Remember to give all the relevant information that we are seeking. The bug report must communicate “How?” and “Where?” and should clearly answer how the test was performed and where the defect occurred. We should be able to easily reproduce the bug and find where the bug is. 

Bug reports will be handled through Githubs issues tab in the project repository : REP HERE 

__Submitting a report:__ 
* Include a Bug ID to make reporting and referring easier. 
* Include a Bug Title about the outcome in the bug. 
* Include Priority based on the severity of the bug. Minimal, Major, Critical etc. 
* Include Description to describe the problem encountered, to help us understand the bug. 
* Include Expected/Actual results, to outline the outcome of the test and what you expected. 
* Limit each submission to one issue 
* Clear and concise steps to reproduce, and attach any necessary information, such as screenshots, logs etc. 


Feel free to provide any feedback in regards to the system. We take all feedbacks with open arms. 

## Deployment

### Environment

* Lemp Stack
	+ * Linux 16.04
	+ * Nginx
	+ * MySQL 5.7
	+ * PHP 7.1

![Text]()

## System Access & Credentials

The back-end can be accessed via http://165.227.136.184/

Credentials will be negotiated later

## Development Team

| ROLE | NAME | EMAIL |
|------|------|-------|
|Dev Ops      |Kevin Turan     |  MertDK@live.dk     |
|Product Owner      |Mustafa Hakimi      |Mustafa.hakimi94@gmail.com       | 
|Lead Developer      |Ismail Cam      |i@bigstep.dk       |
|Architect|Mazlum D. Sert|M@bigstep.dk|
|Tester|Kristijan Krsteski|Kristijan222@live.dk|

















