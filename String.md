#include <iostream>
#include <string>

using namespace std;

// Function to calculate total characters
int countCharacters(const string& text) {
    return text.length(); // .length() gets the total number of characters
}

// Function to calculate total spaces
int countSpaces(const string& text) {
    int count = 0;
    for (int i = 0; i < text.length(); i++) {
        if (text[i] == ' ') {
            count++;
        }
    }
    return count;
}

// Function to calculate total tabs
int countTabs(const string& text) {
    int count = 0;
    for (int i = 0; i < text.length(); i++) {
        if (text[i] == '\t') {
            count++;
        }
    }
    return count;
}

// Function to calculate total lines
int countLines(const string& text) {
    if (text.length() == 0) return 0; // If empty string, 0 lines
    
    int count = 0;
    for (int i = 0; i < text.length(); i++) {
        if (text[i] == '\n') {
            count++;
        }
    }
    
    // If the last character isn't a newline, we still need to count that final line
    if (text[text.length() - 1] != '\n') {
        count++;
    }
    
    return count;
}

int main() {
    string inputStr;

    cout << "Enter a string (Type '~' and press Enter to finish):\n";
    
    // getline reads everything, including spaces, tabs, and newlines, until it sees '~'
    getline(cin, inputStr, '~'); 

    cout << "\n--- String Statistics ---\n";
    
    // Calling the functions and printing the results
    cout << "Total number of Characters: " << countCharacters(inputStr) << endl;
    cout << "Total number of Spaces: " << countSpaces(inputStr) << endl;
    cout << "Total number of Tabs: " << countTabs(inputStr) << endl;
    cout << "Total number of Lines: " << countLines(inputStr) << endl;

    return 0;
}
