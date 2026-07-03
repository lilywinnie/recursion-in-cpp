# recursion-in-cpp-



# 1. Print Your Name N Times


    #include <iostream>
    #include <string>
    using namespace std;
    
    void printName(int n, string name) {
        if (n == 0) return; 
        cout << name << "\n";
        printName(n - 1, name); 
    }
    
    int main() {
        printName(5, "Alex");
        return 0;
    }



# 2. Print 1 to N


    #include <iostream>
    using namespace std;
    
    void print1ToN(int n) {
        if (n == 0) return;
        print1ToN(n - 1); 
        cout << n << " ";
    }
    
    int main() {
        print1ToN(10);
        cout << endl;
        return 0;
    }



# 3. Print N to 1


    #include <iostream>
    using namespace std;
    
    void printNTo1(int n) {
        if (n == 0) return;
        cout << n << " ";
        printNTo1(n - 1); 
    }
    
    int main() {
        printNTo1(10);
        cout << endl;
        return 0;
    }



# 4. Print All Digits of a Given Number N


    #include <iostream>
    using namespace std;
    
    void printDigits(int n) {
        if (n == 0) return;
        printDigits(n / 10); 
        cout << n % 10 << " ";
    }
    
    int main() {
        int n = 45281;
        if (n == 0) cout << 0;
        else printDigits(n);
        cout << endl;
        return 0;
    }



# 5. Binary to Decimal


    #include <iostream>
    #include <string>
    #include <cmath>
    using namespace std;
    
    int binaryToDecimal(string s, int i = 0) {
        if (s.empty()) return 0;
        int lastDigit = s.back() - '0';
        s.pop_back();
        return lastDigit * pow(2, i) + binaryToDecimal(s, i + 1);
    }
    
    int main() {
        cout << binaryToDecimal("1101") << endl; // 13
        return 0;
    }



# 6. Decimal to Binary


    #include <iostream>
    using namespace std;
    
    void decimalToBinary(int n) {
        if (n == 0) return;
        decimalToBinary(n / 2);
        cout << n % 2;
    }
    
    int main() {
        int n = 13;
        if (n == 0) cout << 0;
        else decimalToBinary(n);
        cout << endl;
        return 0;
    }



# 7. Count Vowels of a Given String S


    #include <iostream>
    #include <string>
    using namespace std;
    
    bool isVowel(char ch) {
        ch = tolower(ch);
        return (ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u');
    }
    
    int countVowels(string s, int idx = 0) {
        if (idx == s.length()) return 0;
        return isVowel(s[idx]) + countVowels(s, idx + 1);
    }
    
    int main() {
        cout << countVowels("Hello World") << endl; // 3
        return 0;
    }



# 8. Count Consonants of a Given String S


    #include <iostream>
    #include <string>
    using namespace std;
    
    bool isVowel(char ch) {
        ch = tolower(ch);
        return (ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u');
    }
    
    bool isConsonant(char ch) {
        ch = tolower(ch);
        return (ch >= 'a' && ch <= 'z') && !isVowel(ch);
    }
    
    int countConsonants(string s, int idx = 0) {
        if (idx == s.length()) return 0;
        return isConsonant(s[idx]) + countConsonants(s, idx + 1);
    }
    
    int main() {
        cout << countConsonants("Hello World") << endl; // 7
        return 0;
    }



# 9. Factorial


    #include <iostream>
    using namespace std;
    
    long long factorial(int n) {
        if (n <= 1) return 1;
        return n * factorial(n - 1);
    }
    
    int main() {
        cout << factorial(5) << endl; // 120
        return 0;
    }



# 10. Sum of 1 to N


    #include <iostream>
    using namespace std;
    
    int sum1ToN(int n) {
        if (n == 0) return 0;
        return n + sum1ToN(n - 1);
    }
    
    int main() {
        cout << sum1ToN(10) << endl; // 55
        return 0;
    }



# 11. Fibonacci


    #include <iostream>
    using namespace std;
    
    int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
    
    int main() {
        cout << fibonacci(6) << endl; // 8
        return 0;
    }




# 12. Palindrome Check


    #include <iostream>
    #include <string>
    using namespace std;
    
    bool isPalindrome(string s, int start, int end) {
        if (start >= end) return true;
        if (s[start] != s[end]) return false;
        return isPalindrome(s, start + 1, end - 1);
    }
    
    int main() {
        string s = "radar";
        if (isPalindrome(s, 0, s.length() - 1)) cout << "Palindrome\n";
        else cout << "Not Palindrome\n";
        return 0;
    }




# 13. Combination (nCr)


    #include <iostream>
    using namespace std;
    
    int nCr(int n, int r) {
        if (r == 0 || r == n) return 1;
        return nCr(n - 1, r - 1) + nCr(n - 1, r);
    }
    
    int main() {
        cout << nCr(5, 2) << endl; // 10
        return 0;
    }



# 14. Print Even Numbers of an Integer Array


    #include <iostream>
    using namespace std;
    
    void printEvenElements(int arr[], int size, int idx = 0) {
        if (idx == size) return;
        if (arr[idx] % 2 == 0) cout << arr[idx] << " ";
        printEvenElements(arr, size, idx + 1);
    }
    
    int main() {
        int arr[] = {1, 2, 3, 4, 5, 6};
        printEvenElements(arr, 6);
        cout << endl;
        return 0;
    }



# 15. Print Odd Numbers of an Integer Array


    #include <iostream>
    using namespace std;
    
    void printOddElements(int arr[], int size, int idx = 0) {
        if (idx == size) return;
        if (arr[idx] % 2 != 0) cout << arr[idx] << " ";
        printOddElements(arr, size, idx + 1);
    }
    
    int main() {
        int arr[] = {1, 2, 3, 4, 5, 6};
        printOddElements(arr, 6);
        cout << endl;
        return 0;
    }



# 16. Print Elements at Even Indices of an Array


    #include <iostream>
    using namespace std;
    
    void printEvenIndices(int arr[], int size, int idx = 0) {
        if (idx >= size) return;
        cout << arr[idx] << " ";
        printEvenIndices(arr, size, idx + 2); 
    }
    
    int main() {
        int arr[] = {10, 20, 30, 40, 50, 60};
        printEvenIndices(arr, 6); // Prints 10, 30, 50
        cout << endl;
        return 0;
    }



# 17. Print Elements at Odd Indices of an Array

      
    #include <iostream>
      using namespace std;
    
    void printOddIndices(int arr[], int size, int idx = 1) {
        if (idx >= size) return;
        cout << arr[idx] << " ";
        printOddIndices(arr, size, idx + 2);
    }
    
    int main() {
        int arr[] = {10, 20, 30, 40, 50, 60};
        printOddIndices(arr, 6); // Prints 20, 40, 60
        cout << endl;
        return 0;
    }



# 18. Check if an Array is Sorted

    
    #include <iostream>
    using namespace std;
    
    bool isSorted(int arr[], int size, int idx = 0) {
        if (idx >= size - 1) return true;
        if (arr[idx] > arr[idx + 1]) return false;
        return isSorted(arr, size, idx + 1);
    }
    
    int main() {
        int arr[] = {1, 3, 5, 7, 9};
        if (isSorted(arr, 5)) cout << "Sorted\n";
        else cout << "Not Sorted\n";
        return 0;
    }



# 19. Find the Maximum Digit of a Number


    #include <iostream>
    #include <algorithm>
    using namespace std;
    
    int maxDigit(int n) {
        if (n == 0) return 0;
        return max(n % 10, maxDigit(n / 10));
    }
    
    int main() {
        cout << maxDigit(39482) << endl; // 9
        return 0;
    }



# 20. Find the Minimum Digit of a Number


    #include <iostream>
    #include <algorithm>
    using namespace std;
    
    int minDigit(int n) {
        if (n < 10) return n;
        return min(n % 10, minDigit(n / 10));
    }
    
    int main() {
        cout << minDigit(39482) << endl; // 2
        return 0;
    }




# 21. Check if a Number is Prime


    #include <iostream>
    using namespace std;
    
    bool isPrime(int n, int i = 2) {
        if (n <= 2) return (n == 2);
        if (n % i == 0) return false;
        if (i * i > n) return true; 
        return isPrime(n, i + 1);
    }
    
    int main() {
        if (isPrime(29)) cout << "Prime\n";
        else cout << "Not Prime\n";
        return 0;
    }



# 22. Tribonacci (Sum of preceding 3 values)


    #include <iostream>
    using namespace std;
    
    int tribonacci(int n) {
        if (n == 0) return 0;
        if (n == 1 || n == 2) return 1;
        return tribonacci(n - 1) + tribonacci(n - 2) + tribonacci(n - 3);
    }
    
    int main() {
        cout << tribonacci(5) << endl; // 7
        return 0;
    }



# 23. Calculate $n$-th Harmonic Number 


    #include <iostream>
    using namespace std;
    
    double harmonic(int n) {
        if (n == 1) return 1.0;
        return (1.0 / n) + harmonic(n - 1);
    }
    
    int main() {
        cout << harmonic(4) << endl; // 2.08333
        return 0;
    }




# 24. Calculate GCD (Greatest Common Divisor)


    #include <iostream>
    using namespace std;
    
    int gcd(int a, int b) {
        if (b == 0) return a;
        return gcd(b, a % b);
    }
    
    int main() {
        cout << gcd(48, 18) << endl; // 6
        return 0;
    }




# 25. Calculate LCM (Least Common Multiple)


    #include <iostream>
    using namespace std;
    
    int gcdHelper(int a, int b) { 
        return b == 0 ? a : gcdHelper(b, a % b); 
    }
    
    int lcm(int a, int b) {
        return (a * b) / gcdHelper(a, b); 
    }
    
    int main() {
        cout << lcm(12, 18) << endl; // 36
        return 0;
    }




# 26. Calculate Ackermann Function


    #include <iostream>
    using namespace std;
    
    int ackermann(int m, int n) {
        if (m == 0) return n + 1;
        if (m > 0 && n == 0) return ackermann(m - 1, 1);
        return ackermann(m - 1, ackermann(m, n - 1));
    }
    
    int main() {
        cout << ackermann(2, 2) << endl; // 7
        return 0;
    }




# 27. Print Your Name in Reverse Order


    #include <iostream>
    #include <string>
    using namespace std;
    
    void reverseName(string name, int idx) {
        if (idx < 0) return;
        cout << name[idx];
        reverseName(name, idx - 1);
    }
    
    int main() {
        string name = "Alex";
        reverseName(name, name.length() - 1); // xelA
        cout << endl;
        return 0;
    }




# 28. Reverse a Number


    #include <iostream>
    using namespace std;
    
    int reverseNumber(int n, int rev = 0) {
        if (n == 0) return rev;
        return reverseNumber(n / 10, rev * 10 + n % 10);
    }
    
    int main() {
        cout << reverseNumber(12345) << endl; // 54321
        return 0;
    }




# 29. Binary Search in a Sorted Array


    #include <iostream>
    using namespace std;
    
    int binarySearch(int arr[], int low, int high, int target) {
        if (low > high) return -1; 
        
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] > target) return binarySearch(arr, low, mid - 1, target);
        return binarySearch(arr, mid + 1, high, target);
    }
    
    int main() {
        int arr[] = {2, 4, 6, 8, 10};
        cout << "Index: " << binarySearch(arr, 0, 4, 8) << endl; // Index: 3
        return 0;
    }




# 30. Sum of an Integer Array

    
    #include <iostream>
    using namespace std;
    
    int sumArray(int arr[], int size, int idx = 0) {
        if (idx == size) return 0;
        return arr[idx] + sumArray(arr, size, idx + 1);
    }
    
    int main() {
        int arr[] = {1, 2, 3, 4, 5};
        cout << sumArray(arr, 5) << endl; // 15
        return 0;
    }
    
    
