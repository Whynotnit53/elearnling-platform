# 🎓 eLearning Platform

A modern, responsive eLearning platform built using **Django** and **Tailwind CSS**.  
This platform allows students to access courses, assignments, interactive code compiler, and video lectures in a clean, user-friendly interface.

---

## 🚀 Features

- 👤 **User Authentication & Role Management** (Student, Instructor, Admin)
- 📚 **Course Management & Curriculum**
- 🎥 **Lecture Video Support**
- 📝 **Assignment System** (Upload & Submissions)
- 💻 **Online Code Compiler** (Judge0 API Integration)
- 💬 **Discussion Forum**
- 📜 **University-Branded Certificate Generation** (ReportLab PDF)
- 🎨 **Modern UI** with Tailwind CSS & FontAwesome
- 📱 **Fully Responsive Design**

---

## 🛠 Tech Stack

- **Backend:** Python, Django 5
- **Frontend:** HTML5, Tailwind CSS, JavaScript, FontAwesome
- **Database:** SQLite (default) / PostgreSQL
- **Production Server:** Gunicorn + WhiteNoise
- **Deployment:** Render / Vercel

---

## 💻 Local Setup & Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Whynotnit53/elearnling-platform.git
   cd elearnling-platform
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations:**
   ```bash
   python manage.py migrate
   ```

5. **(Optional) Create code compiler templates & superuser:**
   ```bash
   python manage.py create_code_templates
   python manage.py createsuperuser
   ```

6. **Start the development server:**
   ```bash
   python manage.py runserver
   ```
   Open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

---

## ☁️ Deployment on Render (Free & Recommended)

1. Sign up or log in at [Render.com](https://render.com) using your GitHub account.
2. Click **New +** → **Web Service**.
3. Select and connect your repository: `Whynotnit53/elearnling-platform`.
4. Fill in the deployment configuration:
   - **Name:** `elearnling-platform` (or any unique name)
   - **Region:** Any close to you (e.g., Oregon, Frankfurt, Singapore)
   - **Branch:** `main`
   - **Runtime:** `Python 3`
   - **Build Command:** `./build.sh`
   - **Start Command:** `gunicorn elearning_platform.wsgi:application`
   - **Instance Type:** Free
5. Under **Environment Variables**, add:
   - `PYTHON_VERSION`: `3.11.9`
   - `SECRET_KEY`: (any long random string)
   - `DEBUG`: `False`
6. Click **Create Web Service**.
7. Render will automatically build the app, run migrations, collect static files, and serve your app at:
   `https://<your-service-name>.onrender.com`
