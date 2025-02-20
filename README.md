# Task Management API

Welcome to the Task Management API, a powerful tool built with Laravel that allows users to manage projects, tasks, and comments efficiently.

## Features

- **User Authentication**: Secure user registration and login
- **Project Management**: Create, update, and manage projects
- **Task Management**: Handle tasks within projects
- **Comment Management**: Add and manage comments on tasks and projects

## Getting Started

### Prerequisites

Make sure you have the following installed on your machine:

- PHP
- Composer
- Laravel
- MySQL (or any other supported database)

### Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/i4sam/midad-training-task-management-api.git
    cd midad-training-task-management-api
    ```

2. **Install dependencies:**
    ```sh
    composer install
    ```

3. **Set up your environment variables:**
    ```sh
    cp .env.example .env
    ```
    Configure the `.env` file according to your environment.

4. **Generate application key:**
    ```sh
    php artisan key:generate
    ```

5. **Run migrations and seed the database:**
    ```sh
    php artisan migrate --seed
    ```

6. **Start the development server:**
    ```sh
    php artisan serve
    ```

### Using Postman Collection

1. **Import the Postman Collection:**
    - Open Postman.
    - Click on `Import` in the top left corner.
    - Select the `Task Management API.postman_collection.json` file from the project root.

2. **Set the base URL:**
    - Go to the `Environments` section in Postman.
    - Create a new environment and set the `base_url` variable to your application's URL (e.g., `http://127.0.0.1:8000`).

3. **Test the API:**
    - Use the endpoints provided in the collection to test the API functionalities.

### API Endpoints

#### Authentication

- `POST /api/register` - Register a new user
- `POST /api/login` - Login a user

#### User

- `GET /api/user` - Get authenticated user details
- `GET /api/user/projects` - Get user projects
- `GET /api/user/tasks` - Get user tasks

#### Projects

- `GET /api/projects` - Get all projects
- `POST /api/projects` - Create a new project
- `GET /api/projects/{project_id}` - Get project details
- `PUT /api/projects/{project_id}` - Update project
- `DELETE /api/projects/{project_id}` - Delete project
- `GET /api/projects/{project_id}/users` - Get users in a project
- `POST /api/projects/{project_id}/invite` - Invite user to project
- `GET /api/projects/{project_id}/accept/{invitee_id}` - Accept project invitation
- `PUT /api/projects/{project_id}/users/{userId}/role` - Update user role in project
- `DELETE /api/projects/{project_id}/users/{userId}` - Remove user from project

#### Tasks

- `POST /api/projects/{project_id}/tasks` - Create a task
- `GET /api/projects/{project_id}/tasks` - Get all tasks in a project
- `GET /api/projects/{project_id}/tasks/{task_id}` - Get task details
- `PUT /api/projects/{project_id}/tasks/{task_id}` - Update task
- `DELETE /api/projects/{project_id}/tasks` - Delete tasks
- `PUT /api/projects/{project_id}/tasks/{task_id}/status` - Update task status
- `GET /api/projects/{project_id}/users/{userId}/tasks` - Get user tasks in project

#### Project Comments

- `GET /api/projects/{project_id}/comments` - Get all comments in a project
- `POST /api/projects/{project_id}/comments` - Create a project comment
- `PUT /api/projects/{project_id}/comments/{comment_id}` - Update project comment
- `DELETE /api/projects/{project_id}/comments/{comment_id}` - Delete project comment

#### Task Comments

- `GET /api/tasks/{task_id}/comments` - Get all comments in a task
- `POST /api/tasks/{task_id}/comments` - Create a task comment
- `PUT /api/tasks/{task_id}/comments/{comment_id}` - Update task comment
- `DELETE /api/tasks/{task_id}/comments/{comment_id}` - Delete task comment
