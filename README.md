# Consumer Mart 



## Enterprise E-Commerce Application 
Consumer Mart is a fully-fledged enterprise E-Commerce conception that is still in development.  


## Languages & Framework
![](https://img.shields.io/badge/FrontEnd-Angular-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Framework-.NET-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/Database-SQLITE-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)
![](https://img.shields.io/badge/BackEnd-C-informational?style=flat&logo=<LOGO_NAME>&logoColor=white&color=5F7FF6)

## Status Update

Currently, the ProductRepository and IProductRepository are being initialized with each HTTP request since the service is added at runtime with an 'AddScoped' method.  I used lambda expressions to include eager loading navigation properties as it queries from the database.  This allows us to retrieve relational attributes from other tables and display back in our API.  Prior to this, we were only getting back 'null' under ProductBrands and ProductTypes;  All of the Entities being created all have a unique identifier as the primary key, so a base entity was created so that each of the consecutive entities abstract from the base entity.  This avoides a lot of repetitive coding.  New HttpGet requests (2) were added for the two new entities to include retrieiving the brands and types from the database.  

## Features

- Added dependency injection in several places of our application, including in the startup file where I added the controllers, 'addDbContext', and auto mapper which get added to the container at runtime as services that the application are dependent upon
- Repository/MVC Architecture
- Added Generic interface and Specifications interface in order to abstract and specify criteria or include statements from the entities since a lot of them share similar methods
- Task-based Asynchronous Pattern (TAP) used for scalability purposes with our Http Requests and DB queries
- Using Entity Framework as a way to model our database objects and query ;  We are using SQLITE for our development DB but Entity allows us to migrate to any relational DB that we desire when deploying or in production without losing our database objects provided by the ORM
- Added DTO with use of AutoMapper to shape and/or flatten data objects in our API;  Implemented AutoMapper package with NuGet with help of a MappingProfile class and ProductURL Resolver for our images URL to display the entire URL;  Enabled static content to be consumed by our API by adding middleware to the Startup Configuration file.
- Swagger API Documentation
- API error handling/exceptions added as Middleware that executes at runtime

## Future Updates

- Add API Paging, Sorting, Filtering, and Searching
- Front-End Development (Javascript - Angular Framework)
- Payment Integration (Stripe)
- Expand API - Add Orders, Checkout, Validation, Identity
- Analyze/Improve Performance 
- Drop SQLITE and migrate to another relational database 
- Expand database - more products, brands, typesf
- Upgrade existing web assets (logo, images)

## Swagger API Documentation 

![API](https://user-images.githubusercontent.com/62531841/129465619-b666c2c0-2b4e-442d-9460-494e021311c0.png)


