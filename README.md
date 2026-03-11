#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

// Function to convert decimal to binary
string decimalToBinary(int n) {
    string binary = "";
    while (n > 0) {
        binary += (n % 2 == 0 ? "0" : "1");
        n /= 2;
    }
    reverse(binary.begin(), binary.end());
    return binary.empty() ? "0" : binary;
}

// Function to convert binary to decimal
int binaryToDecimal(string binary) {
    int decimal = 0;
    int power = 1; // 2^0
    for (int i = binary.size() - 1; i >= 0; i--) {
        if (binary[i] == '1') {
            decimal += power;
        }
        power *= 2;
    }
    return decimal;
}

int main() {
    int choice;
    cout << "Number Conversion Program\n";
    cout << "1. Decimal to Binary\n";
    cout << "2. Binary to Decimal\n";
    cout << "Enter your choice: ";
    cin >> choice;

    if (choice == 1) {
        int decimal;
        cout << "Enter a decimal number: ";
        cin >> decimal;
        cout << "Binary representation: " << decimalToBinary(decimal) << endl;
    } else if (choice == 2) {
        string binary;
        cout << "Enter a binary number: ";
        cin >> binary;
        cout << "Decimal representation: " << binaryToDecimal(binary) << endl;
    } else {
        cout << "Invalid choice!" << endl;
    }

    return 0;
}
