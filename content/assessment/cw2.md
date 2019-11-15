+++
title= "Coursework 2"
weight = 2
+++

Coursework 2 is worth 70% of the marks for the module.

It was handed out in Week 7 and is due for submission by 09:30am on 10th January 2020. Marks and written feedback will be returned via email within four working weeks.

<!-- #### Coursework Briefing

The video below explains the coursework details - please ignore the reference to 2018 in the document shown, this video is from last year, but the general assignment remains the same!

<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=5603c23c-8fd9-4b82-ad67-aacc014f739c&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe> -->

## Assignment

PontyBridge University are back. They’re so impressed with the work you did on their prototype website in the first assignment that they’ve returned to the company with another project and specifically requested you work on it.

The University has bought a new backend for their Library system. This is a simple server application that allows the University to track the books that they have, the library users, and which users have borrowed which books. Unfortunately, they forgot to buy a front-end for the system, so they need you to write one.
The code for the Library server is available [here](cw2-libraryserver.zip). You should download the code and familiarise yourself with it. Full usage instructions are included in the Readme.md file contained in the project folder.

The applications itself provides a simple server with a REST API which has the following functionality:

#### API endpoints:

-   `/users`
-   `/books`
-   `/loans`

Each API endpoint accepts HTTP requests with the verbs GET, POST, PUT and DELETE.

The application also comes with an .sqlite database in which the data for the application is stored, and an ORM mapping between the database objects and JavaScript objects. Further documentation on the API server is available in the Library system source code and through the provided tests.

You are tasked with creating a front-end website that interfaces with this API to provide the library functionality requested by the University. This system will be used by the librarians to manage their library and associated data. Your front end should allow them to:

-   U1 - Add a new User to the Library system with the fields Name, Barcode and Member Type (Staff/Student).
-   U2 - Get a User’s details from the Library system by searching on Name or Barcode
-   U3 - Update a User’s Name or Member Type
-   U4 - Remove a User

-   B1 - Add a new Book to the Library system with the fields Title, ISBN, Authors.
-   B2 - Get a Book’s details by searching on Title or Author
-   B3 - Remove a Book

-   L1 - Loan a Book to a User (if it is not already out on Loan), specifying the Due Date
-   L2 - Get a list of a User’s current Loans
-   L3 - Get the User currently borrowing a Book

API endpoints are implemented in the Server application to allow this functionality, documentation comments on each endpoint and the parameters accepted are included in the server application source code.

You are free to modify the server code as you see fit. You are also free to add additional functionality beyond that requested by the University. Alongside the final source code for your front-end (and the server application if you have modified that) you should submit a short document describing the functionality you have implemented. This does not need to be extensive: one or two sentences on each functional requirement, indicating how and where you have implemented the functionality is fine. You may also include screenshots showing the website functionality.

### Marking Criteria

Design of the front end is not an important issue on this project, though the system is expected to present a usable interface. For this project the functionality of the system is more relevant. The general level of functionality required for each grade boundary is described below.

#### Pass

A frontend is created that fulfils most (>80%) of the functional requirements above.
The back-end server code has not been significantly modified beyond that provided.

#### Merit

A frontend is created that fulfils all of the functional requirements above.
The back-end server code may have been modified to improve existing functionality or provide new functionality.

#### Distinction

A frontend is created that fulfils all of the functional requirements above and adds additional functionality.
The back-end server code will have been modified to improve existing functionality or provide new functionality

## Learning Central

The assignment and associated reference material can be found [on Learning Central, under 'Assessment' in the CMT112 module](https://learningcentral.cf.ac.uk/webapps/blackboard/content/listContentEditable.jsp?content_id=_5004043_1&course_id=_393319_1). Full marking criteria are also listed there.

{{%panel theme="danger" header="Warning"%}}
All submission will be through Learning Central - no submissions will be accepted via email.
{{% /panel %}}

## Questions and Answers

If you have a question about the coursework, please submit it through the [COMSC StackOverflow site](stackoverflow.com/c/comsc)
