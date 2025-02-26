Doom Library
Library Management System
Project Overview
Doom Library is a web application for managing a book library, allowing users to register, log in, and manage their loans. Admin users can add, update, and delete books, as well as manage users and loans.

Features
Books Management

Add a new book (admin only).
View the list of all books.
Update book details (admin only).
Delete a book (admin only).
Customers Management

Add a new customer.
View the list of all customers (admin only).
Update customer details (admin only).
Delete a customer (admin only).
Loans Management

Add a new loan.
View the list of all loans (admin only).
Return a book.
Technologies Used
Backend:

Flask
Flask-SQLAlchemy
Flask-CORS
Flask-Bcrypt
Flask-JWT-Extended
Frontend:

HTML
CSS
JavaScript
Axios
Setup Instructions
Prerequisites
Python 3.x
Virtualenv (recommended)
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/oferpop/doom_library_project.git
cd doom-library
Create a virtual environment and activate it:

bash
Copy code
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
Install the dependencies:

bash
Copy code
pip install -r requirements.txt
Set up the database:

python
Copy code
from app import db, create_app
app = create_app()
with app.app_context():
    db.create_all()
Run the application:

bash
Copy code
python app.py
API Endpoints
Authentication
POST /register: Register a new user.
POST /login: Log in a user.
User Management
GET /customers: Get a list of all users (admin only).
GET /customers/<id>: Get details of a specific user.
PUT /customers/<id>: Update user details (admin only).
DELETE /customers/<id>: Delete a user (admin only).
Book Management
GET /books: Get a list of all books.
GET /books/<id>: Get details of a specific book.
POST /add_book: Add a new book (admin only).
PUT /books/<id>: Update a book (admin only).
DELETE /books/<id>: Delete a book (admin only).
Loan Management
GET /loans: Get a list of all loans (admin only).
GET /loans/<email>: Get loans by user email.
POST /add_loan: Add a new loan (authenticated users).
PUT /loans/<book_id>/return: Return a loaned book (authenticated users).
Database Models
Customer
id: Integer, Primary Key
name: String, Not Null
city: String, Not Null
age: Integer, Not Null
mail: String, Unique
password: String, Not Null
gender: String, Not Null
role: String, Not Null, Default: 'user'
Book
id: Integer, Primary Key
name: String, Not Null
author: String, Not Null
year_published: Integer, Not Null
type: Integer, Not Null
img: String
Loan
id: Integer, Primary Key
cust_id: Integer, Foreign Key (Customer.id)
book_id: Integer, Foreign Key (Book.id)
loan_date: DateTime, Not Null
return_date: DateTime, Not Null
License
This project is licensed under the MIT License.

Contributing
Contributions are welcome! Please fork this repository and submit a pull request for review.

Credits
Created by Ofer Koren
Admin Details
Name: oferpop
Email: oferpop@gmail.com
Password: ok1505
Note
When a customer is deleted, they become inactive.

##CLOUD LINKS 
FRONTEND:
http://doomlibrary.netlify.app/

backend
https://doom-lib-bac.onrender.com/

LOCAL GIT (backend and frontend)

https://github.com/oferpop/doom_library_project