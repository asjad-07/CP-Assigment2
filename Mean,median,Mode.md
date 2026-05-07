#include <iostream>
#include <algorithm> // Required for std::sort

using namespace std;

// Function to calculate the Mean
double getMean(int arr[], int n) {
    double sum = 0;
    for(int i = 0; i < n; i++) {
        sum += arr[i];
    }
    return sum / n;
}

// Function to calculate the Median
double getMedian(int arr[], int n) {
    // Sort the array first
    sort(arr, arr + n);
    
    // If even number of elements, return average of two middle elements
    if (n % 2 == 0) {
        return (arr[(n - 1) / 2] + arr[n / 2]) / 2.0;
    } 
    // If odd, return the middle element
    return arr[n / 2];
}

// Function to calculate the Mode
int getMode(int arr[], int n) {
    sort(arr, arr + n); // Sorting helps count consecutive duplicates easily
    
    int max_count = 1, mode = arr[0], current_count = 1;
    
    for (int i = 1; i < n; i++) {
        if (arr[i] == arr[i - 1]) {
            current_count++;
        } else {
            if (current_count > max_count) {
                max_count = current_count;
                mode = arr[i - 1];
            }
            current_count = 1; // Reset count for the next number
        }
    }
    
    // Check the last sequence
    if (current_count > max_count) {
        mode = arr[n - 1];
    }
    
    return mode;
}

int main() {
    int data[] = {1, 3, 2, 4, 2, 5, 2, 8, 4};
    int n = sizeof(data) / sizeof(data[0]);

    cout << "Array elements: ";
    for(int i=0; i<n; i++) cout << data[i] << " ";
    cout << "\n\n";

    cout << "Mean: " << getMean(data, n) << endl;
    cout << "Median: " << getMedian(data, n) << endl;
    cout << "Mode: " << getMode(data, n) << endl;

    return 0;
}
