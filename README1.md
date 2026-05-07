// 
#include <iostream>

using namespace std;


void findMaxMin(int arr[], int n) {
    if (n <= 0) {
        cout << "Array is empty." << endl;
        return;
    }

   
    int max_val = arr[0];
    int min_val = arr[0];

    
    for (int i = 1; i < n; i++) {
        if (arr[i] > max_val) {
            max_val = arr[i]; // Update max if current element is greater
        }
        if (arr[i] < min_val) {
            min_val = arr[i]; // Update min if current element is smaller
        }
    }

  
    cout << "Maximum value: " << max_val << endl;
    cout << "Minimum value: " << min_val << endl;
}

int main() {
    int data[] = {15, 22, 8, 45, 3, 91, 14};
    int n = sizeof(data) / sizeof(data[0]);

    cout << "Array elements: ";
    for(int i = 0; i < n; i++) {
        cout << data[i] << " ";
    }
    cout << "\n\n";

    // Call the function
    findMaxMin(data, n);

    return 0;
}
