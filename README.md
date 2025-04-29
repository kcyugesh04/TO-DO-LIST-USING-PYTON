## NAME:YUGESH K C
## REG NO:111923AI01118
## DEPARTMENT:B.TECH (AI&DS)

#  TASK 1-TO-DO-LIST-USING-PYTHON

## PROGRAM:
```
import json
import os

TODO_FILE = "todo.json"

def load_tasks():
    if os.path.exists(TODO_FILE):
        with open(TODO_FILE, "r") as f:
            return json.load(f)
    return []

def save_tasks(tasks):
    with open(TODO_FILE, "w") as f:
        json.dump(tasks, f, indent=4)

def add_task(tasks):
    task = input("Enter the task: ")
    tasks.append({"task": task, "done": False})
    save_tasks(tasks)

def view_tasks(tasks):
    for i, t in enumerate(tasks):
        status = "✔" if t["done"] else "✘"
        print(f"{i + 1}. [{status}] {t['task']}")

def mark_done(tasks):
    view_tasks(tasks)
    idx = int(input("Enter task number to mark done: ")) - 1
    if 0 <= idx < len(tasks):
        tasks[idx]["done"] = True
        save_tasks(tasks)

def delete_task(tasks):
    view_tasks(tasks)
    idx = int(input("Enter task number to delete: ")) - 1
    if 0 <= idx < len(tasks):
        tasks.pop(idx)
        save_tasks(tasks)

def main():
    tasks = load_tasks()
    while True:
        print("\n1. View Tasks\n2. Add Task\n3. Mark Done\n4. Delete Task\n5. Exit")
        choice = input("Choose an option: ")
        if choice == "1":
            view_tasks(tasks)
        elif choice == "2":
            add_task(tasks)
        elif choice == "3":
            mark_done(tasks)
        elif choice == "4":
            delete_task(tasks)
        elif choice == "5":
            break
        else:
            print("Invalid option")

if __name__ == "__main__":
    main()
```

## OUTPUT:
![Screenshot 2025-04-29 205232](https://github.com/user-attachments/assets/94cb4722-0d07-4b0d-98e1-5490467f502f)
![Screenshot 2025-04-29 205610](https://github.com/user-attachments/assets/de00d599-17f5-4f9e-a19f-b9e1df06ecf2)

## RESULT:
THE CODE HAS BEEN EXECUTED SUCCESSFULLY
