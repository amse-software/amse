# amse

## Target
The software is used to organise and manage sports competitions, especially for running and biking events, triathlons, etc. The focus is on the execution of the sports competition. In more detail: Participant data collection, sporting execution (e.g. timing), award ceremony and certificate printing.
The software is available on various platforms and can be operated simultaneously with several user devices. The functions on the different platforms are tailored to these, e.g. on a mobile platform the focus is on the sporting event and not on the printing of certificates. However, the basic functions are available everywhere.
Different users have different permissions.
It is self-hostable.
It is not excluded that the software will additionally support the organisation of sports events in other ways in the future.

### MVP Features
- Collection of participant data
- Processing of participant data
- Structure data collection
- Structure data processing
- Recording of sporting performances
- Results processing
- User and role management
*Note: The printing of certificates can be postponed.*

In the following, some features are described in more detail.

#### Structure data collection
This includes the collection of all data that is required for the sports execution, but is not participant data or sporting performances. This data answers the following questions, among others:
- Which sporting performances do which participants have to achieve?
- How are the sporting performances measured?
- How are the sporting performances combined and compared?
- How are the sporting performances made?
- How are the participants grouped?
- What are the guidelines?
- ...

#### Structure data processing
This term refers to the continued compliance/adherence to structural data (see above).


## Implementation frame
- The application must be a client-server application, as it is intended to be used by several users at the same time.
- The application must be able to provide all core functionalities without an internet connection, as the application must be self-hostable.
- The server application should run on a Raspberry Pi 4 to be well self-hostable.
- The application should value the consistency of the data as it is about the results from sporting competitions.
- All actions by users and the system must be traceable to be able to find any fraud or errors.
- The app must be multi-platform. This requires at least a web app, as this is available on every platform. Native applications are still desirable.
- It is inevitable that a server will be needed. Whether this is available as a standalone application is not decided.

## Technical implementation
- Frontend:
	- Application is developed with Flutter, as this allows development for Android, iOS, Windows, macOS, Linux and the web at the same time. The web app must be the most feature-rich variant. All other platforms can follow, but the web app must set the pace.
- Api: GraphQL
- Backend: 
	- NodeJS-Server with PostGraphile running
	- GraphileWorker
	- PostgreSQL
	This backend stack was chosen because of its simpicity. Postgres is the single source of truth. And PostGraphile run in library mode is great for future expandibility.

### Tech Stack
- Flutter
- GraphileWorker
- PostGraphile
- NodeJS
- PostgresSQL
- GraphileMigrate
