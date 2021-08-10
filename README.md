# Consumer Mart 



## Enterprise E-Commerce Application 
Consumer Mart is a fully-fledged enterprise E-Commerce conception that is still in development.  


## Languages & Framework
![](https://img.shields.io/badge/FrontEnd-Angular-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Framework-.NET-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Database-SQLITE-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/BackEnd-C-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)

## Status Update

Up until the most recent commit, our Entities file, StoreContext & Migrations, and API Controllers were all in the same project folder.  Since refactoring, I have decided to use dependecy injection and separate the API Controllers from the rest of the code that it depends on. 

Stepping back for a moment, the API Controller depends on the StoreContext/Migrations and the StoreContext/Migrations depends on the Entities.  Because of this, Entities has been placed in it's own separate folder, "Core", and StoreContext/Migrations wer placed in it's own separate folder, "Infrastructure."  Doing this required a couple of changes to current namespaces and bringing in the other files as dependencies, but will make debugging and maintaining code simpler and less prone to errors. Now when API requests come in, they go to the API Controller which gets it's dependency injected from the Infrastructure Data.  Based on what the request is, it will either get or set products from the DB based on the DB object given by the Core Entities file.  It is in the Entities file that it knows the specifics about each class, which in our case only has one Product Class and 2 attributes - ID (PK) and Name. 

## Features

- Asynchronous HTTP methods used to delegate tasks while allowing other tasks to execute concurrently
- Using Entity Framework as a way to model our database objects and query ;  We are using SQLITE for our development DB but Entity allows us to migrate to any relational DB that we desire when deploying or in production without losing our database objects provided by the ORM
- Currently has 5 records in the DB that we can query using two methods provided in our API controller - GetProduct or GetProducts;  primary key is used as a parameter for the GetProduct Method in order to retrieve the product based on the primary key unique identifier.  

## Future Updates

- Real products added
- API Error Handling
- More API Features (sorting, searching, filters)
- Front-End Development (Javascript - Angular Framework)
- Payment Integration (Stripe)
- Expand our API - Add Orders, Checkout, Validation, Identity
- Analyze/Improve Performance 


