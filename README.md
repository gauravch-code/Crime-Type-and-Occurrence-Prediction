
---

# Crime Type and Occurrence Prediction

This project is a Django-based web application designed to predict and analyze different types of crimes based on historical crime data. It includes multiple Django apps, data files (CSV/Excel), and templates for both the user-facing and service-provider interfaces.

## Table of Contents
1. [Overview](#overview)  
2. [Features](#features)  
3. [Technologies Used](#technologies-used)  
4. [Installation & Setup](#installation--setup)  
5. [Usage](#usage)  
6. [Project Structure](#project-structure)  
7. [Database](#database)  
8. [License](#license)  
9. [Contact](#contact)

---

## Overview

The **Crime Type and Occurrence Prediction** system allows users (or administrators) to:
- Upload and manage crime-related data.
- Train machine learning models (e.g., Naive Bayes or other algorithms) to predict crime types or occurrences.
- View visualizations and charts related to crime statistics.
- Access various functionalities through distinct user roles (e.g., **Remote_User** vs. **Service_Provider**).

This application is intended for researchers, law enforcement, or anyone interested in analyzing and predicting crime patterns.

---

## Features

- **Multiple User Roles**:  
  - **Remote_User**: Can log in, register, view or search data, and interact with posted datasets.  
  - **Service_Provider**: Can train models, view user data, generate charts, and make crime predictions.
- **Machine Learning**: Integrates scripts (e.g., `Crime.py`) and data files (`crime.csv`, `offense_codes.csv`) to facilitate crime analysis and predictions.
- **Database Management**: Django migrations for structured data, plus an optional SQL file for direct database setup.
- **Template-Driven UI**: Organized HTML templates under `Template/htmls` for both **Remote_User** and **SProvider** views.

---

## Technologies Used

1. **Programming Language**: Python 3.7+  
2. **Web Framework**: Django  
3. **Database**: SQLite (default Django) or MySQL/PostgreSQL (if configured)  
4. **Front-End**: HTML, CSS, and basic JavaScript for templates  
5. **Data Files**: CSV/Excel (e.g., `crime.xlsx`, `crime.csv`, `offense_codes.csv`)  
6. **IDE/Editor**: (Optional) PyCharm or VSCode — project includes a `.idea` folder for PyCharm

---

## Installation & Setup

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/YourUsername/Crime_Type_and_Occurrence_Prediction.git
   cd Crime_Type_and_Occurrence_Prediction
   ```

2. **Create and Activate a Virtual Environment** (recommended)  
   ```bash
   python -m venv venv
   # Windows
   venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```

3. **Install Dependencies**  
   ```bash
   pip install -r requirements.txt
   ```
   If you don’t have a `requirements.txt`, install Django manually:
   ```bash
   pip install django
   ```

4. **Apply Migrations**  
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **(Optional) Create a Superuser**  
   ```bash
   python manage.py createsuperuser
   ```

6. **Run the Development Server**  
   ```bash
   python manage.py runserver
   ```
   The application should be accessible at [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

---

## Usage

1. **Accessing the Admin Panel**  
   - Go to `/admin` (e.g., [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)) and log in with your superuser credentials.

2. **Remote_User Functionalities**  
   - Register or log in via the user interface (e.g., `login.html`, `Register1.html`).  
   - Search or add dataset details (`Add_DataSet_Details.html`, `Search_DataSets.html`).  
   - View your profile (`ViewYourProfile.html`).

3. **Service_Provider Functionalities**  
   - Log in via `serviceproviderlogin.html`.  
   - Train machine learning models (`train_model.html`).  
   - Predict crime type (`Predict_Crime_Type.html`).  
   - Visualize data in charts (`charts.html`, `charts1.html`, `likeschart.html`, `dislikeschart.html`).  
   - Manage user data (`View_Remote_Users.html`, `Download_Trained_DataSets.html`).

4. **Data Files**  
   - `crime.csv`, `crime.xlsx`, and `offense_codes.csv` are located in the main application folder.  
   - You can replace or update these with your own data as needed.

---

## Project Structure

Below is a simplified version of your folder structure (omitting `__pycache__` and other generated files):

```
C:.
│   Crime_DataSets.xlsx
│   DataStructure.txt
│   README.md
│
├── .idea/                          # IDE-specific folder (PyCharm)
│   ├── Crime_Type_and_Occurrence_Prediction.iml
│   ├── misc.xml
│   ├── modules.xml
│   └── workspace.xml
│
├── crime_typeand_occurrence_prediction/
│   ├── crime.csv
│   ├── Crime.py
│   ├── crime.xlsx
│   ├── manage.py
│   ├── offense_codes.csv
│   │
│   ├── crime_typeand_occurrence_prediction/  # Main Django project folder
│   │   ├── asgi.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── __init__.py
│   │
│   ├── Remote_User/                # Django app for remote user functionality
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── forms.py
│   │   ├── models.py
│   │   ├── tests.py
│   │   ├── views.py
│   │   └── migrations/
│   │
│   ├── Service_Provider/           # Django app for service provider/admin
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── models.py
│   │   ├── tests.py
│   │   ├── views.py
│   │   └── migrations/
│   │
│   └── Template/                   # HTML templates for both apps
│       ├── htmls/
│       │   ├── images/
│       │   ├── media/
│       │   ├── RUser/             # Templates for Remote_User
│       │   └── SProvider/         # Templates for Service_Provider
│       └── images/
│           ├── bg.jpg
│           ├── Login.jpg
│           └── Register.jpg
│
├── Database/
│   └── crime_typeand_occurrence_prediction.sql
```

### Key Folders

- **`.idea/`**: PyCharm IDE settings (optional).  
- **`crime_typeand_occurrence_prediction/`**: Main Django project folder containing:
  - **`manage.py`**: Django management commands.  
  - **`Remote_User/`**: App for user-related features.  
  - **`Service_Provider/`**: App for admin/service provider features.  
  - **`Template/`**: Contains HTML templates, images, and other static files.
- **`Database/`**: Contains `.sql` dump for the database schema or data.
- **`DataStructure.txt`**: (Optional) A text file describing your data structure.
- **`Crime_DataSets.xlsx`**: Another dataset file (Excel format).

---

## Database

- By default, Django uses SQLite. You can configure your `settings.py` to connect to another database (MySQL, PostgreSQL, etc.).
- A SQL dump file (`crime_typeand_occurrence_prediction.sql`) is provided in the `Database/` folder if you prefer manually importing tables/data.
- Use Django migrations for seamless database creation and updates:
  ```bash
  python manage.py makemigrations
  python manage.py migrate
  ```

---

## Contact

- **Author**: Gaurav Chintakunta  
- **Email**: [gchin6@uic.edu](mailto:gchin6@uic.edu)  
- **GitHub**: [gauravch-code](https://github.com/gauravch-code)

For any questions or feedback, please open an issue on GitHub or reach out via email.
