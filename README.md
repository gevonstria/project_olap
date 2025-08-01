# Django Online Loan Application System

## Project Overview

This is a full-featured online loan application system built with Django and Docker. The platform provides a secure and user-friendly interface for applicants to submit their information and a robust backend for administrators to review and manage loan applications. The system utilizes a two-factor authentication (OTP) flow for enhanced user security.

## Features

* **User Authentication:** Secure login with username/password and two-factor authentication (OTP).

* **Two-Factor Authentication (OTP):** A one-time password is sent to the user's email to verify their identity upon login.

* **Application Backend:** A dedicated Django backend for application logic and data management.

* **Admin Dashboard:** A built-in Django admin interface for administrators to manage users and other data.

* **Containerized Environment:** The entire application is containerized using Docker, providing a consistent and isolated development and production environment.

## Technologies Used

* **Backend:** Python 3.9, Django, Gunicorn, PostgreSQL

* **Frontend:** HTML5, Bootstrap 5

* **Dependencies:** `psycopg2-binary`, `python-decouple`, `dj-database-url`

* **Tools:** Docker, Docker Compose, Git

## Setup and Installation

### Prerequisites

* Docker and Docker Compose must be installed on your machine.

### Instructions

1.  **Clone the repository:**

    ```bash
    git clone [your-repo-url]
    cd [your-repo-name]
    ```

2.  **Create a `.env` file:**
    In the root of your project directory, create a `.env` file with the following content. **Remember to generate a new, secure `SECRET_KEY`.**

    ```env
    DATABASE_URL=postgres://django_user:mysecretpassword@db:5432/django_db
    SECRET_KEY=a-new-random-secret-key-that-you-should-generate
    ```

3.  **Build and run the Docker containers:**

    ```bash
    docker-compose up --build
    ```

    This command will build the Django image, start the PostgreSQL database, and run the Django web server.

4.  **Run database migrations:**

    ```bash
    docker-compose exec web python manage.py migrate
    ```

5.  **Create a superuser (admin account):**

    ```bash
    docker-compose exec web python manage.py createsuperuser
    ```

    Follow the prompts to set up your admin username, email, and password.

6.  **Access the application:**
    Open your web browser and navigate to `http://127.0.0.1:8000`.

## Usage

* **Public Access:** The application's main page is a placeholder. You can access the custom login page at `http://127.0.0.1:8000/login/`.

* **Admin Access:** The administrative interface is available at `http://127.0.0.1:8000/admin/`. Use the superuser credentials you created to log in and manage the system.
