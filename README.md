This Java program implements a To-Do List Application that allows users to manage their tasks effectively. It provides functionalities such as adding tasks, removing tasks, marking tasks as complete, and viewing all tasks. The program is structured into three main components: the Task class, the TaskManager class, and the ToDoListApp main class. Here's a detailed breakdown of the code:


---

1. Task Class

The Task class represents an individual task in the to-do list. It implements the Serializable interface to enable saving and loading tasks to/from a file.

Fields:

title - The name of the task.

category - The category or type of the task (e.g., Work, Personal).

dueDate - The due date for the task (LocalDate type).

isComplete - A boolean indicating whether the task has been completed.


Methods:

Constructor: Initializes a task with a title, category, and due date. By default, tasks are incomplete (isComplete = false).

Getters: Provide access to the task's fields (getTitle(), getCategory(), getDueDate(), and isComplete()).

markComplete(): Marks the task as complete by setting isComplete to true.

toString(): Returns a string representation of the task for easy viewing.



---

2. TaskManager Class

The TaskManager class is responsible for managing the list of tasks. It provides functionalities to add, remove, mark as complete, and retrieve tasks. Additionally, it handles saving and loading tasks to/from a file for persistence.

Fields:

tasks - A List<Task> to store all tasks.

FILE_NAME - The name of the file used to store the tasks (tasks.ser).


Methods:

Constructor: Loads tasks from the file when the TaskManager is initialized.

addTask(Task task): Adds a new task to the list and saves the updated list to the file.

removeTask(String title): Removes a task by its title (case-insensitive) and saves the updated list.

markTaskComplete(String title): Marks a task as complete by its title (case-insensitive) and saves the updated list.

getTasks(): Returns the list of tasks.

saveTasks(): Saves the current list of tasks to a file using ObjectOutputStream.

loadTasks(): Loads tasks from the file using ObjectInputStream. If the file does not exist or an error occurs, it initializes an empty task list.



---

3. ToDoListApp Class

This is the main class where the application is run. It provides a menu-driven interface for interacting with the to-do list. The user can input their choices, and the application executes the corresponding functionality.

Features:

1. Add Task:

Prompts the user to enter the task's title, category, and due date.

Creates a new Task object and adds it to the TaskManager.



2. Remove Task:

Prompts the user to enter the title of the task to remove.

If a matching task exists, it is removed from the list.



3. Mark Task as Complete:

Prompts the user to enter the title of the task to mark as complete.

Updates the isComplete field of the matching task.



4. View Tasks:

Displays all tasks with details including title, category, due date, and completion status.



5. Exit:

Terminates the program.





---

Persistence:

Tasks are saved to a file (tasks.ser) when any operation modifies the list (e.g., adding, removing, or marking tasks as complete).

Upon restarting the program, tasks are loaded from this file, ensuring data persistence.



---

How It Works:

1. Initialization:
The TaskManager is initialized, which loads tasks from the file (if available).


2. Menu Options:

The user is presented with a menu to choose an operation.

Based on the user's choice, the corresponding method in TaskManager is called.



3. Task Management:

Tasks are added, removed, or marked complete as per the user's input.

The task list is saved to the file after every operation.



4. Task Viewing:

The user can view all tasks with their details at any time.



5. Exit:

Exits the program. Any unsaved data will already be stored due to the save operation in each modifying method.





---

Example Interaction:

Scenario:

1. Add a task:
Input:

Title: Buy Groceries
Category: Personal
Due Date: 2025-01-16

Output:
Task added successfully!


2. View tasks:
Output:

Task: Buy Groceries | Category: Personal | Due: 2025-01-16 | Completed: No


3. Mark task as complete:
Input: Buy Groceries
Output: Task marked as complete!


4. View tasks:
Output:

Task: Buy Groceries | Category: Personal | Due: 2025-01-16 | Completed: Yes


5. Remove task:
Input: Buy Groceries
Output: Task removed successfully!




---

Advantages of the Program:

Simple and user-friendly interface.

Data persistence using file serialization.

Modular structure with separate classes for task management and the main application.

Flexibility to add more features in the future (e.g., task prioritization or search functionality).


