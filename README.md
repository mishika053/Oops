# Oops

#include <iostream>
#include <string>
using namespace std;

// Parent Class
class Employee {
public:
    int employeeId;
    string employeeName;

    // Function to enter basic employee details
    void getBasicDetails() {
        cout << "Enter employee ID: ";
        cin >> employeeId;

        cout << "Enter employee name: ";
        getline(cin >> ws, employeeName);
    }

    // Function to display basic employee details
    void showBasicDetails() {
        cout << "Employee ID: " << employeeId << endl;
        cout << "Employee Name: " << employeeName << endl;
    }
};

// Child Class (Single Inheritance)
class PermanentEmployee : public Employee {
public:
    string department;
    double monthlySalary;

    // Function to enter job details
    void getJobDetails() {
        cout << "Enter department: ";
        getline(cin >> ws, department);

        cout << "Enter monthly salary: ";
        cin >> monthlySalary;
    }

    // Function to display all employee details
    void showAllDetails() {
        cout << "\n--- Employee Details ---" << endl;

        // Calling inherited function of parent class
        showBasicDetails();

        cout << "Department: " << department << endl;
        cout << "Monthly Salary: Rs. " << monthlySalary << endl;
    }
};

// Main Function
int main() {
    PermanentEmployee emp;

    cout << "===== EMPLOYEE DETAILS SYSTEM =====" << endl;

    emp.getBasicDetails();
    emp.getJobDetails();

    emp.showAllDetails();

    return 0;
}
