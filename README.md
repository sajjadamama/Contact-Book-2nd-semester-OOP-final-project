# 📒 Contact Book Application
**Student ID:** 23F-6014  Amama Sajjad
**Course:** Object-Oriented Programming  
**Language:** C++

A console-based Contact Book application built in C++ using OOP principles. It supports adding, searching, sorting, grouping, and persisting contacts to a file.

---

## Features

- **Add Contacts** — Store first name, last name, phone number, email, and full address
- **Search** — Find contacts by name, phone number, address, or any single keyword
- **Sort** — Print all contacts sorted by first name or last name
- **Merge Duplicates** — Detect and merge duplicate contacts
- **Groups** — Create named groups, add/remove contacts, and search within groups
- **File I/O** — Save contacts to a file and load them back across sessions
- **Contact Count** — Display total number of contacts in the book

---

## Project Structure

```
CONTACT_BOOK_PROJECT_23F-6014/
├── main.cpp            # Entry point; menu-driven interface
├── contact.h/.cpp      # Contact class (name, phone, email, address, ID, search tracking)
├── address.h/.cpp      # Address class (house, street, city, country)
├── contactbook.h/.cpp  # ContactBook class (dynamic array, sort, search, file I/O)
├── Group.h/.cpp        # Group class (named groups of contacts)
├── Search.h/.cpp       # SearchHistory class (tracks search timestamps and inputs)
├── object.h/.cpp       # Objects class (manages search history list)
├── dataxyz             # Default data file (auto-used on contact add)
├── dataxyz.txt         # Sample/test contact data
└── Project7.sln        # Visual Studio solution file
```

---

## How to Run

### Option 1 — Visual Studio (Windows, Recommended)

1. Open `Project7.sln` in **Visual Studio 2019 or later**
2. Set the build configuration to **Debug** or **Release**
3. Press **Ctrl+F5** to build and run without debugging

---

### Option 2 — g++ (Command Line, Windows/Linux/macOS)

Make sure you have `g++` installed (comes with MinGW on Windows, or GCC on Linux/macOS).

```bash
g++ -std=c++17 -o contactbook main.cpp contact.cpp address.cpp contactbook.cpp Group.cpp Search.cpp object.cpp
```

Then run it:

```bash
# Windows
contactbook.exe

# Linux / macOS
./contactbook
```

> **Note:** The app uses `system("cls")` and `system("pause")` in a few places, which are Windows-only calls. On Linux/macOS these will silently do nothing (the program will still work correctly).

---

## Usage

When the program starts, a menu is displayed:

```
-------------------- WELCOME TO THE CONTACT BOOK APP --------------------
Menu
[1]  Create a contacts list
[2]  Add new contact
[3]  Search contact by name
[4]  Search contact by phone number
[5]  Search contact by address
[6]  Print all contacts sorted by name
[7]  Merge duplicate contacts
[8]  Total contacts
[9]  Save contacts to a file
[10] Load contacts from a file
[11] Search By Single Word
[12] Open Group Menu
[13] Exit
```

Enter the number corresponding to your choice and follow the prompts.

### Saving & Loading
- Contacts are **automatically saved** to `dataxyz` whenever a new contact is added (Option 2).
- Use **Option 9** to save to a custom filename.
- Use **Option 10** to load contacts from any saved file.

### Phone Number Validation
Phone numbers must be at least **11 digits** — the app will re-prompt if the input is too short.

---

## Classes Overview

| Class | Responsibility |
|---|---|
| `Address` | Stores and manages house, street, city, country |
| `Contact` | Stores contact info; tracks search count and timestamp |
| `ContactBook` | Dynamic array of contacts; handles add, search, sort, file I/O |
| `Group` | Named group containing a `ContactBook`; supports add/remove/search |
| `SearchHistory` | Records a single search event (input string + timestamp) |
| `Objects` | Manages the search history list |

---

## Requirements

- C++17 or later
- Visual Studio 2019+ **or** g++ / MinGW
- No external libraries required
