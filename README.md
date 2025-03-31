# REST API for an E-Commerce Application
We have developed this REST API for an e-commerce application. This API performs all the fundamental CRUD operations of any e-commerce platform with user validation at every step.


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

# Installation & Run
Before running the API server, you should update the database config inside the application.properties file.
Update the port number, username and password as per your local database config.
    server.port=8009

    spring.datasource.url=jdbc:mysql://localhost:3306/ecommercedb
    spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
    spring.datasource.username=root
    spring.datasource.password=root

# API Root Endpoint
https://localhost:8009/

http://localhost:8009/swagger-ui/index.html#/

API Module Endpoints
🔹 Login & Logout Module
POST /register/customer : Register a new customer

POST /login/customer : Logging in customer with valid mobile number & password

POST /logout/customer : Logging out customer based on session token

POST /register/seller : Register a new seller

POST /login/seller : Logging in seller

POST /logout/seller : Logging out seller based on session token

🔹 Customer Module
GET /customer/current : Getting currently logged-in customer

GET /customer/orders : Getting order history of logged-in customer

GET /customers : Getting all customers

PUT /customer : Updates logged-in customer

PUT /customer/update/password : Updates customer password

PUT /customer/update/card : Updates credit card details

PUT /customer/update/address?type=home : Updates customer's home address

PUT /customer/update/credentials : Updates email address and mobile number

DELETE /customer : Deletes logged-in user with valid session token

DELETE /customer/delete/address?type=home : Deletes customer's home address

🔹 Seller Module
GET /seller/{sellerid} : Gets seller with given seller ID

GET /seller/current : Gets seller details for currently logged-in seller

GET /sellers : Gets all sellers

POST /addseller : Adding a new seller

PUT /seller : Updates seller details

PUT /seller/update/password : Updates seller password

PUT /seller/update/mobile : Updates seller mobile number

DELETE /seller/{sellerid} : Deletes seller with given ID

🔹 Product Module
GET /product/{id} : Gets product with given product ID

GET /products : Gets all products

GET /products/{category} : Gets products within a given category

GET /products/seller/{id} : Gets products of given seller ID

POST /products : Adds a new product to the database

PUT /products : Updates product details

PUT /products/{id} : Updates product quantity

DELETE /product/{id} : Deletes product with given ID

🔹 Cart Module
GET /cart : Get all items in the customer cart

POST /cart/add : Add item to cart

DELETE /cart : Remove item from cart

DELETE /cart/clear : Clear entire cart

🔹 Order Module
GET /orders/{id} : Gets order details with given order ID

GET /orders : Gets all orders

GET /orders/by/date : Gets orders placed on given date (DD-MM-YYYY)

POST /order/place : Places a new order based on cart items

PUT /orders/{id} : Updates a pending order

DELETE /orders/{id} : Cancels an order

Sample API Response for Customer Login
Request
🔹 POST localhost:8009/login/customer

Request Body
json
Copy
Edit
{
    "mobileId": "9999999999",
    "password": "shyam123456"
}
Response
json
Copy
Edit
{
    "sessionId": 23,
    "token": "customer_0ad57094",
    "userId": 19,
    "userType": "customer",
    "sessionStartTime": "2022-06-10T10:48:20.0109626",
    "sessionEndTime": "2022-06-10T11:48:20.0109626"
}
This format is structured and easy to read! 🚀 Let me know if you need any more modifications.







You said:
add bullet points and give


ChatGPT said:
Here’s your API documentation with proper bullet points for clarity:

# API Module Endpoints
📌 Login & Logout Module
✅ POST /register/customer – Register a new customer

✅ POST /login/customer – Login customer with valid mobile number & password

✅ POST /logout/customer – Logout customer based on session token

✅ POST /register/seller – Register a new seller

✅ POST /login/seller – Login seller

✅ POST /logout/seller – Logout seller based on session token

📌 Customer Module
✅ GET /customer/current – Retrieve currently logged-in customer

✅ GET /customer/orders – Get order history of logged-in customer

✅ GET /customers – Retrieve all customers

✅ PUT /customer – Update logged-in customer details

✅ PUT /customer/update/password – Update customer password

✅ PUT /customer/update/card – Update credit card details

✅ PUT /customer/update/address?type=home – Update customer's home address

✅ PUT /customer/update/credentials – Update email & mobile number

✅ DELETE /customer – Delete logged-in customer with valid session token

✅ DELETE /customer/delete/address?type=home – Delete customer's home address

📌 Seller Module
✅ GET /seller/{sellerid} – Get seller by ID

✅ GET /seller/current – Get details of currently logged-in seller

✅ GET /sellers – Retrieve all sellers

✅ POST /addseller – Add a new seller

✅ PUT /seller – Update seller details

✅ PUT /seller/update/password – Update seller password

✅ PUT /seller/update/mobile – Update seller mobile number

✅ DELETE /seller/{sellerid} – Delete seller by ID

📌 Product Module
✅ GET /product/{id} – Get product by ID

✅ GET /products – Retrieve all products

✅ GET /products/{category} – Get products by category

✅ GET /products/seller/{id} – Get products by seller ID

✅ POST /products – Add a new product to the database

✅ PUT /products – Update product details

✅ PUT /products/{id} – Update product quantity

✅ DELETE /product/{id} – Delete product by ID

📌 Cart Module
✅ GET /cart – Retrieve all items in the customer cart

✅ POST /cart/add – Add item to cart

✅ DELETE /cart – Remove item from cart

✅ DELETE /cart/clear – Clear the entire cart

📌 Order Module
✅ GET /orders/{id} – Get order details by order ID

✅ GET /orders – Retrieve all orders

✅ GET /orders/by/date – Get orders placed on a specific date (DD-MM-YYYY)

✅ POST /order/place – Place a new order based on cart items

✅ PUT /orders/{id} – Update a pending order

✅ DELETE /orders/{id} – Cancel an order

🔹 Sample API Response for Customer Login
📌 Request
✅ POST localhost:8009/login/customer

Request Body
json
Copy
Edit
{
    "mobileId": "9999999999",
    "password": "shyam123456"
}
📌 Response
json
Copy
Edit
{
    "sessionId": 23,
    "token": "customer_0ad57094",
    "userId": 19,
    "userType": "customer",
    "sessionStartTime": "2022-06-10T10:48:20.0109626",
    "sessionEndTime": "2022-06-10T11:48:20.0109626"
}
