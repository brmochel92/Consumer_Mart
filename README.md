# Consumer Mart 



## Enterprise E-Commerce Application 
Consumer Mart is a fully-fledged enterprise E-Commerce conception that is still in development.  


## Languages & Framework
![](https://img.shields.io/badge/FrontEnd-Angular-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Framework-.NET-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Database-SQLITE-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/BackEnd-C-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)

## Status Update

Up until the most recent commit, the Entities file, StoreContext & Migrations, and API Controllers were all in the same project folder.  Since refactoring, I have used dependecy injection as a way to avoid dependency on the classes, and instead keep the dependecy on the interfaces themselves.  This allows for reusability and decoupling of the code to make maintainability and testing more efficient.  I have added initial seed data to provide actual data to the three tables currently avaialable - Product Brands, Product Types, and Products.  Adding an IRepository interface allows us to keep the StoreContext file less cluttered as it grows in size and the store context file is using an interface to abstract methods from the IRepository Interface.  I used lambda expressions to include eager loading navigation properties as it queries from the database.  This allows us to retrieve relational attributes from other tables and display back in our API.  

## Features

- Asynchronous HTTP methods used to delegate tasks while allowing other tasks to execute concurrently
- Using Entity Framework as a way to model our database objects and query ;  We are using SQLITE for our development DB but Entity allows us to migrate to any relational DB that we desire when deploying or in production without losing our database objects provided by the ORM
- Currently has 5 records in the DB that we can query using two methods provided in our API controller - GetProduct or GetProducts;  primary key is used as a parameter for the GetProduct Method in order to retrieve the product based on the primary key unique identifier.  Currently, I am testing the API with PostMan until the front-end development progresses. 

## Future Updates

- Real products added
- API Error Handling
- More API Features (sorting, searching, filters)
- Front-End Development (Javascript - Angular Framework)
- Payment Integration (Stripe)
- Expand our API - Add Orders, Checkout, Validation, Identity
- Analyze/Improve Performance 


