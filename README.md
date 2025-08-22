# 📝 To-Do List App in C++

## 📌 Overview
This is a console-based **To-Do List Manager** written in **C++**.  
It supports **user authentication (Register/Login)**, and allows managing tasks with attributes like title, description, status, and priority.  

Tasks are stored in a **`username.txt`** file, enabling persistence across sessions.

---

## 🔑 Features

### 👤 Authentication
- Register new users (username + password, password stored in encrypted form).
- Login with existing credentials.

### 📂 Task Management
- Add a task (with title, description, and priority number).
- Delete a task by ID.
- Search for a task by ID.
- Update an existing task.
- Change task status (Pending ↔ Completed).

### 📋 Task Display
- Print **all tasks**.
- Print only **pending tasks**.
- Print only **completed tasks**.
- Tasks are displayed with **color-coded output** (using ANSI escape codes).

---

## ⚙️ Classes & Structures

### `struct Task`
Represents a task in the list.  
- `int id` → Unique ID for the task.  
- `string title` → Task title.  
- `string description` → Task details.  
- `bool status` → Completion status (false = pending, true = completed).  
- `int priority` → Task priority (lower number = higher priority).  

---

### `class ToDoManager`
Manages the list of tasks.  

#### Methods
- `mainMenu()` → Displays main task menu.  
- `addTask()` → Adds a new task.  
- `deleteTask()` → Deletes a task by ID.  
- `searhTaskById()` → Searches for a task by ID.  
- `printAllTask()` → Displays all tasks.  
- `printAllTaskPending()` → Displays only pending tasks.  
- `printAllTaskCompleted()` → Displays only completed tasks.  
- `changeStatusOfTask()` → Toggles task completion status.  
- `updateTask()` → Updates an existing task.  
- `saveTasks()` / `loadTasks()` → Stores and loads tasks from `<username>.txt`.  

---

### `class Authentication : public ToDoManager`
Handles **user registration and login**.  

#### Methods
- `authMainMenu()` → Authentication menu (Register / Login / Exit).  
- `registerUser()` → Registers a new user.  
- `login()` → Authenticates a user and loads their tasks.  

---

## 📚 Libraries Used
- `<iostream>` → Input/output operations.  
- `<fstream>` → File handling (save/load tasks).  
- `<string>` → Handling user input and task details.  
- `<queue>` & `<vector>` → Priority queue for managing tasks.  
- `"encryption.cpp"` → Used for password encryption.  

---
### Prerequisites
- A C++ compiler (e.g., g++, clang++)
- A text editor or IDE (e.g., VSCode, CLion)
  
### Installation
1. Clone the repository:
   ```sh
    git clone https://github.com/naemazam/to-do-cpp.git
    cd project1
    ```
2. Compile the application:
    ```sh
    g++ -std=c++17 -o first todo.cpp
    ```
### Usage
Run the application:
```sh
./first
```
### Example
Upon running the application, you will be presented with an **Authentication Menu** (Register / Login).  
After successful login, the **Main Menu** will allow you to add, delete, update, search, display, and manage tasks.  
Tasks are displayed with color-coded output, and changes are saved automatically in a `<username>.txt` file.  

## File Structure
- **main.cpp**: The main file containing the entry point and all core logic.  
- **encryption.cpp**: File containing encryption logic for securing user passwords.  
- **<username>.txt**: User-specific file that stores tasks persistently (created automatically after registration).  
- **README.md**: This README file.  

## Future Enhancements
- Add support for **task deadlines** and due date reminders.  
- Implement **categories or labels** to group tasks.  
- Improve password encryption with stronger hashing.  
- Add a **search function by task title/description**.  
- Create a **graphical user interface (GUI)** for better usability.  
