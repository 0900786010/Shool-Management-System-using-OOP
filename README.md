📌 School Management System (C++)

This project is a console-based School Management System built in C++, designed to manage and organize essential school records. It provides a simple yet effective way to store and display information about students, teachers, and staff members.

✨ Features

Add Student Records: Enter and store student ID, name, and age.

Add Teacher Records: Manage teacher ID, name, and subject specialization.

Add Staff Records: Maintain staff ID, name, and job position.

Display Records: View all stored records with clear formatting.

Menu-Driven System: Easy-to-use interface with options to insert or display data.

Dynamic Memory Management: Uses polymorphism and pointers for efficient record handling.

🛠️ Technical Details

Implemented using Object-Oriented Programming (OOP) concepts such as inheritance, polymorphism, and virtual functions.

Base class: School (abstract class with virtual methods).

Derived classes: Student, Teacher, and Staff, each handling specific attributes and methods.

Stores records dynamically in an array of pointers (School* records[MAX_RECORDS]).

Supports up to 100 entries in one run.

Includes memory cleanup to prevent memory leaks.

🎯 Purpose

This project is ideal for beginners learning C++ and OOP principles. It demonstrates how to design a structured system using inheritance, abstract classes, and polymorphism, while solving a practical real-world problem.
