# 🛒 E-Commerce Backend API

A **Spring Boot–based backend** for an e-commerce platform that supports **user authentication (JWT)**, **product management**, **category management**, **shopping cart**, **orders**, and **addresses**.  
Built with **Spring Boot, Spring Security, JWT, JPA/Hibernate, MySQL**.

---

## 🚀 Features

- **Authentication & Authorization**
  - User registration & login with JWT authentication
  - Role-based access (`USER`, `SELLER`, `ADMIN`)
  - Secure endpoints with Spring Security

- **Products & Categories**
  - CRUD operations for products & categories
  - Upload/update product images
  - Search products by keyword or category
  - Pagination & sorting support

- **Shopping Cart**
  - Add/remove products from cart
  - Update product quantity
  - Fetch user-specific cart

- **Orders**
  - Place orders with payment details
  - User-specific order tracking

- **Addresses**
  - Manage multiple user addresses
  - CRUD operations for addresses

- **API Documentation**
  - Integrated Swagger UI for easy testing & documentation

---

## 🏗️ Tech Stack

- **Backend Framework**: Spring Boot 3.x  
- **Security**: Spring Security + JWT  
- **Database**: MySQL (JPA/Hibernate for ORM)  
- **Validation**: Jakarta Validation  
- **Build Tool**: Maven  
- **API Documentation**: Swagger / OpenAPI 3  

---

## 📂 Project Structure (Controllers Overview)

- `AuthController` → Login, Signup, Logout, User Info  
- `ProductController` → Manage products (admin) & browse/search (public)  
- `CategoryController` → Manage categories (admin/public)  
- `CartController` → Manage cart operations  
- `OrderController` → Place orders with payment details  
- `AddressController` → Manage user addresses  

---

## ⚙️ Setup Instructions

1️⃣ Clone Repository
```bash
git clone https://github.com/Bhaskar692/ecommerce-backend.git
cd ecommerce-backend
```
2️⃣ Configure Database

Update your `application.properties` (or `application.yml`) with MySQL settings:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```
3️⃣ Build & Run
 - mvn clean install
 - mvn spring-boot:run

4️⃣ Access APIs

Base URL → http://localhost:8080/api

Swagger Docs → http://localhost:8080/swagger-ui/index.html

---

🔑 API Endpoints (Summary)
🔐 Auth APIs

  - POST /api/auth/signup → Register new user

  - POST /api/auth/signin → Login & receive JWT

  - POST /api/auth/signout → Logout user

  - GET /api/auth/user → Get logged-in user details

📦 Product APIs

  - POST /api/admin/categories/{categoryId}/product → Add product (Admin)

  - GET /api/public/products → Get all products (with pagination & sorting)

  - GET /api/public/categories/{categoryId}/products → Products by category

  - GET /api/public/products/keyword/{keyword} → Search products by keyword

  - PUT /api/admin/products/{productId} → Update product (Admin)

  - DELETE /api/admin/products/{productId} → Delete product (Admin)

  - PUT /api/products/{productId}/image → Update product image

🏷 Category APIs

  - POST /api/public/categories → Create category

  - GET /api/public/categories → Get all categories

  - PUT /api/public/categories/{categoryId} → Update category

  - DELETE /api/admin/categories/{categoryId} → Delete category

🛒 Cart APIs

  - POST /api/carts/products/{productId}/quantity/{quantity} → Add product to cart

  - GET /api/carts/users/cart → Get logged-in user’s cart

  - PUT /api/cart/products/{productId}/quantity/{operation} → Increase/decrease quantity

  - DELETE /api/carts/{cartId}/product/{productId} → Remove product from cart

🏠 Address APIs

  - POST /api/addresses → Add new address

  - GET /api/addresses → Get all addresses

  - GET /api/addresses/{addressId} → Get address by ID

  - GET /api/users/addresses → Get logged-in user’s addresses

  - PUT /api/addresses/{addressId} → Update address

  - DELETE /api/addresses/{addressId} → Delete address

📦 Order APIs

  - POST /api/order/users/payments/{paymentMethod} → Place an order

---

📝 Future Improvements

  - Payment gateway integration (Razorpay/Stripe)

  - Order tracking & invoice generation

  - Wishlist & product reviews

  - Caching & performance optimization

---

🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.
