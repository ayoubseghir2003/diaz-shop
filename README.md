#  diAz Shop – Full Stack Food Ordering & Delivery System

##  Overview

**diAz Shop** is a full-stack web application for ordering traditional Algerian food online, managing deliveries, and tracking order status in real time.

The project consists of:
-  A frontend web app for customers to browse menu items, place orders, and track deliveries.
-  A Node.js backend API that handles authentication, order processing, and delivery management.
-  A lightweight file-based database (JSON + TXT) for persistence.

---

##  Features

###  Customer Features
- Browse categorized food menu (soups, traditional dishes, desserts, etc.)
- Add items to cart
- Automatic delivery price calculation based on distance
- Interactive map selection (Leaflet)
- Submit orders online
- Download order receipt as PDF
- Track order status by phone number

###  Delivery Agent Features
- Login using phone + username
- View available and assigned orders
- Assign orders to themselves
- Update delivery status:
  - `ready`
  - `in_transit`
  - `arrived`
  - `delivered`

###  Authentication
- JWT-based authentication
- Role-based access (`client` / `agent`)

###  Notifications
- Email sent to admin when a new order is placed (via Nodemailer)

---


---

## Backend (server.js)

The backend is built with Node.js + Express and provides REST APIs.

### Key Functionalities
- Authentication with JWT  
- Order management  
- Delivery agent assignment  
- Email notifications  
- File-based persistence  

---

##  API Endpoints

###  Auth
POST /login

Body:
```json
{
  "phone": "123456",
  "username": "John",
  "role": "agent"
}
```
### Orders (Customer)
```json
POST /api/submit-order
GET  /api/orders/:phone
```
###  Delivery (Agent Only)
```json
GET  /delivery/orders
POST /delivery/orders/:id/assign
POST /delivery/orders/:id/status
```
## Frontend (index.html)
The frontend is a single-page application using:

- HTML, CSS, JavaScript
- Leaflet (maps)
- jsPDF (PDF generation)
## Installation
### 1. Clone the project
``` bash
git clone https://github.com/your-repo/diaz-shop.git
cd diaz-shop
```
### 2. install dependencies
``` bash
npm install
```
### 3. Create .env file
``` bash
PORT=3000
JWT_SECRET=your_secret_key
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_password
ADMIN_EMAIL=admin@email.com
```
### 4. Run the server
``` bash
node server.js
```
open : http://localhost:3000
## Technologies
### Backend
- Node.js
- Express
- JSON Web Token (JWT)
- Nodemailer
- File System (fs)
### frontend 
- HTML5 / CSS3 / JavaScript
- Leaflet.js
- jsPDF
## Security
- JWT tokens expire after 2 hours
- No password system (phone-based auth)
<img width="1885" height="868" alt="image" src="https://github.com/user-attachments/assets/f85ea2ba-8dcc-49ae-84b9-2d9e5a83d4c3" />
<img width="1915" height="820" alt="image" src="https://github.com/user-attachments/assets/fe7a512b-d4e5-4757-8b3c-324daafe5035" />
<img width="1889" height="868" alt="image" src="https://github.com/user-attachments/assets/85a5a927-f837-4353-a02f-49a224285555" />



