# 🚗 AutoHub — Vehicle Marketplace

A Django web application for buying, selling, and renting vehicles in Pinamungajan and Toledo, Cebu.

---

## 📁 Project Structure

```
autohub_project/
├── autohub/              ← Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── core/                 ← Main app
│   ├── models.py         ← Database models
│   ├── views.py          ← Page logic
│   ├── forms.py          ← Forms
│   ├── urls.py           ← URL routes
│   ├── admin.py          ← Admin panel config
│   └── signals.py        ← Auto-notifications
├── templates/core/       ← All HTML pages
│   ├── base.html         ← Navbar + Footer layout
│   ├── home.html         ← Public homepage
│   ├── login.html
│   ├── signup.html
│   ├── dashboard.html    ← Browse listings
│   ├── vehicle_detail.html
│   ├── post_vehicle.html ← Post/Edit listing
│   ├── my_profile.html
│   ├── notifications.html
│   ├── about.html
│   ├── admin_dashboard.html
│   └── admin_users.html
├── static/css/
│   └── style.css
├── requirements.txt
├── manage.py
└── .env.example
```

---

## ⚡ Quick Setup (Local Development)

### Step 1 — Install Python & Virtual Environment
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
```

### Step 2 — Install Requirements
```bash
pip install -r requirements.txt
```

### Step 3 — Set Up Environment Variables
```bash
# Copy the example file
cp .env.example .env
# Edit .env with your database credentials
```

### Step 4 — Set Up PostgreSQL Database
```sql
-- In PostgreSQL (psql or pgAdmin):
CREATE DATABASE autohub_db;
CREATE USER autohub_user WITH PASSWORD 'your_password';
GRANT ALL PRIVILEGES ON DATABASE autohub_db TO autohub_user;
```
Update `.env` with your DB credentials.

### Step 5 — Run Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 6 — Create Admin User
```bash
python manage.py createsuperuser
```

### Step 7 — Collect Static Files
```bash
python manage.py collectstatic
```

### Step 8 — Run the Server
```bash
python manage.py runserver
```
Open: http://127.0.0.1:8000

---

## 🌐 Deploy to PythonAnywhere

1. Create account at pythonanywhere.com
2. Open a **Bash console** and upload your files:
   ```bash
   git clone <your-repo-url>  # OR upload via Files tab
   ```
3. Create virtual environment:
   ```bash
   mkvirtualenv autohub --python=python3.10
   pip install -r requirements.txt
   ```
4. Set up the database (use Supabase for free PostgreSQL)
5. Create `.env` file with your production values
6. Configure WSGI file at: `/var/www/yourusername_pythonanywhere_com_wsgi.py`
7. Run migrations:
   ```bash
   python manage.py migrate
   python manage.py collectstatic
   ```
8. Reload the web app

---

## 📸 Image Storage (Cloudinary)

1. Sign up free at [cloudinary.com](https://cloudinary.com)
2. Get your Cloud Name, API Key, and API Secret
3. Add them to your `.env` file
4. Images will automatically upload to Cloudinary

---

## 🗺️ Pages & URLs

| URL | Page |
|-----|------|
| `/` | Public Homepage |
| `/signup/` | Sign Up |
| `/login/` | Login |
| `/logout/` | Logout |
| `/dashboard/` | Browse All Vehicles |
| `/vehicles/<id>/` | Vehicle Detail |
| `/vehicles/post/` | Post a Vehicle |
| `/vehicles/<id>/edit/` | Edit Listing |
| `/profile/` | My Profile |
| `/notifications/` | Notifications |
| `/about/` | About Page |
| `/admin-panel/` | Admin Dashboard |
| `/admin/` | Django Admin |

---

## ✨ Features

- ✅ User registration with full name, email, phone number
- ✅ Profile picture upload
- ✅ Vehicle listings (sale & rent)
- ✅ Multiple photo uploads per listing
- ✅ Search & filter by brand, type, price, fuel
- ✅ Vehicle location with Google Maps embed
- ✅ Contact seller via phone or inquiry message
- ✅ Real-time notifications
- ✅ Admin panel with user & listing management
- ✅ My Profile with listing management
- ✅ Fully responsive design

---

## 🛠️ Tech Stack

- **Backend:** Python 3.10 + Django 4.2
- **Database:** PostgreSQL
- **Image Storage:** Cloudinary
- **Frontend:** Bootstrap 5 + Poppins font
- **Icons:** Bootstrap Icons
- **Hosting:** PythonAnywhere
