Pascal’s triangle is a triangular array of binomial coefficients. Write a function that takes an integer value N as input and prints the first N lines of Pascal’s triangle.

Example:

The below image shows the Pascal’s Triangle for N=6

Pascal's-Triangle-for-first-6-Rows

Recommended Problem
Pascal Triangle
Arrays
Recursion
+2 more
Amazon
Microsoft
+1 more
Solve Problem
Submission count: 1.1L
Pascal’s Triangle using Binomial Coefficient:
The number of entries in every line is equal to line number. For example, the first line has “1“, the second line has “1 1“, the third line has “1 2 1“,.. and so on. Every entry in a line is value of a Binomial Coefficient. The value of ith entry in line number line is C(line, i). The value can be calculated using following formula. 

C(line, i) = line! / ( (line-i)! * i! )
 
Algorithm:

Run a loop for each row of pascal’s triangle i.e. 1 to N.
For each row, run an internal loop for each element of that row.
Calculate the binomial coefficient for the element using the formula mentioned in the approach.
Below is the implementation of the above approach:


//  C++ code for Pascal's Triangle
#include <iostream>
using namespace std;
 
 
int binomialCoeff(int n, int k);
 
// Function to print first
// n lines of Pascal's
// Triangle
void printPascal(int n)
{
    // Iterate through every line and
    // print entries in it
    for (int line = 0; line < n; line++) {
        // Every line has number of
        // integers equal to line
        // number
        for (int i = 0; i <= line; i++)
            cout << " " << binomialCoeff(line, i);
        cout << "\n";
    }
}
 
// See
// https://www.geeksforgeeks.org/space-and-time-efficient-binomial-coefficient/
// for details of this function
int binomialCoeff(int n, int k)
{
    int res = 1;
    if (k > n - k)
        k = n - k;
    for (int i = 0; i < k; ++i) {
        res *= (n - i);
        res /= (i + 1);
    }
 
    return res;
}
 
// Driver program
int main()
{
    int n = 7;
    printPascal(n);
    return 0;
}
 
// This code is contributed by shivanisinghss2110
