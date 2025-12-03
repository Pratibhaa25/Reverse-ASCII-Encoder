#include<iostream>
#include<string>
#include<sstream>
#include<vector>
using namespace std;

int main() {
    
    cout << " Please Enter your messgae: ";
    string message;
    getline(cin, message);

    vector<string> sentences; //to store sentence seggregate krke  just to print in reverse order     
    stringstream stream(message); 
    string singleSentence; ////temporary variable to store strings

    // Split input into sentences using '.' as the delimiter
    while (getline(stream, singleSentence, '.')) { 
        if (!singleSentence.empty()) {
            sentences.push_back(singleSentence);
        }
    }

    cout << "\nASCII Conversion (Reverse Order):\n";

    // Print sentences in reverse order with ASCII codes
    for (int i = sentences.size() - 1; i >= 0; i--) {
        for (char ch : sentences[i]) {
            cout << (int)ch << " ";
        }
        cout << (int)'.' << endl; // add ASCII for the period
    }

    return 0;
}
