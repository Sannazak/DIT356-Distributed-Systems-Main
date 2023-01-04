# Documentation (Last update: 2022-12-12)

# About the Project

## Name
Dens Cura: Distributed dental clinic booking system

## Description
It is undoubtable that dental health is crucial to one's well-being. For its importance, a modern society is expected to support a decent dental care of the people. This support includes a right to get a dental care in a timely manner without travelling too far fron one's residence. These features are facilitated by the online booking system that support easy and effienct reservation of timeslot in dental clinics. Despite the importance, not every society is equipped with the dental clinic booking system that satisfies all residents' needs; one example is the Västra Götaland county in Sweden.

As of autumn 2022, the only web-service for online dental clinic booking is Folktandvården, the Public Dental Service in Västra Götaland country. Although this service provides the users with multiple functionalities, there are several limitations that can be improves for higher customer satisfaction. One of the major issues is that the current Folktandvården system only covers search for public dental clinics and excludes numerous private clinics. Moreover, in the current system the user should manually filter the geographical search area as the system is not using the current location of the user connected to a map.

The project aims to develop a brand-new distributed system for dental clinic booking which overcomes the identified challenges in the current setting; that is, to provide the user with access to all dental clinics in the city of Gothenburg. The project team consists of eight student developers. The initial and foundational requirements were provided by the university of Gothenburg to ensure the quality of the software. Additionally, the project team has been added creativity in the project to maximize the user satisfaction.

## Development Team

| Team member | Main Role | Tasks |
| ------ | ------ | ------ |
| Mijin Kim | Product Owner, Developer | Product backlog maintanance, contact point with clients, software development |
| Erik Harring | Scrum Master, Developer | Support agile practice in the team, software development |
| Christopher Andersson | Developer | Software Development |
| Jonathan Bergdahl | Developer | Software Development |
| Sanna Evertsson | Developer | Git Responsible, Software Development |
| William Hilmersson | Developer | Software Development |
| Patricia Antunes Marklund | Developer | Kanban Board Responsible, Software Development |
| Anna Törngren | Developer | Software Development |

## Project repositories
To implement the distributed nature of *Dens Cura*, the system has been developed in the following five repositories in GitLab:
- [Booking Backend](https://git.chalmers.se/courses/dit355/dit356-2022/t-10/booking-backend)
- [Clinic backend](https://git.chalmers.se/courses/dit355/dit356-2022/t-10/booking)
- [Frontend](https://git.chalmers.se/courses/dit355/dit356-2022/t-10/frontend)
- [Broker](https://git.chalmers.se/courses/dit355/dit356-2022/t-10/broker)
- [Filter](https://git.chalmers.se/courses/dit355/dit356-2022/t-10/filter)

## Software Requirement Specification (SRS)
1. General Requirements
1.1. The system shall have 4 distributed and independent components 
1.2. The application shall not break when a faulty input is received. 

2. Frontend:
2.1. The system shall allow users to book appointments with dental clinics.
2.2. The system shall contain a map-view over Gothenburg that can be navigated. 
2.3. The system shall have a calendar displaying the times for booking.
2.4. The system shall display only the times that are available for booking.
2.5. The system shall display a message in case a user clicks on a time that is already booked.
2.6. The system shall display a confirmation message when a booking is confirmed.
2.7. The system shall have an option to find an existing booking.
2.8. The system shall allow the user to cancel an existing booking.

3. Booking Backend:
3. 1. The system shall make changes to booking availability as simultaneous bookings happen 
3. 2. The system shall reserve the time chosen in the calendar by the user for 5 minutes. 
3. 3. The system shall cancel the reservation if the booking is not confirmed within 5 minutes. 
3. 4. The booking shall contain email, SSN, first and last name of the user. 

4. Clinic Backend:
4. 1. The booking slots shall have 30 minutes of duration 
4. 2. The booking shall require one dentist 
4. 3. The system shall allocate a lunch break of 1 hour per day to the dentist 
4. 4. The system shall allocate a Fika break of 30 minutes per day 

5. Filter:
5. 1. The system shall veriry if booking requests are in JSON format
5. 2. The system shall guarantee no overload by using a load balancer 

6. Broker:
6. 1. The system shall have middleware based on the MQTT protocol 
6. 2. Booking requests and responses shall be handled through MQTT 
6. 3. Stopped components must unsubscribe from the MQTT broker 
6. 4. The system shall guarantee a Qo2 level for 2 for all MQTT messages. 

## Software Architecture Document (SAD)
### Component diagram
![Component diagram with a high-level view](./component_diagram.png)


# Project Management Report (PMR)

## Project management practices used
The project team has actively adopted the principles of Scrum in combination with Kanban.
- The important Scrum decisions that the development team has been made are:
  - Election of a Product Owner (PO) and a Scrum Master (SM)
  - The project consists of multiple sprints
  - Diverse Scrum artifacts; e.g. product backlog, sprint backlog
  - Diverse sprint rituals; e.g. sprint planning, sprint review and sprint retrospective
- [A kanban board in Trello](https://trello.com/b/mpXIOkcb/dit-356-2022-team-10)  has been used to facilitate the team's work with visual presentation of tasks


## Important project management decisions (regarding schedule and scope)

*Iteration week 1 (Sprint 1)* 
- The team created a team contract to reach agreement on the common aim, vacation days as well as basic guidelines for the team work.
- The team has been agreed on communication channels and the way of communication.
- The team decided to actively adopt the Scrum practices with certian variations.
- Roles of the team members have been decided after analyzing each member's strength.
  - The Project Owner and Scrum Master of the team has been decided. This will not change during the project cycle due to short time period.
  - All members got a position as a software developer.
  - Additionally, Git responsible and Trello responsible have been selected.
- Based on specific milestone dates provided by the project sponsor, the timeframe of four sprints has been decided.
- Considering the sprint schedule, plans and dates for regular Scrum events were decided.
  - Every Tuesday and Thursday, the team will conduct a 15-minutes daily Scrum meeting.
  - A sprint meeting shall be held one day before the milestone of each sprint.
  - There should be two sprint review sessions per sprint:
    - The first sprint review shall be conducted a day before the milestone date at a team level (including Product Owner and Scrum Master).
    - The second sprint review shall be conducted on the milestone date with the Scrum team and the teaching assistence of the course.
  - Sprint planning shall be made shortly after the latter sprint review. In a sprint meeting, product backlog shall be refined and a new sprint backlog shall be created.
  
*Iteration week 2 (Sprint 1)*
- Continued from the previous iteration, the team have agreed to spend iteration 2 for the project planning. Furthermore, the team made a rough plan of the focus of the software development during the project cycle as below:
  - *Sprint 1 (current sprint)*: Finalizing project planning
  - *Sprint 2*: Back-end development
  - *Sprint 3*: Front-end development
  - *Sprint 4*: Integration of the back-end and front-end & resolving any issue in development
- Based one the grading criteria of the course, the team agreed on minimum viable products to deliver and also created a list of optional features which could be implemented to add extra value to the product; i.e. login functionality and the level of GUI aesthetics.
- 

*Iteration week 3 (Sprint 2)*
- The original sprint-2 backlog has been updated during the sprint as the backlog items had to be broken down further to faciliate the members' work.

*Iteration week 4 (Sprint 2)*
- The sprint review and sprint retrospective which originally scheduled on 30th November with the TA have been changed to 29th November considering the deadline of retrospective-2 submission being on 30th of November.
- The team members have worked efficiently during the iteration and have finished many items in the sprint-2 backlog earlier than the estimation. Therefore, the team has started working on several front-end related features in the product backlog, which were planned to be done in the upcoming sprint.
  
*Iteration week 5 (Sprint 3)*
- In the original project scope, the team has decided to implement a login functionality by verifying user with a login token. However, the team encountered several issues with login functionality which hinders the progress of all related tasks. The team has decided to commit a day to fix the issue(7th of December). If the issue cannot be solved, the login functionality shall be excluded out of the project scope.

*Iteration week 6 (Sprint 3)*<br />
  There was a significant change in the project scope and the software architecture.
  - Change in the project scope: The user-related functionalities, which the team has been put a lot of effort and time, started to cause issues in the project and take a lot more time than the team has estimated. As they are not mandatory requirements of the course, the team has decided to move them out of the scope in order to commit all the resources into the more important tasks.
  - Change in the software architecture: Before the scope change, the team had four separate components (repositories) including User Backend repository which contains all user-related functionalities such as login, registration and user sessions. As the team decided to remove the user-related functionalities out of the scope, the User Backend is no longer in use. This leads the team to have only three independent components in the system, which does not satisfy the grading criteria; i.e. at least four independent components are required in the system. Thus, the team had to split Clinic Backend repository into Clinic Backend and Booking Backend repository.
  - The team has completed all necessary features about booking functionlities by the end of Sprint 3. All remaining features and documentation will be conducted in Sprint 4 according to the original schedule.


**keep for the potential usage (everything below this line)**

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser.

## Authors and acknowledgment
Show your appreciation to those who have contributed to the project.

## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers.
