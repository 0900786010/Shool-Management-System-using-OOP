# Shool-Management-System-using-OOP
#include <iostream>
#include <string>

using namespace std;

// Base class for the school
class School {
public:
    virtual void insert() = 0;
    virtual void display() const = 0;
};

// Derived class for student information
class Student : public School {
public:
    int id;
    string name;
    int age;

    void insert() override {
        cout << "Enter student ID: ";
        cin >> id;
        cin.ignore(); // Ignore leftover newline
        cout << "Enter student name: ";
        getline(cin, name);
        cout << "Enter student age: ";
        cin >> age;
        cin.ignore(); // Ignore leftover newline
    }

    void display() const override {
        cout << "Student Record:\n";
        cout << "ID: " << id << "\nName: " << name << "\nAge: " << age << endl;
    }
};

// Derived class for teacher information
class Teacher : public School {
public:
    int id;
    string name;
    string subject;

    void insert() override {
        cout << "Enter teacher ID: ";
        cin >> id;
        cin.ignore(); // Ignore leftover newline
        cout << "Enter teacher name: ";
        getline(cin, name);
        cout << "Enter subject: ";
        getline(cin, subject);
    }

    void display() const override {
        cout << "Teacher Record:\n";
        cout << "ID: " << id << "\nName: " << name << "\nSubject: " << subject << endl;
    }
};

// Derived class for staff information
class Staff : public School {
public:
    int id;
    string name;
    string position;

    void insert() override {
        cout << "Enter staff ID: ";
        cin >> id;
        cin.ignore(); // Ignore leftover newline
        cout << "Enter staff name: ";
        getline(cin, name);
        cout << "Enter position: ";
        getline(cin, position);
    }

    void display() const override {
        cout << "Staff Record:\n";
        cout << "ID: " << id << "\nName: " << name << "\nPosition: " << position << endl;
    }
};

// Main function
int main() {
    const int MAX_RECORDS = 100;
    School* records[MAX_RECORDS];
    int recordCount = 0;
    int choice;

    cout << "School Management System\n";
    do {
        cout << "\n1. Add Student\n2. Add Teacher\n3. Add Staff\n4. Display All\n5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        School* record = nullptr;
        switch (choice) {
            case 1:
                if (recordCount < MAX_RECORDS) {
                    record = new Student();
                } else {
                    cout << "No more space to add records.\n";
                }
                break;
            case 2:
                if (recordCount < MAX_RECORDS) {
                    record = new Teacher();
                } else {
                    cout << "No more space to add records.\n";
                }
                break;
            case 3:
                if (recordCount < MAX_RECORDS) {
                    record = new Staff();
                } else {
                    cout << "No more space to add records.\n";
                }
                break;
            case 4:
                if (recordCount == 0) {
                    cout << "No records to display.\n";
                } else {
                    for (int i = 0; i < recordCount; ++i) {
                        records[i]->display();
                        cout << "--------------------------------\n";
                    }
                }
                break;
            case 5:
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice! Please try again.\n";
                break;
        }

        if (record && recordCount < MAX_RECORDS) {
            record->insert();
            records[recordCount++] = record;
        }

    } while (choice != 5);

    // Clean up dynamically allocated memory
    for (int i = 0; i < recordCount; ++i) {
        delete records[i];
    }

    return 0;
}
