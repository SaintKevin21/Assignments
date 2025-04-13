// Name: Kevin Kangethe,
//
// Course: CMPS 2433-201, Spring 25, Griffin
//
// Purpose:
// Implement the basic structure of your classes in C++ without full CRUD functionality.
// Focus on constructors, getters, setters, and basic data representation.
//----------------------------------------------------


#include <iostream>
#include <string>
#include <nlohmann/json.hpp> // external JSON library

using namespace std;
using json = nlohmann::json;

// ------------------------------------
// Candy class - represents one candy
// ------------------------------------
class Candy {
private:
    int id;
    double price;
    string name;
    string category;

public:
    // Default + parameterized constructor
    Candy(int id = 0, double price = 0.0, string name = "", string category = "")
        : id(id), price(price), name(name), category(category) {}

    // --- Getters ---
    int getId() const { return id; }
    double getPrice() const { return price; }
    string getName() const { return name; }
    string getCategory() const { return category; }

    // --- Setters ---
    void setId(int id) { this->id = id; }
    void setPrice(double price) { this->price = price; }
    void setName(const string& name) { this->name = name; }
    void setCategory(const string& category) { this->category = category; }

    // Print out candy info (for testing)
    void print() const {
        cout << "Candy [ID: " << id 
             << ", Name: " << name 
             << ", Category: " << category 
             << ", Price: $" << price << "]" << endl;
    }
};


// JSONDBManager class - handles the filename and json object (stub)

class JSONDBManager {
protected:
    string filename; // where the data will be saved/loaded
    json db;         // JSON object to hold data

public:
    // Constructor sets the filename
    JSONDBManager(string file) : filename(file) {}

    //oading data from file
    void load() {
        cout << "Loading from " << filename << "...\n";
       
    }

    // save() method removed for now (not needed yet)
};


// CandyManager - connects to JSONDBManager (also a stub)

class CandyManager : public JSONDBManager {
public:
    // Just pass the filename to the base constructor
    CandyManager(string file) : JSONDBManager(file) {}

    // No extra logic yet — just a stub class
};


int main() {
    // Create a Candy object
    Candy c1(1, 2.99, "Snickers", "Chocolate");

    // print Candy info
    c1.print();

    // Create a CandyManager 
    CandyManager manager("candy_db.json");

    // Test the load function
    manager.load();

    return 0;
}

