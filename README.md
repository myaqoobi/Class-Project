# CSC299 Task Manager - Command Line Application

## Overview
This is a prototype command-line application that allows storing, listing, and searching tasks stored in a JSON data file. The application provides a simple yet powerful interface for task management through the command line.

## Features
- ✅ **Add Tasks**: Create new tasks with title, description, and priority
- 📋 **List Tasks**: View all tasks with optional filtering by status and priority
- 🔍 **Search Tasks**: Find tasks by searching through titles and descriptions
- ✏️ **Update Tasks**: Modify task status (pending, in_progress, completed)
- 🗑️ **Delete Tasks**: Remove tasks from the system
- 📊 **Statistics**: View task completion statistics and progress
- 💾 **JSON Storage**: All data is automatically saved to a JSON file

## Requirements
- Python 3.6 or higher
- No additional dependencies required (uses only Python standard library)

## Installation
1. Clone or download this repository
2. Navigate to the `tasks1` directory
3. No additional installation required - the application uses only Python standard library

## Usage

### Basic Commands

#### Add a Task
```bash
python task_manager.py add "Task Title" "Optional Description" "priority"
```

**Examples:**
```bash
python task_manager.py add "Buy groceries" "Get milk and bread" high
python task_manager.py add "Study for exam" "Review chapters 1-5" medium
python task_manager.py add "Walk the dog" low
```

#### List Tasks
```bash
python task_manager.py list [status] [priority]
```

**Examples:**
```bash
python task_manager.py list                    # List all tasks
python task_manager.py list pending           # List only pending tasks
python task_manager.py list completed high    # List completed high-priority tasks
```

#### Search Tasks
```bash
python task_manager.py search "search term"
```

**Examples:**
```bash
python task_manager.py search "groceries"
python task_manager.py search "study"
```

#### Update Task Status
```bash
python task_manager.py update <task_id> <new_status>
```

**Examples:**
```bash
python task_manager.py update 1 completed
python task_manager.py update 2 in_progress
```

#### Delete a Task
```bash
python task_manager.py delete <task_id>
```

**Example:**
```bash
python task_manager.py delete 1
```

#### View Statistics
```bash
python task_manager.py stats
```

#### Get Help
```bash
python task_manager.py help
```

## Task Properties

### Status Values
- `pending` - Task is not started
- `in_progress` - Task is currently being worked on
- `completed` - Task is finished

### Priority Values
- `low` - Low priority task
- `medium` - Medium priority task (default)
- `high` - High priority task

## Data Storage
- Tasks are automatically saved to `tasks.json` in the same directory
- The JSON file is created automatically when you add your first task
- All data persists between application runs
- The file format is human-readable JSON

## Example Session

```bash
# Add some tasks
$ python task_manager.py add "Complete CSC299 assignment" "Finish the task manager project" high
Task added successfully: 'Complete CSC299 assignment'

$ python task_manager.py add "Buy groceries" "Get milk, bread, and eggs" medium
Task added successfully: 'Buy groceries'

$ python task_manager.py add "Walk the dog" low
Task added successfully: 'Walk the dog'

# List all tasks
$ python task_manager.py list
================================================================================
TASK LIST (3 tasks)
================================================================================

ID: 1
Title: Complete CSC299 assignment
Description: Finish the task manager project
Status: ⏳ Pending
Priority: 🔴 High
Created: 2025-10-21 01:45:30
Updated: 2025-10-21 01:45:30
----------------------------------------

ID: 2
Title: Buy groceries
Description: Get milk, bread, and eggs
Status: ⏳ Pending
Priority: 🟡 Medium
Created: 2025-10-21 01:45:45
Updated: 2025-10-21 01:45:45
----------------------------------------

ID: 3
Title: Walk the dog
Status: ⏳ Pending
Priority: 🟢 Low
Created: 2025-10-21 01:46:00
Updated: 2025-10-21 01:46:00
----------------------------------------

# Search for tasks
$ python task_manager.py search "groceries"
================================================================================
SEARCH RESULTS for 'groceries' (1 task)
================================================================================

ID: 2
Title: Buy groceries
Description: Get milk, bread, and eggs
Status: ⏳ Pending
Priority: 🟡 Medium
Created: 2025-10-21 01:45:45
Updated: 2025-10-21 01:45:45
----------------------------------------

# Update a task status
$ python task_manager.py update 2 completed
Task 2 status updated from 'pending' to 'completed'

# View statistics
$ python task_manager.py stats
==================================================
TASK STATISTICS
==================================================
Total Tasks: 3
Pending: 2
In Progress: 0
Completed: 1

Priority Breakdown:
High Priority: 1
Medium Priority: 1
Low Priority: 1

Completion Rate: 33.3%
```

## File Structure
```
tasks1/
├── task_manager.py    # Main application file
├── README.md         # This documentation file
└── tasks.json        # Data file (created automatically)
```

## Error Handling
The application includes comprehensive error handling for:
- Invalid command arguments
- Missing required parameters
- Invalid task IDs
- Invalid status or priority values
- File I/O errors
- JSON parsing errors

## Author
Created for CSC299 - Computer Science Project Course

## License
This project is created for educational purposes as part of a class assignment.
