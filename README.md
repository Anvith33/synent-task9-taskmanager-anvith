Task 9 – Full Stack Python Project (Task Manager Web Application)

Description:

This project is a Full Stack Task Manager Web Application developed using Python Flask, SQLite, HTML, and CSS as part of the Synent Technologies Python Development Internship.

The application enables users to register, log in, create and manage tasks, set due dates, track task status, and securely access their own tasks through session-based authentication.

Features:

User Authentication,
User Registration,
User Login,
User Logout,
Session Handling,
Protected Routes,
Task Management,
Add New Tasks,
View Tasks,
Edit Existing Tasks,
Delete Tasks,
Mark Tasks as Completed.

Additional Features:

Due Date Tracking,
Task Status (Pending / Completed),
User-Specific Task Lists,
SQLite Database Integration,
Responsive User Interface.

Technologies Used:

Python 3,
Flask,
SQLite,
HTML5,
CSS3.

Project Workflow:

User registers an account,
User logs into the application,
Flask creates a session for the authenticated user,
User creates tasks with due dates,
Tasks are stored in SQLite database,
Users can edit, complete, and delete tasks,
Each user can only access their own tasks,
User can logout securely.

Project Structure:

synent-task9-fullstack-python-project-anvith

│

├── app.py

├── tasks.db

├── README.md

│

├── templates

│   ├── index.html

│   ├── edit.html

│   ├── login.html

│   └── register.html

│

└── static

|    └── style.css

Register link:

http://127.0.0.1:5000/register


### Logic of Task 9 – Full Stack Task Manager

1. The application starts by creating the required SQLite database tables (`users` and `tasks`) if they do not already exist.

2. A new user can register using a username and password. The user information is stored in the `users` table.

3. After registration, the user can log in using their credentials.

4. During login, the application verifies the username and password from the database.

5. If the credentials are correct, Flask creates a session using:

```python
session["user_id"] = user[0]
```

This session keeps the user logged in.

6. When a logged-in user creates a task, the task is stored in the `tasks` table along with the user's ID (`user_id`).

7. The application retrieves only those tasks whose `user_id` matches the currently logged-in user.

8. Users can:

   * Add new tasks
   * Edit existing tasks
   * Mark tasks as completed
   * Delete tasks

9. Each task contains:

   * Task Name
   * Due Date
   * Status (Pending/Completed)

10. The logout feature clears the session using:

```python
session.clear()
```

and redirects the user to the login page.

11. The application prevents unauthorized access by checking whether `user_id` exists in the session before displaying the Task Manager dashboard.

12. This ensures that each user can access only their own tasks, making the application secure and user-specific.
