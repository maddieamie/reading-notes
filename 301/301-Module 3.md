## Module 3: Full Stack and Auth0 

### Class 11

[nosql vs sql](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)

1. Fill in the chart below with five differences between SQL and NoSQL databases:

SQL: relational database // table based, schema that is predefined, vertically scalable by increasing hardware,
structured query language for defining and manipulating data. 

NoSQL: non-relational // document based, key-value pairs, graphs, or wide-column, no standard schema (dynamic schema for 
unstructured data), horizontally scalable by increasing servers to reduce load, queries are focused on a collection of documents with syntax that 
varies from database to database 


   1. What kind of data is a good fit for an SQL database?
  a complex query intensive environment with a need for power, and heavy duty transactional type applications 
   
1. Give a real world example.
My SQL database. 
   
1. What kind of data is a good fit a NoSQL database?
  they fit better for a hierarchical data storage with key-value pairs, similar to JSON data. Highly preferred for large data sets. Hbase is an example. 
   
1. Give a real world example.
Mongo DB
   
1. Which type of database is best for hierarchical data storage?
NoSQL
   
1. Which type of database is best for scalability?
SQL

[sql vs nosql](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)(Video)

  1. What does SQL stand for?
structured query language 

  1. What is a relational database?
Works with tables and has a clear schema that we can call and update. 
Joins retrieve related data

  1. What type of structure does a relational database work with?
It can't add more than is defined for the table of data
All records follow a schema
Work with related multiple tables -- set up the relations between the tables


  1. What is a 'schema'?
It defines the type of data for a relational database-- the organization and logic
of your data within the database. 

  1. What is a NoSQL database?
Able to store lots of data in an efficient way. 
You don't have to use the same schema for document type data 


  1. How does it work?
Generally there are no relations, though you could set them up. 
You store infomation in collections.
Have less time taken for relational querying but then you have to update multiple
collections at once. 

  1. What is inside of a MongoDB database?
  1. Which is more flexible - SQL or MongoDB? and why.
MongoDB is more flexible because you can hold multiple types of data. 

  1. What is the disadvantage of a NoSQL database?
They don't support ACID (atomicity, consistency, isolation, durability)

 Bookmark and Review

- [mongoose api](https://mongoosejs.com/docs/api.html#Model)
- [React Router](https://reactrouter.com/web/api/BrowserRouter)


### Class 12

[Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

1. In your own words, describe what each group of status code represents:

   - 100's = informational status codes that tell us what's happening in requests
   - 200's = a request was successfully made, but that doesn't mean it fully processed successfully
   - 300's = redirect codes -- tells the client that what they were looking for isn't where they were looking for it anymore
   - 400's = client error codes --" timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request."
   - 500's = server error codes, usually best for client to retry their request

1. What is a status code 202?
   something was created! Should return a location header with a url
   
1. What is a status code 308?
   Permanent Redirect: This tells the client to use another URL to access the resource and not use the current URL anymore.
   
1. What code would you use if an update didn't return data to a client?
    No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.
   
1. What code would you use if a resource used to exist but no longer does?
   410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.
   
1. What is the 'Forbidden' status code?
   403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

[Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw) - First 20 minutes

1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?
    process.env.VARIABLE  and do require('dotenv').config();
     
1. What is middleware?
Code that runs when the server gets a request but before it gets to your routes.
   
1. What does `app.use(express.json())` do?
It requires us to use express as our middleware software. It allows us to accept json as a body.
   
1. What does the `/:id` mean in a route?
   It is a parameter with a colon, and the id is the specific thing.
   
1. What is the difference between `PUT` and `PATCH`?
    Patch: only updates based on what the user passes to us.
   Put: It updates all the information about the subscriber at once. 
1. How do you make a default value in a schema?
   default: Date.now
1. What does a `500` error status code mean?
   Internal server error: actual server had an error, it doesn't
1. What is the difference between a status `200` and a status `201`? 200: ok, 201: ok, something was created.

### Class 13

[CRUD Basics](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)

   1. Which HTTP method would you use to update a record through an API?
      PUT
      
   1. Which REST methods require an ID parameter?
      PUT & DELETE

[Speed Coding: Building a CRUD API](https://www.youtube.com/watch?v=EzNcBhSv1Wo)

  1. What's the relationship between REST and CRUD?
CRUD seems to be the methods that you use with your server to create and update resources, while Rest is how the client deals with your application that is using CRUD operations, and the general structure of that application. 

  1. If you had to describe the process of creating a RESTful API in 5 steps, what would they be?

- Create your server and make sure it is connected to a database.
- Make your CRUD paths with the specific endpoints.
- Make your functions in your server to handle those endpoints.
- Validate your data and make sure the correct responses, errors, and status codes are going to your client.
- Validate authorization to your database. 

### Class 14

Consider the history: [That Time When Women Stopped Coding](https://www.npr.org/sections/money/2014/10/21/357629765/when-women-stopped-coding)

- What occurred during the same time as the beginning of the decline of women in computer science?
  They started marketing computers towards men and then women were socialized into not thinking they would be good at it. The expectations of this affected Patricia Ordóñez when she was attempting to major in CS, as she didn't grow up with a computer at home.
  
- Why does it matter that males had been playing on computers growing up?
  They had an advantage in how general software worked when they went to college. It's a step up. If you have to learn how to use a computer at the same time as learning how to do a bunch of stuff on the computer, you will be a little behind people who had that step up.
  
Review the data: [Employee breakdown of key technology companies](https://informationisbeautiful.net/visualizations/diversity-in-tech/)
Interesting that the higher the position, the fewer women are there.

Ask the question: [Why diversity matters to your tech company](https://www.usatoday.com/story/tech/columnist/2015/07/21/why-diversity-matters-your-tech-company/30419871/)

- When are diversity efforts most successful?
  When there is a meaningful commitment from company leaders, and those leaders have a full understanding of what that commitment means.
  
- Why do diverse companies perform better?
  Most likely because they are able to envision and meet expectations of a more diverse population. They can see more solutions to problems and solve them accordingly. They may also have a more empathetic base with a more diverse set of people. "When the employees of an organization better represent their users and desired users, they will build more effectively for those groups."

- Give an example of how a diverse company can serve a diverse user base or vise-versa.
  If you consider different ways that different users will utilize your products, then you can anticipate problems more effectively. If your team is homogenous, their collective experience will miss out on other perspectives simply because it didn't occur to them. The right-handed vs left-handed example of youtube developers having their left-handed users upload videos upside down is striking.
  It brings to mind Siri not being able to recognize female voices or accented English in general but picking up a general US American male voice in a crowded space, because the people programming Siri were not diverse. 

### Class 15

- [What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

  1. What is OAuth?
     OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.
     
  1. Give an example of what using OAuth would look like.
  Auth0 allows a user to log into a new website using their login credentials from a previous thing they are already signed into. They may have to approve the new site's ability to access user info, but then they can use that app using other credentials they already have.

  1. How does OAuth work? What are the steps that it takes to authenticate the user?
    1. The first website's user info connects to the second website using Auth0's verified identity from the first one.
    2. Second website using Auth0 creates a request token & secret for a one-time transaction.
    3. The token and secret are given to initate the user's client software from first site.
    4. Client's software presents it to authorization provider.
    5. Client is asked to authenticate and approve the authorization transaction.
    6. The user approves (or their software silently approves) a particular transaction type at the first website.
    7. The user is given an approved access token (notice it’s no longer a request token).
    8. The user gives the approved access token to the first website.
    9. The first website gives the access token to the second website as proof of authentication on behalf of the user.
    10. The second website lets the first website access their site on behalf of the user.
    11. The user sees a successfully completed transaction occurring.


  1. What is OpenID?
     It uses authentication instead of authorization methods-- you need to prove you're human, hurrah. " In 2014, OpenID Connect was released, which reinvented OpenID as an authentication layer for OAuth. In this space, OpenID has found a niche, and the two technologies now complement each other in many implementations."

- [Authorization and Authentication flows](https://auth0.com/docs/flows)

  1. What is the difference between authorization and authentication?
     Authorization allows a machine to log you in using previously allowed services to communicate with a new website.
     Authentication requires you to prove that you are a user and you are who you say you are. 
     
  1. What is Authorization Code Flow?
     ![Authorization Code Flow](https://images.ctfassets.net/cdy7uua7fh8z/2nbNztohyR7uMcZmnUt0VU/2c017d2a2a2cdd80f097554d33ff72dd/auth-sequence-auth-code.png)
     
  1. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
     ![Proof Key Diagram](https://images.ctfassets.net/cdy7uua7fh8z/3pstjSYx3YNSiJQnwKZvm5/33c941faf2e0c434a9ab1f0f3a06e13a/auth-sequence-auth-code-pkce.png)
     
  1. What is Implicit Flow with Form Post?
     ![Implicit Flow](https://images.ctfassets.net/cdy7uua7fh8z/6m0uE4E7Hpzbdhyh9dEuYK/e36c910ff47a7540bf27e23c02822624/auth-sequence-implicit-form-post.png)
     
  1. What is Client Credentials Flow?
     ![Client Credentials](https://images.ctfassets.net/cdy7uua7fh8z/2waLvaQdM5Fl5ZN5xUrF2F/326677a1322f7fadeaffd9a32777824a/2023-09-22_11-06-54.png)
     
  1. What is Device Authorization Flow?
     ![Device Authorization](https://images.ctfassets.net/cdy7uua7fh8z/1A6jpG3W1H6SC9ZK92NyKd/40af53209f90a7c392f621f329fb4424/auth-sequence-device-auth.png)
     
  1. What is Resource Owner Password Flow?
     ![Resource Owner](https://images.ctfassets.net/cdy7uua7fh8z/4EeYNcnVX1RFcTy5z4lP4v/c3e4d22e6f8bf558caf07338a7388097/ROP_Grant.png)

Bookmark and Review

- [Auth0 for single page apps](https://auth0.com/docs/libraries/auth0-react)
