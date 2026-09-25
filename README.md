# 📚 Library Management System

A Python-based **Library Management System** that allows users to manage books through a simple menu-driven interface.

The project uses **JSON for persistent storage**, so book records remain saved even after closing and reopening the program.

---

## 📌 Project Overview

This project was developed as part of my Python learning journey to practice applying programming concepts to a real-world use case.

The system allows users to:

- Add new books
- Search for books
- Issue books
- Return books
- Display available books
- Save and load records using JSON

---

## 🚀 Features

### 1. Add Books
Users can add a new book by entering:

- Book ID
- Book title
- Author name

New books are automatically saved to the JSON file.

### 2. Search Books
Users can search for a book by title.

The search is **case-insensitive**, making it easier to find books regardless of capitalization.

### 3. Issue Books
Users can issue a book using its Book ID.

When a book is issued:

```text
available = False
