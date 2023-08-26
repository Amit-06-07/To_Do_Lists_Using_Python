# To_Do_Lists_Using_Python
# Initialize an empty list to store tasks
tasks = []

# Function to add a task
def add_task(task_name):
    tasks.append({"name": task_name, "completed": False})

# Function to list tasks
def list_tasks():
    for index, task in enumerate(tasks):
        status = "✓" if task["completed"] else " "
        print(f"{index + 1}. [{status}] {task['name']}")

# Function to mark a task as completed
def complete_task(task_index):
    if 0 <= task_index < len(tasks):
        tasks[task_index]["completed"] = True
        print("Task marked as completed.")
    else:
        print("Invalid task index.")

# Main loop
while True:
    print("\nTo-Do List")
    print("1. Add Task")
    print("2. List Tasks")
    print("3. Complete Task")
    print("4. Exit")
    
    choice = input("Select an option: ")

    if choice == "1":
        task_name = input("Enter task name: ")
        add_task(task_name)
    elif choice == "2":
        list_tasks()
    elif choice == "3":
        task_index = int(input("Enter task index to complete: ")) - 1
        complete_task(task_index)
    elif choice == "4":
        break
    else:
        print("Invalid choice. Please choose again.")
