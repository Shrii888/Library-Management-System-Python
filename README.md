If the file does not exist, the system starts with an empty library.

This allows the application to retain previously saved records across different sessions.

---

### 2. ➕ Add Book

The `add_book()` function allows the user to add a new book to the library.

The user is asked to enter:

- Book ID
- Book Title
- Author Name

Each newly added book is stored with an availability status of `True`.

```python
book = {
    "id": book_id,
    "title": title,
    "author": author,
    "available": True
}
```

After the book is added to the `library` list, `save_records()` is called so that the new book is permanently stored in `library.json`.

Example:

```text
Enter book id: 1
Enter title of the book: Python Basics
Enter author's name: John Smith

Book added successfully!
```

---

### 3. 📚 Display Available Books

The `display_available_books()` function displays all books that are currently available.

The function checks:

```python
if book["available"]:
```

Only books whose availability is `True` are displayed.

Example:

```text
Available Books
------------------------------------------------------------
ID: 1
Title: Python Basics
Author: John Smith
------------------------------------------------------------
```

---

### 4. 🔎 Search Book

The `search_book()` function allows the user to search for a book by title.

The search uses:

```python
search_title.lower() in book["title"].lower()
```

This makes the search case-insensitive and allows partial title matching.

For example, searching for:

```text
The Fault in Our stars
```

can find:

```text
The Fault in Our Stars
```

The search result displays:

- Book ID
- Book Title
- Author
- Availability Status

Example:

```text
Book found!
ID: 8
Title: The Fault in Our Stars
Author: John Green
Status: Available
```

If there is no matching book:

```text
Book not found.
```

---

### 5. 📖 Issue Book

The `issue_book()` function allows the user to issue a book using its Book ID.

The function checks whether the selected book exists and whether it is currently available.

When a book is issued:

```python
book["available"] = False
```

The updated record is then saved using:

```python
save_records()
```

Example:

```text
Enter book ID to issue: 7

Book issued successfully!
```

If the book is already issued:

```text
Book is already issued!
```

If the Book ID does not exist:

```text
Book not found!
```

---

### 6. ↩️ Return Book

The `return_book()` function allows the user to return a previously issued book.

The function checks:

```python
if not book["available"]:
```

If the book is currently issued, its status is changed back to available:

```python
book["available"] = True
```

The change is then saved permanently.

Example:

```text
Enter book id to return: 7

Book returned successfully!
```

If the book is already available:

```text
Book is already available!
```

If the Book ID does not exist:

```text
Book not found!
```

---

### 7. 💾 Save Records

The project uses the `save_records()` function to permanently store library records.

```python
def save_records():
    with open("library.json", "w") as file:
        json.dump(library, file, indent=4)
```

The function is called after important changes such as:

- Adding a book
- Issuing a book
- Returning a book
- Manually choosing Save Records
- Exiting the application

This ensures that changes are not lost when the notebook or application is closed.

---

### 8. 🖥️ Main Library Management System

The `library_management_system()` function brings all the individual functions together into one menu-driven application.

The menu is:

```text
===== LIBRARY MANAGEMENT SYSTEM =====
1. Add Book
2. Search Book
3. Issue Book
4. Return Book
5. Display Available Books
6. Save Records
7. Exit
```

The system uses a `while True` loop to keep displaying the menu until the user selects `7. Exit`.

The menu connects to the functions as follows:

| Choice | Function |
|--------|----------|
| 1 | `add_book()` |
| 2 | `search_book()` |
| 3 | `issue_book()` |
| 4 | `return_book()` |
| 5 | `display_available_books()` |
| 6 | `save_records()` |
| 7 | Save records and exit |

If an invalid option is entered:

```text
Invalid choice. Please try again.
```

Before exiting, the system saves the latest records and then ends the program.

---

## 🔄 Complete Project Workflow

```text
Start Program
      ↓
Load library.json
      ↓
Display Main Menu
      ↓
Choose an Operation
      ↓
Add / Search / Issue / Return / Display / Save
      ↓
Update Library Records
      ↓
Save Changes to JSON
      ↓
Return to Main Menu
      ↓
Exit
```

---

## 🧠 Python Concepts Practiced

This project helped me practice:

- Lists
- Dictionaries
- Functions
- `for` loops
- `while` loops
- Conditional statements
- User input
- String methods
- `.lower()`
- `f-strings`
- Dictionary access
- File handling
- JSON
- `try-except`
- `FileNotFoundError`
- Persistent data storage
- Menu-driven programming

---

## 📂 Project Structure

```text
Library-Management-System-Python/
│
├── Project_2.ipynb
├── library.json
└── README.md
```

### Files

**Project_2.ipynb**  
Contains the complete Python implementation and testing.

**library.json**  
Stores the library records permanently.

**README.md**  
Contains the project documentation.

---

## ▶️ How to Run the Project

1. Open `Project_2.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the cells from top to bottom.
3. Make sure `library.json` is in the same project folder.
4. Run:

```python
library_management_system()
```

5. Use the displayed menu to manage the library.

---

## 🎯 Learning Outcome

Through this project, I learned how to combine Python programming concepts to create a practical application.

The project gave me hands-on experience with:

- Creating reusable functions
- Working with lists and dictionaries
- Using loops and conditions
- Taking user input
- Searching and updating records
- Reading and writing files
- Using JSON for data storage
- Maintaining persistent data
- Building a menu-driven application

---

## 🔮 Future Improvements

Possible future improvements include:

- Member management
- Borrower records
- Issue and return dates
- Due-date tracking
- Fine calculation
- Book categories
- SQL database integration
- GUI interface
- Library reports and analytics

---

## 👩‍💻 Author

**Shrii**
Shriya Verma

 Data Analyst with Generative AI | August Batch

---

⭐ This project is part of my Python and Data Analytics learning journey.
