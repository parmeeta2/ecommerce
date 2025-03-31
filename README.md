# REST API for an E-Commerce Application
I have developed this REST API for an e-commerce application. This API performs all the fundamental CRUD operations of any e-commerce platform with user validation at every step.


# Tech Stack
1. Java
2. Spring Framework
3. Spring Boot
4. Spring Data JPA
5. Hibernate
6. MySQL
   
# Modules
1. Login, Logout Module
2. Seller Module
3. Customer Module
4. Product Module
5. Cart Module
6. Order Module
# Features
 1. Customer and Seller authentication & validation with session token having validity of 1 hour for security purposes
 2. Seller Features:
   -Administrator Role of the entire application
   -Only registered seller with valid session token can add/update/delete products from main database
   -Seller can access the details of different customers, orders
 3. Customer Features:
   -Registering themselves with application, and logging in to get the valid session token
   -Viewing different products and adding them to cart and placing orders
   -Only logged in user can access his orders, cart and other features.





