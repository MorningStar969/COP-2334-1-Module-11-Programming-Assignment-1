# COP-2334-1-Module-11-Programming-Assignment-1
This is a GitHub repository link for the first Programming Assignment from Module 11.

// This program is used to determine the quatity of apple technology products that are in stock, what the price is, and the total price of the products after adding stock or selling.

// Include the header file
#include <iostream>
#include <string> // Include the string library
using namespace std; // Using standard namespace

class Item { // Create a class called Item
private: // Private access specifier
    string itemName; // Declare a string variable called itemName
    int itemID; // Declare an integer variable called itemID
    int quantity; // Declare an integer variable called quantity
    double price; // Declare a double variable called price
public: // Public access specifier
    Item(string name, int id, int qty, double p) { // Constructor with parameters
        itemName = name; // Set the value of itemName to name
        itemID = id; // Set the value of itemID to id
        quantity = qty; // Set the value of quantity to qty
        price = p; // Set the value of price to p
    }
    void AddStock(int qty) { // Function to add stock
        quantity += qty; // Add qty to quantity
    }
    void SellItem(int qty) { // Function to sell item
        if (quantity >= qty) { // If quantity is greater than or equal to qty.
            quantity -= qty; // Subtract qty from quantity
        } // End if statement
    } // End function
    double GetTotalValue() { // Function to get total value
        return quantity * price; // Return the product of quantity and price.
    }
    void Display() { // Function to display item details
        cout << "Item Details:" << endl; // Display the message "Item Details:"
        cout << "Item Name: " << itemName << endl; // Display the message "Item Name: " followed by the value of itemName.
        cout << "Item ID: " << itemID << endl; // Display the message "Item ID: " followed by the value of itemID.
        cout << "Quantity: " << quantity << endl; // Display the message "Quantity: " followed by the value of quantity.
        cout << "Price: $" << price << endl; // Display the message "Price: $" followed by the value of price.
        cout << "Total Value: $" << GetTotalValue() << endl; // Display the message "Total Value: $" followed by the value of GetTotalValue().
    } // End function
}; // End class

int main() { // Main function
    Item item1("MacBook Pro", 101, 10, 450.0); // Create an object of Item class with name "MacBook Pro", ID 101, quantity 10, and price 450.0.
    Item item2( "iPhone 16", 102, 5, 300.0); // Create an object of Item class with name "iPhone 16", ID 102, quantity 5, and price 300.0.
    Item item3("iPad 10th Generation", 103, 8, 150.0); // Create an object of Item class with name "iPad 10th Generation", ID 103, quantity 8, and price 150.0.
    item1.Display(); // Call the Display function of item1.
    cout << endl; // Display a new line.
    cout << "After Adding Stock:" << endl; // Display the message "After Adding Stock:".
    item1.AddStock(5); // Call the AddStock function of item1 with parameter 5.
    item1.Display(); // Call the Display function of item1.
    cout << endl; // Display a new line.
    cout << "After Selling:" << endl; // Display the message "After Selling:".
    item1.SellItem(3); // Call the SellItem function of item1 with parameter 3.
    item1.Display(); // Call the Display function of item1.
    cout << endl; // Display a new line.
    cout << "Other Item Details:" << endl; // Display the message "Other Item Details:".
    item2.Display(); // Call the Display function of item2.
    cout << endl; // Display a new line.
    item3.Display(); // Call the Display function of item3.
    cout << endl; // Display a new line.
    return 0; // Return 0 to indicate successful execution.
}
