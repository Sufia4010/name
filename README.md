#include <iostream>
using namespace std;

namespace ExampleNamespace {
    int namespaceVar = 200;
}

// Global Scope Variable
int globalVar = 100;

class Sample {
private:
    int x;
public:
    // Constructor
    Sample(int val) {
        x = val;
        cout << "Constructor called! Value initialized: " << x << endl;
    }
    
    // Function demonstrating local scope and namespace usage
    void show() {
        int localVar = 10; // Local Scope Variable
        cout << "Local Variable: " << localVar << endl;
        cout << "Class Variable: " << x << endl;
        cout << "Global Variable: " << globalVar << endl;
        cout << "Namespace Variable: " << ExampleNamespace::namespaceVar << endl;
    }
    
    // Destructor
    ~Sample() {
        cout << "Destructor called! Object destroyed." << endl;
    }
};

int main() {
    cout << "Program starts..." << endl;
    
    Sample obj1(50); // Constructor invoked
    obj1.show();
    
    cout << "Exiting main function..." << endl;
    return 0; // Destructor automatically invoked
}
