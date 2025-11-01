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
