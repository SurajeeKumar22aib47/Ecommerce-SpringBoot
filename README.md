# REST API for an E-Commerce Application

* I have developed this REST API for an e-commerce application. This API performs all the fundamental CRUD operations of any e-commerce platform with user validation at every step.
* This project was built as part of my backend development practice, covering authentication, authorization, and full feature implementation for an e-commerce workflow.

---

## E-R Diagram for the application

![E-R Diagram](./ER%20Diagram/E-Commerce%20API%20ER%20Diagram.jpeg?raw=true)

---

## 🛠 Tech Stack

* Java
* Spring Framework
* Spring Boot
* Spring Data JPA
* Hibernate
* MySQL

---

## 📦 Modules

* Login & Logout Module
* Seller Module
* Customer Module
* Product Module
* Cart Module
* Order Module

---

## ✨ Features

* Customer and Seller authentication & validation with session tokens (validity of 1 hour for security)
* **Seller Features**:
  * Administrator control over the application
  * Only registered sellers with a valid session token can add/update/delete products from the main database
  * Can access customer details and orders
* **Customer Features**:
  * Register, login, and manage profile
  * Browse products, add to cart, and place orders
  * Access own orders, cart, and account management features

---

## 👨‍💻 Author

**Surajee Kumar**  
[LinkedIn](https://www.linkedin.com/in/surajee-kumar-853909256) | [Email](mailto:interflow.ai@gmail.com)

---

## ⚙ Installation & Run

1. Update database configuration inside `application.properties`:
    ```properties
    server.port=8009

    spring.datasource.url=jdbc:mysql://localhost:3306/ecommercedb
    spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
    spring.datasource.username=root
    spring.datasource.password=root
    ```

2. Run the Spring Boot application from your IDE or using:
    ```bash
    mvn spring-boot:run
    ```

---

## 🌐 API Root Endpoint

`https://localhost:8009/`  
`http://localhost:8009/swagger-ui/index.html#/`

---

## 📌 API Module Endpoints

### Login & Logout Module
* `POST /register/customer` : Register a new customer  
* `POST /login/customer` : Customer login  
* `POST /logout/customer` : Customer logout  
* `POST /register/seller` : Register a new seller  
* `POST /login/seller` : Seller login  
* `POST /logout/seller` : Seller logout  

---

### Customer Module
* `GET /customer/current` : Get logged-in customer details  
* `GET /customer/orders` : Get logged-in customer's order history  
* `GET /customers` : Get all customers  
* `PUT /customer` : Update logged-in customer  
* `PUT /customer/update/password` : Update password  
* `PUT /customer/update/card` : Update credit card details  
* `PUT /customer/update/address?type=home` : Update home address  
* `PUT /customer/update/credentials` : Update email & mobile  
* `DELETE /customer` : Delete logged-in customer  
* `DELETE /customer/delete/address?type=home` : Delete home address  

---

### Seller Module
* `GET /seller/{sellerid}` : Get seller by ID  
* `GET /seller/current` : Get logged-in seller details  
* `GET /sellers` : Get all sellers  
* `POST /addseller` : Add new seller  
* `PUT /seller` : Update seller details  
* `PUT /seller/update/password` : Update password  
* `PUT /seller/update/mobile` : Update mobile number  
* `DELETE /seller/{sellerid}` : Delete seller by ID  

---

### Product Module
* `GET /product/{id}` : Get product by ID  
* `GET /products` : Get all products  
* `GET /products/{category}` : Get products by category  
* `GET /products/seller/{id}` : Get products by seller ID  
* `POST /products` : Add a new product  
* `PUT /products` : Update a product  
* `PUT /products/{id}` : Update product quantity  
* `DELETE /product/{id}` : Delete product  

---

### Cart Module
* `GET /cart` : View cart items  
* `POST /cart/add` : Add item to cart  
* `DELETE /cart` : Remove item from cart  
* `DELETE /cart/clear` : Clear cart  

---

### Order Module
* `GET /orders/{id}` : Get order by ID  
* `GET /orders` : Get all orders  
* `GET /orders/by/date` : Get orders by date (DD-MM-YYYY)  
* `POST /order/place` : Place an order from cart items  
* `PUT /orders/{id}` : Update pending order  
* `DELETE /orders/{id}` : Cancel order  

---

## 📄 Sample API Response – Customer Login

**POST** `localhost:8009/login/customer`  

**Request Body:**
```json
{
    "mobileId": "9999999999",
    "password": "surajee123456" 
}
    
