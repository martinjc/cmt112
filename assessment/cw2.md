# Coursework 2

Coursework 2 is worth 70% of the marks for the module.

It has been handed out in Week 7 and will be due in on 24th January 2019. Marks and written feedback will be returned within four working weeks.

## Assignment

<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e2f9c6c0-227a-4232-b5aa-a9a000e1ef4e&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

PontyBridge University are back. They’re so impressed with the work you did on their prototype website in the first assignment that they’ve returned to the company with another project and specifically requested you work on it.

The University has bought a new backend for their Library system. This is a simple server application that allows the University to track the books that they have, the library users, and which users have borrowed which books. Unfortunately, they forgot to buy a front-end for the system, so they need you to write one.

The code for the Library server is available at [git@gitlab.cs.cf.ac.uk:cmt112/cw2-libraryserver.git](https://gitlab.cs.cf.ac.uk/cmt112/cw2-libraryserver). You should download the code and familiarise yourself with it. Full usage instructions are included in the Readme.md file contained in the project repository.

The applications itself provides a simple server with a REST API which has the following functionality:

**API endpoints:**

```
    /users
    /authors
    /books
    /loans
    /search
```

Each API endpoint accepts HTTP requests with the verbs GET, POST, PUT and DELETE.
The application also comes with an .sqlite database in which the data for the application is stored, and an ORM mapping between the database objects and JavaScript objects. Further documentation on the API server is available in the Library system source.

You are tasked with creating a front-end website that interfaces with this API to provide the library functionality requested by the University. This system will be used by the librarians to manage their library and associated data. Your front end should allow them to:

-   U1 - Add a new User to the Library system with the fields Name, Barcode and Member Type (Staff/Student).
-   U2 - Get a User’s details from the Library system by searching on Name or Barcode
-   U3 - Update a User’s Name or Member Type
-   U4 - Remove a User

-   B1 - Add a new Book to the Library system with the fields Title, ISBN, Authors.
-   B2 - Get a Book’s details by searching on Title
-   B3 - Remove a Book

-   L1 - Loan a Book to a User (if it is not already out on Loan), specifying the Due Date
-   L2 - Get a list of a User’s current Loans
-   L3 - Get the User currently borrowing a Book

API endpoints are implemented in the Server application to allow this functionality, documentation comments on each endpoint and the parameters accepted are included in the server application source code.

You are free to modify the server code as you see fit. You are also free to add additional functionality beyond that requested by the University. Alongside the final source code for your front-end (and the server application if you have modified that) you should submit a short document describing the functionality you have implemented. This does not need to be extensive: one or two sentences on each functional requirement, indicating how and where you have implemented the functionality is fine. You may also include screenshots showing the website functionality.

### Quick explanation of the Coursework

<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=0b3f6f9a-150f-423f-9e23-a9a000e5ed6f&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

### In depth look at the Coursework server

<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=6bd69cfa-2fe2-4ed0-9e94-a9bb00f8b204&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

### Questions and Answers about the Coursework

<iframe src="https://cardiff.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=48e37b0b-11d2-46fa-b404-a9bb01042f57&v=1" width="720" height="405" style="padding: 0px; border: 1px solid #464646;" frameborder="0" allowfullscreen allow="autoplay"></iframe>

## Learning Central

The assignment and associated reference material can be found [on Learning Central, under 'Assessment' in the CMT112 module]().

!> All submission will be through Learning Central - no submissions will be accepted via email.
