# C-important-concept-

1)  Structure (struct)
A structure is a user-defined data type used to store different types of data in one unit.
Example:
Copy code
Cpp
struct Student {
    int id;
    float marks;
    char grade;
};
2) Structure Declaration vs Definition
  Declaration
Tells compiler that a struct exists.
Copy code
Cpp
struct Student;
✅ Definition
Creates members inside struct.
Copy code
Cpp
struct Student {
    int id;
    float marks;
};
3) Structure Variable
Copy code
Cpp
Student s1;
s1.id = 101;
4) Structure Members
The variables inside a structure are called structure members.
Example:
Copy code
Cpp
s1.id
s1.marks
5)  Accessing Structure Members (Dot Operator)
Used when you have a normal structure variable.
Copy code
Cpp
Student s1;
s1.id = 10;
👉 . is called member access operator.
6) Pointer to Structure (Arrow Operator)
When you use a pointer, use ->
Copy code
Cpp
Student s1;
Student *p = &s1;

p->id = 10;
👉 -> is called structure pointer member access operator
7) Nested Structure
A structure inside another structure is called nested structure.
Copy code
Cpp
struct Date {
    int day, month, year;
};

struct Student {
    int id;
    Date dob;
};
Access:
Copy code
Cpp
Student s;
s.dob.day = 5;
8)  Structure inside Structure (Nested Members)
Example:
Copy code
Cpp
struct A {
    int x;
};

struct B {
    A obj;
};
9) Size of Operator (sizeof)
Used to find memory size of data type or variable.
Copy code
Cpp
cout << sizeof(int);
cout << sizeof(Student);
⚡ Structure size depends on members + padding.
10)  Address Understanding (Pointer + &)
& gives the address of a variable.
Copy code
Cpp
int a = 5;
cout << &a;
Pointer stores address:
Copy code
Cpp
int *p = &a;
11)  Scope (Understanding Scope)
Scope means where a variable is accessible.
Types:
✅ Local Scope
Copy code
Cpp
void fun() {
   int x = 10; // only inside fun
}
✅ Global Scope
Copy code
Cpp
int x = 100; // accessible everywhere
12)  Structure Pointer Arithmetic
Pointer arithmetic means moving pointer in memory.
Example:
Copy code
Cpp
Student arr[3];
Student *p = arr;

p++; // moves to next Student
📌 p+1 jumps by sizeof(Student) bytes.
13)  Relationship Between Array, Pointer and Structure
Array name is a pointer to first element
Copy code
Cpp
int arr[5];
int *p = arr;
Same for structure array:
Copy code
Cpp
Student s[3];
Student *p = s;
Access:
Copy code
Cpp
(p+1)->id = 20;
14)  Looping in Structure Array
Copy code
Cpp
Student s[3];

for(int i=0; i<3; i++){
    cin >> s[i].id;
}
Using pointer:
Copy code
Cpp
Student *p = s;
for(int i=0; i<3; i++){
    cin >> (p+i)->id;
}
15)  Call By Value
Copy of variable is passed.
Original value does not change.
Copy code
Cpp
void change(int x){
    x = 50;
}
16)  Call By Reference (Using Reference in C++)
Original variable is passed.
Changes affect original.
Copy code
Cpp
void change(int &x){
    x = 50;
}
17)  Call By Reference (Using Pointer in C)
Copy code
Cpp
void change(int *x){
    *x = 50;
}
Call:
Copy code
Cpp
int a=10;
change(&a);
18)  Function with Structure (Call by Value)
Copy code
Cpp
void display(Student s){
    cout << s.id;
}
19)  Function with Structure (Call by Reference)
Using reference:
Copy code
Cpp
void update(Student &s){
    s.id = 99;
}
Using pointer:
Copy code
Cpp
void update(Student *s){
    s->id = 99;
}
20)  Function Pointer (Function Call Reference)
A function pointer stores address of a function.
Copy code
Cpp
int add(int a, int b){
    return a+b;
}

int (*fp)(int,int) = add;
cout << fp(2,3);
21)  Structure + Pointer + Function Example
Copy code
Cpp
struct Student{
    int id;
};

void setData(Student *s){
    s->id = 100;
}

int main(){
    Student s1;
    setData(&s1);
    cout << s1.id
  }
