
# Hospital Management Backend using Django REST API

This is a RESTful backend for a Hospital Management System built with Django and Django REST Framework.
It provides modular APIs for managing patients, doctors, appointments, services, contact queries, and authentication.

Live Project: 👉 **[https://hospital-management-backend-using-django.onrender.com/](https://hospital-management-backend-using-django.onrender.com/)**


## 🔧 Features

* 🩺 **Doctor Management**: Specializations, designations, availability, reviews
* 👨‍⚕️ **Patient Management**: Registration, login, logout, activation, CRUD operations
* 📅 **Appointment Booking**: Schedule and manage appointments via API
* 📞 **Contact API**: Submit and manage user contact inquiries
* 💉 **Service API**: List available medical services
* 🔐 **Token-based Authentication**
* ⚙️ **Modular Django apps for clean architecture**

---

## 🚀 Tech Stack

* **Backend Framework**: Django 5.2.3
* **API**: Django REST Framework (DRF)
* **Database**: PostgreSQL (Render), SQLite (local)
* **Others**: django-filter, dj-database-url, django-environ

---

## 📁 Project Structure Overview

```
smart_care/               # Django project folder
├── settings.py           # Main settings including db, apps, middleware
├── urls.py               # Root URL configuration
├── wsgi.py               # WSGI entry point for deployment
├── asgi.py               # ASGI entry point (if needed)

doctor/                   # App for managing doctors
├── models.py
├── views.py
├── urls.py
├── serializers.py

patient/                  # App for patient data and auth
├── models.py
├── views.py
├── urls.py
├── serializers.py

appointment/              # App for appointment booking
contact/                  # App for contact form management
service/                  # App for listing hospital services
```

---

## 🌐 API Endpoints Overview

| Module      | Endpoint Prefix | Example Endpoints                       |
| ----------- | --------------- | --------------------------------------- |
| Admin       | `/admin/`       | Django Admin Panel                      |
| Contact     | `/contact/`     | `GET`, `POST` for contact inquiries     |
| Service     | `/service/`     | List of services offered                |
| Patient     | `/patient/`     | List, Register, Login, Logout, Activate |
| Doctor      | `/doctor/`      | List doctors, Specializations, Reviews  |
| Appointment | `/appointment/` | Create/list appointments                |

### 🧪 Example Patient Auth Endpoints

* `POST /patient/register/`
* `POST /patient/login/`
* `POST /patient/logout/`
* `GET /patient/activate/<uid64>/<token>/`

---

## ⚙️ Local Setup Instructions

### 1. Clone the repository

```bash
git clone <repo-url>
cd Hospital-Management-Backend-Using-Django-REST-API
```

### 2. Create and activate a virtual environment

```bash
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Apply migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Run the development server

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/`

---

## 🔐 Authentication

This project supports token-based authentication using Django REST Framework’s built-in mechanisms.
Patients can register, log in to get a token, and use that token for authorized API requests.

---

## 🧪 Testing API

You can test the API using:

* **Postman**
* **cURL**
* **DRF's browsable API** (enabled in development)

---

## 🗃️ Database

* **SQLite** used by default in development (`db.sqlite3`)
* **PostgreSQL** used in production (configured via `dj_database_url`)

---

## 📦 Deployment

Deployed on [Render.com](https://render.com/) with:

* PostgreSQL Database
* Gunicorn as WSGI server
* Static/media handling (can integrate with WhiteNoise/S3)


