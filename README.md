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


****PROGRAM 4:  Implement passing object as function arguments and return object from function***

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
***To demonstrate the use of constructor with its types and destructor***

**AIM** :To demonstrate the use of constructors (default, parameterized, and copy constructors) and a destructor in C++.

**Algorithm**  :

1.Start the program.

2.Create a class MyClass with:

 -A data member int value.

 -A default constructor that initializes value to 0 and prints a message.

 -A parameterized constructor that initializes value to a given parameter and prints a message.

 -A copy constructor that initializes an object using another object of the same class and prints a message.

 -A destructor that displays a message when an object is destroyed.

3.In the main() function:

  -Create obj1 → calls the default constructor.


  -Create obj2 → calls the parameterized constructor with argument 10.


  -Create obj3 → calls the copy constructor, copying obj2.

4.When the program ends, destructors are automatically called for each object in reverse order of creation.

5.End program.


***SOURCE CODE***:
#include <iostream>
using namespace std;

class MyClass {
public:
    int value;

    // Default Constructor
    MyClass() {
        value = 0;
        cout << "Default Constructor Called. Value: " << value << endl;
    }

    // Parameterized Constructor
    MyClass(int val) {
        value = val;
        cout << "Parameterized Constructor Called. Value: " << value << endl;
    }

    // Copy Constructor
    MyClass(const MyClass& other) {
        value = other.value;
        cout << "Copy Constructor Called. Value: " << value << endl;
    }

    // Destructor
    ~MyClass() {
        cout << "Destructor Called for object with value: " << value << endl;
    }
};

int main() {
    // Calling Default Constructor
    MyClass obj1;

    // Calling Parameterized Constructor
    MyClass obj2(10);

    // Calling Copy Constructor
    MyClass obj3 = obj2;

    return 0; // Destructors will be called automatically
}


***SAMPLE Output***:
Default Constructor Called. Value: 0
Parameterized Constructor Called. Value: 10
Copy Constructor Called. Value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 0


**Result**:
The program successfully demonstrates the use of:

     -Default constructor (for obj1)

     -Parameterized constructor (for obj2)

    -Copy constructor (for obj3)

    -Destructor (automatically called when objects go out of scope)

It shows the order of constructor and destructor calls, confirming correct object creation and destruction in C++.



**PROGRAM 6** :
***Illustrate the use of static data member and static member function***

**AIM** :
        To illustrate the use of static data member and static member function in a C++ class.

**Algorithm** :
1.Start the program.

2.Define a class Car with:

    -A static data member carCount to keep track of the number of Car objects created.

    -A constructor that increments carCount every time a new object is created.

    -A non-static member function displayCarInfo() to display a simple message.

    -Define and initialize the static data member carCount outside the class using the scope resolution operator ::.


3.In the main() function:

   -Create multiple Car objects (car1, car2, car3).

   -Display the total number of cars created using the class name (Car::carCount).

4.End program.



 **Program 7:**
#include <iostream>
using namespace std;

class Car {
public:
    static int carCount; // Static data member to count cars

    // Constructor
    Car() {
        carCount++; // Increment count when a new car object is created
    }

    void displayCarInfo() {
        cout << "This is a car object." << endl;
    }

    // Static member function to display total cars
    static void displayCount() {
        cout << "Total cars created: " << carCount << endl;
    }
};

// Initialize static data member outside the class
int Car::carCount = 0;

int main() {
    Car car1;
    Car car2;
    Car car3;

    // Accessing static member through class name
    Car::displayCount();

    return 0;
}


**SAMPLE OUTPUT**:
Total cars created: 3


 **Result**:
The static data member carCount is shared by all objects of the class.

    -Each time a new Car object is created, the counter increases.

    -The static member function displayCount() can be called without creating an object, using the class name (Car::displayCount()).

Thus, the program successfully demonstrates the use of static data members and static member functions in C++.


**PROGRAM 8** :
***Illustrate the memory management operator***
**8(A).Allocating and deallocating a single variable.**

**AIM** :
         To demonstrate how to allocate and deallocate memory dynamically for a single variable using the new and delete operators in C++.

 **Algorithm:**

**1.** Start the program.

**2.** Declare a pointer variable ptr_int of type int.
      
**3.** Use the new operator to allocate memory dynamically for a single integer and initialize it with the value 10.
      int* ptr_int = new int(10);

**4.** Display the value stored in the dynamically allocated memory using dereferencing.
    std::cout << *ptr_int;

**5.** Deallocate the memory using the delete operator to prevent memory leaks:
          delete ptr_int;

**6.** Set the pointer to nullptr to avoid dangling pointers:
          ptr_int = nullptr;
          
**7.** End the program


**SOURCE CODE** :
#include <iostream>
using namespace std;

int main() {
    // Dynamically allocate memory for an integer and initialize it to 10
    int* ptr_int = new int(10);

    // Print the value stored at the allocated address
    cout << "Value of dynamically allocated integer: " << *ptr_int << endl;

    // Deallocate the memory to prevent a memory leak
    delete ptr_int;

    // Set the pointer to nullptr after deletion (best practice)
    ptr_int = nullptr;

    return 0;
}

**SAMPLE OUTPUT** :
        Value of dynamically allocated integer: 10
**Result:**

   -The program successfully demonstrates dynamic memory allocation and deallocation for a single variable using new and delete.

   -Memory is safely released, and the pointer is set to nullptr to avoid dangling references — following best programming practices in C++.


**8(b). Allocating and deallocating a dynamic array.**
**AIM** :
To demonstrate how to allocate and deallocate a dynamic array in C++ using the new[] and delete[] operators.

**Algorithm:**
**1.** Start the program.

**2.** Ask the user to input the number of elements for the array.

**3.** Use the new operator to dynamically allocate memory for an array of integers of the specified size:
      int* dynamic_array = new int[size];

**4.** Input elements from the user and store them in the array using a loop.

**5.** Display the array elements using another loop.

**6.** Use the delete[] operator to deallocate the memory used by the array:
delete[] dynamic_array;

**7.** Set the pointer to nullptr to prevent it from becoming a dangling pointer.

**8.** End the program.



 **SOURCE CODE**:
#include <iostream>
using namespace std;

int main() {
    int size;
    cout << "Enter the number of elements for the dynamic array: ";
    cin >> size;

    // Dynamically allocate memory for an array of integers
    int* dynamic_array = new int[size];

    // Read values into the array
    cout << "Enter " << size << " integer values:" << endl;
    for (int i = 0; i < size; i++) {
        cin >> dynamic_array[i];
    }

    // Print the array elements
    cout << "The elements of the dynamic array are: ";
    for (int i = 0; i < size; i++) {
        cout << dynamic_array[i] << " ";
    }
    cout << endl;

    // Deallocate the entire array
    delete[] dynamic_array;
    dynamic_array = nullptr;

    return 0;
}


 **SAMPLE INPUT & OUTPUT:**
**Input:**
Enter the number of elements for the dynamic array: 5
Enter 5 integer values:
10 20 30 40 50

**Output:**
The elements of the dynamic array are: 10 20 30 40 50


**RESULT** :

 **-** The program successfully demonstrates how to dynamically allocate memory for an array at runtime using new[].

**-** It also shows the proper way to free the allocated memory using delete[] to prevent memory leaks.

**-** This is an essential technique in dynamic memory management in C++.


**8(c).Dynamic object creation with constructors and destructors.**

**Aim:**
    To demonstrate dynamic object creation using constructors and destructors in C++.

 **Algorithm:**

**1.** Start the program.

**2.** Define a class Box with:

**3.** A constructor that initializes the length and displays a message when a box is created.


**4.** A destructor that displays a message when a box is destroyed.

**5.** In the main() function:

**-**  Dynamically create a single Box object using the new operator.

**-** Delete that object using the delete operator to call its destructor.

 **-** Dynamically create an array of Box objects using new[].

**-** Delete that array using delete[], which calls destructors for all array elements in reverse order.

**6.** End the program.


 **SOURCE CODE**:

#include <iostream>
using namespace std;

class Box {
public:
    // Constructor
    Box(int length) {
        this->length = length;
        cout << "Constructor for a box of length " << length << " is called." << endl;
    }

    // Destructor
    ~Box() {
        cout << "Destructor for a box of length " << length << " is called." << endl;
    }

private:
    int length;
};

int main() {
    // Create a single Box object dynamically
    Box* myBox = new Box(5);

    // Deallocate the object, which calls the destructor
    delete myBox;
    myBox = nullptr;

    // Create a dynamic array of Box objects
    Box* boxArray = new Box[3]{Box(1), Box(2), Box(3)};

    // Deallocate the array, calling the destructor for each element
    delete[] boxArray;
    boxArray = nullptr;

    return 0;
}

**SAMPLE OUTPUT** :
Constructor for a box of length 5 is called.
Destructor for a box of length 5 is called.
Constructor for a box of length 1 is called.
Constructor for a box of length 2 is called.
Constructor for a box of length 3 is called.
Destructor for a box of length 3 is called.
Destructor for a box of length 2 is called.
Destructor for a box of length 1 is called.


**RESULT** :
**1.** The program successfully demonstrates dynamic object creation and destruction using:

 **-** new and delete (for single objects)

 **-** new[] and delete[] (for arrays of objects)


**2.** It shows how constructors and destructors automatically manage resource initialization and cleanup in C++.


**8(d) Illustrative Program** :

**Aim:**
To illustrate the use of dynamic memory allocation and deallocation for both a single variable and an array using new, delete, new[], and delete[] in C++.

 **Algorithm:**

**1.** Start the program.

**2.** Dynamically allocate memory for a single integer using new:
     int* singleInt = new int;

  **-** Assign the value 25 to it.

  **-** Display the value using dereferencing.

**3.** Dynamically allocate memory for an integer array of size 3 using new[]:
int* dynamicArray = new int[size];

   **-** Assign values to each element of the array (e.g., 10, 20, 30).

   **-** Display the elements of the array.

 **4.** Deallocate the memory:

  **-** Use delete to free the single integer.

  **-** Use delete[] to free the dynamically allocated array.

  **-** Set both pointers to nullptr (to avoid dangling pointers).

 **5.** End the program.

**SOURCE CODE** :
#include <iostream>
using namespace std;

int main() {
    // Dynamic allocation for a single integer
    int* singleInt = new int;
    *singleInt = 25;
    cout << "Value of singleInt: " << *singleInt << endl;

    // Dynamic allocation for an array of integers
    int size = 3;
    int* dynamicArray = new int[size];
    for (int i = 0; i < size; ++i) {
        dynamicArray[i] = (i + 1) * 10;
    }

    // Display array elements
    cout << "Elements of dynamicArray: ";
    for (int i = 0; i < size; ++i) {
        cout << dynamicArray[i] << " ";
    }
    cout << endl;

    // Deallocate memory
    delete singleInt;
    singleInt = nullptr; // Best practice

    delete[] dynamicArray;
    dynamicArray = nullptr; // Best practice

    return 0;
}

**SAMPLE OUTPUT** :
Value of singleInt: 25
Elements of dynamicArray: 10 20 30


**RESULT** :
The program successfully demonstrates:

 **-** Dynamic allocation and deallocation of a single variable and an array.

 **-** Proper memory management using new, delete, new[], and delete[].

 **-** Safe programming practices by setting pointers to nullptr after deletion.


**PROGRAM 9** :

**9.Illustrate the use of friend class and friend function**
 **Aim:** :
To illustrate the use of a friend class in C++, which allows one class to access the private and protected members of another class.

**Algorithm:** :

**1.** Start the program.

**2.** Define a class Geeks with:

     **-** A private data member private_variable.

     **-** A protected data member protected_variable.

     **-** A constructor to initialize both variables.

     **-** A friend class declaration (friend class GFG;), allowing the class GFG to access its private and protected members.

**2.** Define another class GFG that:

**-** Contains a member function display() which takes a Geeks object as a parameter.

**-** Accesses and displays the private and protected data of the Geeks class.

**3.** In the main() function:

  **-** Create an object of Geeks.

  **-** Create an object of GFG.

  **-** Call the display() function of GFG, passing the Geeks object.

**4.** End the program.



**SOURCE CODE** :
#include <iostream>
using namespace std;

class Geeks {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    Geeks() {
        private_variable = 10;
        protected_variable = 99;
    }

    // Friend class declaration
    friend class GFG;
};

// Class GFG is declared as a friend of Geeks
class GFG {
public:
    void display(Geeks& t) {
        cout << "The value of Private Variable = " << t.private_variable << endl;
        cout << "The value of Protected Variable = " << t.protected_variable << endl;
    }
};

int main() {
    Geeks obj;
    GFG obj2;
    obj2.display(obj);
    return 0;
}


**SAMPLE OUTPUT** :
The value of Private Variable = 10
The value of Protected Variable = 99



**RESULT** :
The program successfully demonstrates the concept of a friend class in C++, showing that a friend class can access private and protected data members of another class.



**9(B).Friend Function in C++**

 **Aim:**
To demonstrate the use of a friend function in C++, allowing a non-member function to access the private and protected members of a class.

**Algorithm:**

**1.** Start the program.

**2.** Define a class base with:

**-** A private data member private_variable.

**-** A protected data member protected_variable.

**-** A constructor that initializes both variables.

**-** A friend function declaration to allow an external function to access its private and protected members.

**3.** Define a global function friendFunction() outside the class:

**-** It takes an object of type base as an argument.

**-** It directly accesses and displays the private and protected members of the base class.

**4.** In the main() function:

**-** Create an object of base.

**-** Call the friendFunction() and pass the object.

**5.** End the program.



**SOURCE CODE** :
#include <iostream>
using namespace std;

class base {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    base() {
        private_variable = 10;
        protected_variable = 99;
    }

    // Friend function declaration
    friend void friendFunction(base& obj);
};

// Friend function definition
void friendFunction(base& obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable << endl;
}

int main() {
    base object1;
    friendFunction(object1);
    return 0;
}


**SAMPLE OUTPUT** :
Private Variable: 10
Protected Variable: 99

**RESULT** :
The program successfully demonstrates the concept of a friend function in C++.
It shows that a friend function can access private and protected members of a class even though it is not a member of that class.



***9(c) Member Function of Another Class as Friend Function***
**AIM** :
To illustrate how a member function of one class can be declared as a friend function of another class in C++.

 **Algorithm:** 

**1.** Start the program.

**2.** Forward declare the class base before defining class GFG, since GFG will contain a function that takes a base object as a parameter.

**3.** Define class GFG:

**-** Declare a member function GFG_Function(base& obj) that will later access the private and protected members of base.

**4.** Define class base:

 **-** Include private and protected data members.

 **-** Initialize them in the constructor.

 **-** Declare the function GFG::GFG_Function(base&) as a friend, allowing it to access base’s private and protected members.

**5.** Define the function GFG::GFG_Function() outside both classes:

**-** Inside the function, access and display the private and protected members of the base object.

**6.** In the main() function:

 **-** Create objects of base and GFG.

 **-** Call GFG_Function() using the GFG object, passing the base object as an argument.

**7.** End the program.

**SOURCE CODE :** 
#include <iostream>
using namespace std;

// Forward declaration of class base
class base;

// Another class in which function is declared
class GFG {
public:
    void GFG_Function(base& obj);
};

// Base class declaring a friend function of another class
class base {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    base() {
        private_variable = 10;
        protected_variable = 99;
    }

    // Friend function declaration
    friend void GFG::GFG_Function(base&);
};

// Friend function definition
void GFG::GFG_Function(base& obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable << endl;
}

int main() {
    base object1;
    GFG object2;
    object2.GFG_Function(object1);

    return 0;
}

**SAMPLE OUTPUT** :
Private Variable: 10
Protected Variable: 99


**RESULT** :
The program successfully demonstrates how a member function of one class (GFG::GFG_Function) can be made a friend function of another class (base), enabling controlled access to private and protected data members between classes in C++.


**PROGRAM 10 : To implement the use of unary operator overloading**      

**10(a).Overloading the unary minus (-) operator**

**Aim:** :To implement the unary operator overloading in C++ by overloading the unary minus (-) operator for a user-defined class.

**Algorithm:**

**1.** Start the program.

**1.** Define a class Point with:

**-** Two private data members x and y.

**-** A constructor to initialize these coordinates.

**-** A member function operator-() to overload the unary minus operator.

**3.** A display function to show the values of x and y.

**-** In the operator-() function:

**-** Return a new Point object with the negated values of x and y.

**4.** In the main() function:

**-** Create a Point object p1 with coordinates (10, -20).

**-** Use the statement p2 = -p1; to invoke the overloaded operator.

**-** Display both p1 and p2 using the display() function.

**5.** End the program.

**SOURCE CODE** :
#include <iostream>
using namespace std;

class Point {
private:
    int x, y;

public:
    // Constructor to initialize the point
    Point(int x_coord = 0, int y_coord = 0) {
        x = x_coord;
        y = y_coord;
    }

    // Overload the unary minus operator as a member function
    Point operator-() {
        return Point(-x, -y);
    }

    // Function to display the point's coordinates
    void display() {
        cout << "Point(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    Point p1(10, -20);
    Point p2 = -p1; // Calls the overloaded operator-()
    
    cout << "Original point p1: ";
    p1.display();
    
    cout << "Negated point p2: ";
    p2.display();
    
    return 0;
}

**SAMPLE OUTPUT** :
Original point p1: Point(10, -20)
Negated point p2: Point(-10, 20)


**RESULT** :
The program successfully demonstrates unary operator overloading by redefining the unary minus (-) operator for a class.
When applied to a Point object, it creates a new object with the negated coordinates of the original




**Aim:**

To implement unary operator overloading using a friend function in C++, allowing the unary minus (-) operator to access private members of a class.

 **Algorithm:**

**1.** Start the program.

**2.** Define a class Point with:

**-** Private data members x and y.

**-** A constructor to initialize the coordinates.

**-** A friend function declaration for the unary minus operator.

**-** A display function to print the coordinates.

**3.** Define the friend function operator-() outside the class:

**-** The function should take a const Point& as input.

**-** Return a new Point object with negated x and y values.

**4.** In main() function:

**-** Create a Point object p1.

**-** Apply the unary minus operator to create p2 using the friend function.

**-** Display both p1 and p2.

**5.** End the program.

**SOURCE CODE** :
#include <iostream>
using namespace std;

class Point {
private:
    int x, y;

public:
    // Constructor
    Point(int x_coord = 0, int y_coord = 0) {
        x = x_coord;
        y = y_coord;
    }

    // Declare friend function for unary minus operator
    friend Point operator-(const Point& p);

    // Function to display coordinates
    void display() {
        cout << "Point(" << x << ", " << y << ")" << endl;
    }
};

// Define the friend function outside the class
Point operator-(const Point& p) {
    return Point(-p.x, -p.y);
}

int main() {
    Point p1(10, -20);
    Point p2 = -p1; // Calls the friend operator-()

    cout << "Original point p1: ";
    p1.display();

    cout << "Negated point p2: ";
    p2.display();

    return 0; // Corrected capitalization
}

**SAMPLE OUTPUT** :
Original point p1: Point(10, -20)
Negated point p2: Point(-10, 20)


**RESULT** :

The program demonstrates unary minus operator overloading using a friend function, producing a new object with negated coordinates while keeping the original object unchanged.


