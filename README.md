# Library Management System (LMS)

A full-stack web application for managing library operations including book inventory, lending, reservations, and user accounts.

## Tech Stack

### Backend
- **Django** - Web framework
- **Django REST Framework** - REST API development
- **SQLite** - Database (default)
- **Python 3.x**

### Frontend
- **React** - UI library
- **JavaScript (ES6+)** - Programming language
- **Axios** - HTTP client
- **CSS** - Styling

## Project Structure

```
LMS/
├── backend/                    # Django backend
│   ├── manage.py
│   ├── requirements.txt
│   ├── accounts/              # User authentication & management
│   ├── books/                 # Book inventory management
│   ├── lending/               # Book lending operations
│   ├── reservations/          # Book reservations
│   ├── book_requests/         # Book request management
│   └── backend/               # Django settings & configuration
│
├── frontend/                  # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   ├── pages/             # Page components
│   │   │   ├── Auth/          # Login & registration
│   │   │   └── dashboard/     # Role-based dashboards
│   │   ├── context/           # React context for state management
│   │   ├── api/               # API service layer
│   │   └── App.js
│   ├── package.json
│   └── README.md
│
└── README.md                  # This file
```

## Features

- **User Authentication** - Registration, login, and role-based access (Admin, Librarian, Member)
- **Book Management** - Add, update, and manage book inventory
- **Lending System** - Borrow and return books with tracking
- **Reservations** - Reserve books for future borrowing
- **Book Requests** - Request new books for the library
- **Admin Dashboard** - Reports and system management
- **Librarian Tools** - Manage books, lending, reservations, and requests
- **Member Portal** - View borrowed books, make requests, and reservations

## Prerequisites

- **Python 3.8+**
- **Node.js 14+** and npm
- **Git**

## Installation

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run migrations:**
   ```bash
   python manage.py migrate
   ```

6. **Create a superuser (admin account):**
   ```bash
   python manage.py createsuperuser
   ```

7. **Start the Django development server:**
   ```bash
   python manage.py runserver
   ```
   The backend will run at `http://localhost:8000`

### Frontend Setup

1. **Navigate to frontend directory (in a new terminal):**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the React development server:**
   ```bash
   npm start
   ```
   The frontend will run at `http://localhost:3000`

## Running the Project

1. **Terminal 1 - Backend:**
   ```bash
   cd backend
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   python manage.py runserver
   ```

2. **Terminal 2 - Frontend:**
   ```bash
   cd frontend
   npm start
   ```

The application will be accessible at `http://localhost:3000`

## API Endpoints

### Authentication
- `POST /api/accounts/register/` - User registration
- `POST /api/accounts/login/` - User login
- `POST /api/accounts/logout/` - User logout

### Books
- `GET /api/books/` - List all books
- `POST /api/books/` - Create a new book (Librarian/Admin)
- `GET /api/books/{id}/` - Get book details
- `PUT /api/books/{id}/` - Update book (Librarian/Admin)
- `DELETE /api/books/{id}/` - Delete book (Admin)

### Lending
- `POST /api/lending/` - Borrow a book
- `GET /api/lending/` - List borrowing history
- `PUT /api/lending/{id}/` - Return a book

### Reservations
- `POST /api/reservations/` - Create a reservation
- `GET /api/reservations/` - List reservations
- `DELETE /api/reservations/{id}/` - Cancel reservation

### Book Requests
- `POST /api/book-requests/` - Request a new book
- `GET /api/book-requests/` - List book requests
- `PUT /api/book-requests/{id}/` - Update request status

## Development

### Backend Testing
```bash
cd backend
python manage.py test
```

### Frontend Testing
```bash
cd frontend
npm test
```

### Frontend Build
```bash
cd frontend
npm run build
```

## Database

The project uses **SQLite** by default (stored as `db.sqlite3`). To use a different database:
1. Update `DATABASES` in [backend/backend/settings.py](backend/backend/settings.py)
2. Install the appropriate database driver
3. Run migrations: `python manage.py migrate`

## Configuration

### Django Settings
- Update `SECRET_KEY` in [backend/backend/settings.py](backend/backend/settings.py) for production
- Configure `ALLOWED_HOSTS` for your domain
- Set up CORS in `INSTALLED_APPS`

### Environment Variables
Create a `.env` file in the backend directory for sensitive data:
```
DEBUG=True
SECRET_KEY=your-secret-key
DATABASE_URL=sqlite:///db.sqlite3
```

## Troubleshooting

### Backend won't start
- Ensure virtual environment is activated
- Run `python manage.py migrate` to initialize the database
- Check port 8000 is not in use

### Frontend won't start
- Delete `node_modules` and `package-lock.json`, then run `npm install`
- Ensure Node.js and npm are installed correctly
- Check port 3000 is not in use

### API connection issues
- Verify backend is running on `http://localhost:8000`
- Check CORS settings in Django settings
- Verify API base URL in [frontend/src/api/axiosInstance.js](frontend/src/api/axiosInstance.js)



**Last Updated:** June 2026
#
