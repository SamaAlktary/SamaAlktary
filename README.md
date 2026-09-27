# University Study Plans Management System

#### Video Demo: https://youtu.be/xVmlqYsf8wI

#### Description:

### Overview
The **University Study Plans Management System** is a localized, web-based platform designed specifically to streamline and simplify the academic journey for university students in the Gaza Strip. Navigating through multiple university websites to find study plans, credit hours, course syllabi, textbooks, and past exams can be overwhelming and fragmented for students. This project addresses this real-world problem by providing a centralized, responsive, and easy-to-use repository where students can seamlessly explore universities, browse detailed academic majors, view semester-by-semester course matrices, and access essential learning resources.

Built with **Python**, **Flask**, and **Bootstrap 5 (RTL)**, the application ensures a native and optimized experience for Arabic-speaking users. It features robust user authentication, role-based access control (Admin vs. Regular User), dynamic data management, and PDF export capabilities.

---

### Key Features
1. **User Authentication & Authorization:** Secure registration and login system implemented using Werkzeug security hashing. The platform distinguishes between standard students and administrators, dynamically rendering administrative control panels based on user roles.
2. **University & Major Directory:** Displays accredited universities operating within the Gaza Strip (such as Al-Azhar University, the Islamic University of Gaza, Al-Aqsa University, and University of Israa), listing all specialized faculties and academic majors.
3. **Structured Study Plans & Course Matrix:** Breaks down each academic major into structured semesters (years 1 through 4/5), detailing course codes, course names, credit hours, and prerequisites.
4. **Comprehensive Course Hub:** Clicking on any specific course opens a dedicated resource page containing official textbooks, lecture slide streams, video summaries, and archives of past exams.
5. **Dynamic Resource & User Management (Admin Dashboard):** Authorized administrators can add new study resources, link external Google Drive files, modify course details, and manage user roles (promoting users to admin status or revoking privileges).
6. **Print & PDF Export:** Integrated utility allowing students to print or export entire study plans cleanly for offline tracking.

---

### Project Structure & File Breakdown
The project follows a standard Flask MVC-like directory layout:

- **`app.py`**: The core backend application file written in Python using the Flask framework. It handles route definitions, database queries using SQLite (via `cs50` library or standard `sqlite3`), user session management, authentication decorators, and administrative logic.
- **`requirements.txt`**: Lists all external Python dependencies required to run the application (such as Flask, Werkzeug, etc.).
- **`static/`**: Contains static assets including custom CSS stylesheets, responsive layout overrides, and branding assets tailored for right-to-left (RTL) typography.
- **`templates/`**: Houses all Jinja2 HTML templates used to render dynamic views:
  - `layout.html`: The base layout template containing the navigation bar, footer, and shared Bootstrap 5 CDN links.
  - `index.html`: The landing page welcoming students and showcasing available universities.
  - `login.html` & `register.html`: User authentication interfaces with form validation.
  - `majors.html`: Displays specialized tracks and departments for selected universities.
  - `course_details.html`: The detailed view for individual courses, showing prerequisites, textbooks, and resources.
  - `admin_resources.html` & `admin_users.html`: The administrative dashboards for managing course assets and user permissions.

---

### Design Choices & Rationale
- **Why Flask and Python?** Python provides a clean, readable, and highly extensible backend environment. Flask was chosen over Django because of its lightweight and micro-framework nature, giving full flexibility over database design and routing structure without unnecessary boilerplate overhead.
- **Why Bootstrap 5 with RTL?** Since the platform is fully in Arabic, implementing a Right-to-Left (RTL) layout was crucial for usability. Bootstrap 5 offers robust native RTL support (`dir="rtl"`), ensuring that tables, navigation bars, cards, and forms align naturally for Arabic readers.
- **Typography Selection (Tajawal Font):** Standard system fonts can look unpolished. Incorporating Google Fonts (Tajawal) provides a modern, clean, and highly readable typographic hierarchy tailored for Arabic educational interfaces.
- **Role-Based Access Control Design:** Separating normal student views from the administrative panel ensures data integrity, preventing unauthorized users from altering official study plans or adding unverified resources while keeping the platform collaborative and maintainable.

---

### How to Run the Project Locally
1. Ensure you have Python installed on your system.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt