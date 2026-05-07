
#include <iostream>
#include <cmath>

using namespace std;


double stdev(double x[], int n) {
    if (n <= 1) return 0.0; 

    double sum = 0.0, mean = 0.0, standardDeviation = 0.0;

  
    for(int i = 0; i < n; ++i) {
        sum += x[i];
    }
    mean = sum / n;

    
    for(int i = 0; i < n; ++i) {
        standardDeviation += pow(x[i] - mean, 2);
    }

    
    return sqrt(standardDeviation / (n - 1));
}

int main() {
    double data[] = {10.0, 12.0, 23.0, 23.0, 16.0, 23.0, 21.0, 16.0};
    int n = sizeof(data) / sizeof(data[0]);

    cout << "Standard Deviation: " << stdev(data, n) << endl;

    return 0;
}
