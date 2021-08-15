# Consumer Mart 



## Enterprise E-Commerce Application 
Consumer Mart is a fully-fledged enterprise E-Commerce conception that is still in development.  


## Languages & Framework
![](https://img.shields.io/badge/FrontEnd-Angular-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Framework-.NET-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Database-SQLITE-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/BackEnd-C-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)

## Status Update

Up until the most recent commit, the Entities file, StoreContext & Migrations, and API Controllers were all in the same project folder.  Since refactoring, I have used dependecy injection as a way to avoid dependency on the classes, and instead keep the dependecy on the interfaces themselves.  This allows for reusability and decoupling of the code to make maintainability and testing more efficient.  The architecture of the application now follows a Repository/MVC architecture.  I have added initial seed data to provide actual data to the three tables currently avaialable - Product Brands, Product Types, and Products.  Adding an IRepository interface allows us to keep the StoreContext file less cluttered as it grows in size and the store context file is using an interface to abstract methods from the IRepository Interface.  Currently, the ProductRepository and IProductRepository are being initialized with each HTTP request since the service is added at runtime with an 'AddScoped' method.  I used lambda expressions to include eager loading navigation properties as it queries from the database.  This allows us to retrieve relational attributes from other tables and display back in our API.  Prior to this, we were only getting back 'null' under ProductBrands and ProductTypes;  All of the Entities being created all have a unique identifier as the primary key, so a base entity was created so that each of the consecutive entities abstract from the base entity.  This avoides a lot of repetitive coding.  New HttpGet requests (2) were added for the two new entities to include retrieiving the brands and types from the database.  

## Features

- Repository/MVC Architecture
- Added Generic repository for scalability; Once there are more entities with similar HttpGet methods in the controller, they will be able to use the same Generic Repository (with added specifications to include parameters) which will pass in the correct object type and use the evaluator method that we created to convert to an IQueryable in which the list is enumerated back to the end-user.  
- Asynchronous HTTP methods used to delegate tasks while allowing other tasks to execute concurrently
- Using Entity Framework as a way to model our database objects and query ;  We are using SQLITE for our development DB but Entity allows us to migrate to any relational DB that we desire when deploying or in production without losing our database objects provided by the ORM
- DTO to shape and/or flatten data objects in our API;  Implemented AutoMapper package with NuGet with help of a MappingProfile class and ProductURL Resolver for our images URL to display the entire URL;  Enabled static content to be consumed by our API by adding middleware to the Startup Configuration file.
- Swagger API Documentation
- API error handling/exceptions 

## Future Updates

- Current database being initialized with hard-coded products (Seed Data) upon program startup
- API Error Handling
- More API Features (sorting, searching, filters)
- Front-End Development (Javascript - Angular Framework)
- Payment Integration (Stripe)
- Expand our API - Add Orders, Checkout, Validation, Identity
- Analyze/Improve Performance 


