#include <iostream>
#include <string>
using namespace std;
class Student {
private:
    string name;
public:
    Student(const string& name) : name(name) {}
    string getName() const {
        return name;
    }
};

class Course {
public:
    Course(const string& name) : name(name), studentCount(0) {}
    Course(const Course& other) : name(other.name), studentCount(other.studentCount) {
        for (int i = 0; i < studentCount; ++i) {
            students[i] = other.students[i];
        }
    }

    void addStudent(const string& studentName) {
        if (studentCount < MaxStudents) {
            students[studentCount++] = Student(studentName);
        }
    }

    void dropStudent(const string& studentName) {
        for (int i = 0; i < studentCount; ++i) {
            if (students[i].getName() == studentName) {
                for (int j = i; j < studentCount - 1; ++j) {
                    students[j] = students[j + 1];
                }
                studentCount--;
                return;
            }
        }
    }

    void printStudents() {
        cout << "Students in " << name << ":\n";
        for (int i = 0; i < studentCount; ++i) {
            cout << students[i].getName() << endl;
        }
    }
private:
    static const int MaxStudents = 100;
    string name;
    Student students[MaxStudents];
    int studentCount;
};

int main() {
    Course math("Math");
    math.addStudent("Ali");
    math.addStudent("Ana");
    math.addStudent("Sara");
    Course copyMath = math;
    math.dropStudent("Ana");
    cout << "Original Math Course:" << endl;
    math.printStudents();
    cout << "\nCopied Math Course:" << endl;
    copyMath.printStudents();
    return 0;
}
