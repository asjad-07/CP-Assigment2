
#include <iostream>

using namespace std;

// Function to get values from the user
void GetValue(int arr[3][3]) {
    cout << "Enter 9 elements for the 3x3 matrix:\n";
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            cin >> arr[i][j];
        }
    }
}

// Function to compute element-wise multiplication (A x A)
void ComputeAxA(int A[3][3], int result[3][3]) {
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            // Element-wise multiplication (squaring the element)
            result[i][j] = A[i][j] * A[i][j]; 
        }
    }
}

// Function to print the matrix
void PrintArray(int arr[3][3]) {
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            cout << arr[i][j] << "\t";
        }
        cout << "\n";
    }
}

int main() {
    int matrixA[3][3];
    int resultMatrix[3][3];

    GetValue(matrixA);
    ComputeAxA(matrixA, resultMatrix);
    
    cout << "\nResulting Matrix (Element-wise A x A):\n";
    PrintArray(resultMatrix);

    return 0;
}
