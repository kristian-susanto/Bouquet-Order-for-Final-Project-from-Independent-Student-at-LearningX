# Bouquet Ordering Web Application (Flask & MongoDB)

## Description
This project is a web-based bouquet ordering application built using **Flask** and **MongoDB**.
The application supports **user and admin roles**, bouquet management, ordering, payment proof uploads, testimonials, FAQs, and contact messages.
Authentication is handled using **JWT (JSON Web Token)**, and the application supports image uploads for bouquet images, profile pictures, and payment proofs.

The system is suitable for small to medium bouquet shops that want to manage online orders efficiently.

## Features
### User Features
- User registration and login (JWT-based authentication)
- User profile management (including profile picture upload)
- Browse bouquet collections
- Bouquet ordering and payment submission
- Order history tracking
- Submit testimonials after order completion
- Contact admin via “Hubungi Kami”
### Admin Features
- Admin registration and login
- Dashboard with statistics (users, bouquets, transactions, income, etc.)
- Manage users
- Manage bouquets (CRUD + image upload)
- Manage transactions (accept, reject, ship orders)
- Manage testimonials
- Manage FAQs

## Tech Stack
- **Backend**: Python, Flask
- **Database**: MongoDB
- **Authentication**: JWT (PyJWT)
- **Frontend**: HTML, Jinja2 Templates, CSS, JavaScript
- **Other Libraries**:
  - pymongo
  - python-dotenv
  - werkzeug
  - pytz
  - hashlib

## Folder Structure
```
bouquet-web-app/
│
├── static/
│   ├── admin/
│   │   ├── css/
│   │   ├── img/
│   │   └── js/
│   ├── profile_pics/
│   └── user/
│       ├── css/
│       ├── img/
│       └── js/
│
├── templates/
│   ├── user/
│   │   ├── auth/
│   │   ├── dashboard.html
│   │   ├── profile.html
│   │   ├── collection.html
│   │   ├── payment.html
│   │   └── order_history.html
│   │
│   └── admin/
│       ├── auth/
│       ├── dashboard.html
│       ├── user.html
│       ├── bouquet.html
│       ├── transaction.html
│       ├── testimonial.html
│       ├── faq.html
│       └── contact_us.html
│
├── app.py
├── requirements.txt
└── README.md
```

## How to Run
### 1. Clone Repository
```bash
git clone https://github.com/kristian-susanto/Bouquet-Order-for-Final-Project-from-Independent-Student-at-LearningX.git
cd Bouquet-Order-for-Final-Project-from-Independent-Student-at-LearningX
```

### 2. Dependency Installation
It is recommended to use a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Mac/Linux
.\venv\Scripts\activate   # Windows
```

Once the virtual environment is active, install all dependencies in one of the following ways:
Using the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install flask pymongo pyjwt python-dotenv pytz werkzeug
```

### 3. .env File Configuration
Create a file named `.env` in the project root directory, then add your MongoDB configuration as follows:
```bash
MONGO_URI="mongodb+srv://<username>:<password>@<cluster>.mongodb.net/my_app_db?retryWrites=true&w=majority"
DB_NAME="your_database_name"
SECRET_KEY="your_secret_key"
TOKEN_KEY="your_token_key"
```
Replace `<username>`, `<password>`, and `<cluster>` with your MongoDB credentials and database details.
If you are using the MongoDB Atlas service, make sure your IP address has been whitelisted and that access from external applications has been enabled.

### 4. Run the Flask Application
```bash
python app.py
```
The application will open in the browser automatically at the address `http://localhost:5000`.

## Security Notes
- Passwords are hashed using SHA-256
- Authentication uses JWT stored in cookies
- Admin routes are protected with role-based middleware (admin_required)
- File uploads are handled securely using secure_filename

## Contributor
- [Kristian Susanto](https://github.com/kristian-susanto)
