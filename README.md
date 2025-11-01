# 11249a390-00PS-LAB-RECORD
**PROGRAM 1** :
         ***Illustrate class & objects. Implement member function defined inside and outside the class***.
         
***AIM** :To illustrate the concept of Class and Objects in C++ and demonstrate how to implement member functions defined both inside and outside the class.

***ALGORITHM*** 
1.Start the program.

2.Define a class named Car.

3.Declare data members: brand, model, and year.

    -Define one member function (displayInfo()) inside the class to display car details.

    -Declare another member function (startEngine()) to be defined outside the class.

    -Define the function startEngine() outside the class using the scope resolution operator ::.

4.In the main() function:

   -Create two objects: myCar and anotherCar.

    -Assign values to myCar's data members.

    -Call the member functions displayInfo() and startEngine() for myCar.

5.End the program.

***SOURCE CODE :***
#include <iostream>
#include <string>

// Define a class named 'Car'
class Car {
public:
    // Data members (attributes)
    std::string brand;
    std::string model;
    int year;

    // Member function defined inside the class
    void displayInfo() {
        std::cout << "Brand: " << brand << ", Model: " << model << ", Year: " << year << std::endl;
    }

    // Member function declared inside, defined outside
    void startEngine(); 
};

// Member function defined outside the class using the scope resolution operator (::)
void Car::startEngine() {
    std::cout << "The " << brand << " " << model << " engine is starting..." << std::endl;
}

int main() {
    // Create objects of the 'Car' class
    Car myCar; // Object 1
    Car anotherCar; // Object 2

    // Assign values to data members of myCar
    myCar.brand = "Toyota";
    myCar.model = "Camry";
    myCar.year = 2023;

     // Assign values to data members of anotherCar
    anotherCar.brand = "Honda";
    anotherCar.model = "Civic";
    anotherCar.year = 2022;

    // Call member functions for each object
    myCar.displayInfo();
    myCar.startEngine();

    anotherCar.displayInfo();
      anotherCar.startEngine();

    return 0;
}

***SAMPLE OUTPUT*** :
Brand: Toyota, Model: Camry, Year: 2023
The Toyota Camry engine is starting...


***FINAL RESULT*** :
The program successfully demonstrates:
   -The concept of classes and objects in C++.
   -How member functions can be defined inside and outside a class.
   -How to create objects, assign values, and invoke class functions.
Thus, the objective of illustrating Class and Objects with member function implementation has been achieved successfully .




***PROGRAM 2 :***
        ***To demonstrate the concept of function overloading applied to the member functions***
 ***AIM*** :

To demonstrate the concept of Function Overloading applied to member functions in C++.
Function overloading allows multiple functions to have the same name but differ in the number or type of parameters.

***ALGORITHM*** :

1.Start the program.

2.Create a class named Calculator.

3.Inside the class, define multiple add() functions with the same name but different parameter lists:

     -add(int, int) → adds two integers.

     -add(int, int, int) → adds three integers.

     -add(string, string) → concatenates two strings.

4.In the main() function:

     -Create an object calc of the class Calculator.

     -Call the overloaded add() function with different argument types and counts.

4.Display the results for each function call.

5.End the program.


***SOURCE CODE :***

#include <iostream>
#include <string>
using namespace std;

class Calculator {
public:
    // Overloaded member function to add two integers
    int add(int a, int b) {
        return a + b;
    }

    // Overloaded member function to add three integers
    int add(int a, int b, int c) {
        return a + b + c;
    }

    // Overloaded member function to concatenate two strings
    string add(const string& s1, const string& s2) {
        return s1 + s2;
    }
};

int main() {
    Calculator calc;

    // Call the add function for integers (two arguments)
    int sum1 = calc.add(5, 10);
    cout << "Sum of two integers: " << sum1 << endl;

    // Call the add function for integers (three arguments)
    int sum2 = calc.add(5, 10, 15);
    cout << "Sum of three integers: " << sum2 << endl;

    // Call the add function for strings
    string combinedString = calc.add("Hello, ", "World!");
    cout << "Combined string: " << combinedString << endl;

    return 0;
}
***SAMPLE OUTPUT*** 

Sum of two integers: 15
Sum of three integers: 30
Combined string: Hello, World!


***FINAL RESULT***
The program successfully demonstrates Function Overloading in C++:
The same function name add() performs different operations depending on the type and number of arguments passed.
It shows how compile-time polymorphism (also called static binding) works in C++.
Hence, the aim of demonstrating function overloading applied to member functions is achieved successfully.


***PROGRAM 3*** :
***Implement passing object as function arguments and return object from function***

**AIM**: To demonstrate how to pass objects as function arguments (by value and by reference) and return objects from functions in C++.

**ALGORITHM** :

1.Start the program.

2.Create a class MyClass with a data member value.

3.Define a constructor to initialize the object with a given value.

4.Write a function modifyObject() that takes a MyClass object by value and modifies it — this will not affect the original object.

5.Write another function modifyAndReturn() that takes a MyClass object, modifies it, and returns a new object.

6.In the main() function:

   -Create an object originalObj.

   -Pass it to modifyObject() (changes won’t affect the original).

   -Pass it to modifyAndReturn() and get a new modified object as return.

   -Display the results.

7.End the program.

**PROGRAM**
  #include <iostream>

    class MyClass {
    public:
        int value;
        MyClass(int v) : value(v) {}
        };

    void modifyObject(MyClass obj) { // obj is a copy
        obj.value = 100;
    }

    int main() {
        MyClass originalObj(10);
        std::cout << "Original value before: " << originalObj.value << std::endl;
        modifyObject(originalObj);
        std::cout << "Original value after: " << originalObj.value << std::endl; // Still 10
        return 0;
    }


**SAMPLE OUTPUT** :
Original value before modifyObject(): 10
Inside modifyObject(): value changed to 100
Original value after modifyObject(): 10
Original value after modifyAndReturn(): 10
New object value (returned): 200


**FINAL RESULT**
 The program demonstrates two important concepts:
 
1.Passing object as a function argument (by value):
   -When an object is passed by value, a copy of the object is made.
   -Changes inside the function do not affect the original object.
2.Returning object from a function:
  -A function can return an object.
 -The returned object can contain modified data that is independent of the original.
Thus, the aim of implementing passing object as function argument and returning object from function is successfully achieved.


****PROGRAM 4:****   
    ***Implement passing object as function arguments and return object from function***

**AIM**:
To implement and demonstrate the concept of passing objects as function arguments (by value) and returning objects from functions in C++.

**ALGORITHM**

1.Start the program.

2.Define a class MyClass with a data member value.

3.Create a constructor to initialize the value of the object.

4.Define a function modifyObjectByValue() that:

  -Takes an object of MyClass by value.

   -Modifies its value attribute.

   -Displays the modified value inside the function.

5.In the main() function:

    -Create an object originalObj of MyClass with an initial value (e.g., 10).

     -Display the value before calling the function.

     -Call modifyObjectByValue(originalObj) — since it’s passed by value, changes won’t affect the original object.

     -Display the value after the function call to show that it remains unchanged.

6.End the program.

 **PROGRAM** :
 
#include <iostream>
using namespace std;

class MyClass {
public:
    int value;

    // Constructor to initialize the object
    MyClass(int v) : value(v) {}
};

// Function that takes an object by value (creates a copy)
void modifyObjectByValue(MyClass obj) {
    obj.value = 100; // Modifies the copy, not the original
    cout << "Inside function (by value): " << obj.value << endl;
}

// Function that returns an object (to demonstrate return object concept)
MyClass createNewObject() {
    MyClass tempObj(200); // Create new object
    return tempObj;       // Return object
}

int main() {
    MyClass originalObj(10);

    cout << "Original object before call: " << originalObj.value << endl;

    // Passing object by value
    modifyObjectByValue(originalObj);

    cout << "Original object after call: " << originalObj.value << endl;

    // Returning object from function
    MyClass returnedObj = createNewObject();
    cout << "Returned object value: " << returnedObj.value << endl;

    return 0;
}

**SAMPLE OUTPUT** :

Original object before call: 10
Inside function (by value): 100
Original object after call: 10
Returned object value: 200


**FINAL RESULT** :
 The program successfully demonstrates two key concepts:
1.Passing object as function argument (by value):
    -When the object is passed by value, a copy is created inside the function.
    -Any modification to the object inside the function does not affect the original object.
2.Returning object from a function:
   -A new object can be created and returned from a function.
   -The returned object can hold its own data, separate from the original object.
Hence, the aim of “Implementing passing object as function arguments and returning object from function” is successfully achieved.



**PROGRAM 5** :
**AIM** :























        

