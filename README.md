#include <iostream>

using namespace std;

void arithmeticOperations() {
    int num1, num2;
    cout << "\nEnter first number: ";
    cin >> num1;
    cout << "Enter second number: ";
    cin >> num2;
    cout << "\nResults:\n";
    cout << "Sum: " << num1 + num2 << endl;
    cout << "Difference: " << num1 - num2 << endl;
    cout << "Product: " << num1 * num2 << endl;
    cout << "Quotient: " << (float)num1 / num2 << endl;
    cout << "Remainder: " << num1 % num2 << endl;
}

void checkNumber() {
    int num;
    cout << "\nEnter a number: ";
    cin >> num;
    if (num > 0)
        cout << "The number is positive.\n";
    else if (num < 0)
        cout << "The number is negative.\n";
    else
        cout << "The number is zero.\n";
}

void multiplicationTable() {
    int num;
    cout << "\nEnter a number for multiplication table: ";
    cin >> num;
    cout << "\nMultiplication Table of " << num << ":\n";
    for (int i = 1; i <= 10; i++) {
        cout << num << " x " << i << " = " << num * i << endl;
    }
}

void gradingSystem() {
    int score;
    cout << "\nEnter your score: ";
    cin >> score;
    if (score >= 90 && score <= 100)
        cout << "Your grade is: A\n";
    else if (score >= 80)
        cout << "Your grade is: B\n";
    else if (score >= 70)
        cout << "Your grade is: C\n";
    else if (score >= 60)
        cout << "Your grade is: D\n";
    else
        cout << "Your grade is: F\n";
}

void primeNumberCheck() {
    int num, i;
    bool isPrime = true;
    cout << "\nEnter a number: ";
    cin >> num;
    if (num <= 1)
        isPrime = false;
    else {
        for (i = 2; i * i <= num; i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
    }
    if (isPrime)
        cout << num << " is a prime number.\n";
    else
        cout << num << " is not a prime number.\n";
}

void fibonacciSeries() {
    int n, t1 = 0, t2 = 1, nextTerm;
    cout << "\nEnter the number of Fibonacci terms: ";
    cin >> n;
    cout << "Fibonacci Series: " << t1 << ", " << t2;
    for (int i = 2; i < n; i++) {
        nextTerm = t1 + t2;
        cout << ", " << nextTerm;
        t1 = t2;
        t2 = nextTerm;
    }
    cout << endl;
}

int main() {
    int choice;
    do {
        cout << "\n===== C++ Hands-On Activity =====\n";
        cout << "1. Arithmetic Operations\n";
        cout << "2. Check Positive, Negative, or Zero\n";
        cout << "3. Multiplication Table\n";
        cout << "4. Grading System\n";
        cout << "5. Prime Number Check\n";
        cout << "6. Fibonacci Series\n";
        cout << "7. Exit\n";
        cout << "Enter your choice (1-7): ";
        cin >> choice;
        
        switch (choice) {
            case 1: arithmeticOperations(); break;
            case 2: checkNumber(); break;
            case 3: multiplicationTable(); break;
            case 4: gradingSystem(); break;
            case 5: primeNumberCheck(); break;
            case 6: fibonacciSeries(); break;
            case 7: cout << "Exiting the program...\n"; break;
            default: cout << "Invalid choice! Try again.\n";
        }
    } while (choice != 7);
    return 0;
}
