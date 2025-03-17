# PRACTICALS_cpp_SEM2
All the practicals of c++ in syllabus are pushed here 
<br>
<br>
#1 WAP to Remove duplicates from Array. <br>
<b>CODE AREA</b> <br>


    #include <iostream>
    #include <unordered_set>
    using namespace std;
    int main() {
      int size;
    
    cout << "Enter array size: ";
    
    cin >> size;
    
    if (size <= 0) return 1;
    
    int arr[size], uniqueArr[size], count = 0;
    unordered_set<int> seen;

    cout << "Enter " << size << " elements:\n";
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
        if (seen.insert(arr[i]).second) uniqueArr[count++] = arr[i];
    }

    cout << "Array without duplicates: ";
    for (int i = 0; i < count; i++) cout << uniqueArr[i] << " ";

    cout << "\nUnique count: " << count << endl;
    return 0;
    }
<b>OUTPUT</b> <br>
<img src="https://github.com/user-attachments/assets/9f8ad516-35b9-4146-bddc-a2980491f358" lenth='400' width ='450'>

#2 wap that prints a table indicating the number of occurrance of each alphabet in the text entered as command line argument.
<BR>
<b>CODE</b> <br>

    #include <iostream>
    #include <cctype>
    using namespace std;

    int main() {
       string input;
       int count[26] = {0};

       cout << "Enter a string: ";
       getline(cin, input);

       for (char c : input) {
          if (isalpha(c)) {
              count[tolower(c) - 'a']++;
        }
    }

    cout << "Alphabet Frequency Table:\n";
    for (int i = 0; i < 26; i++) {
        if (count[i] > 0) {
            cout << char('a' + i) << " : " << count[i] << endl;
        }
    }

    return 0;
    }
<br>
<b>OUTPUT</b> <br>
<img src='https://github.com/user-attachments/assets/280b5b5c-daa6-4c5f-b462-ab588e9813ff'length='500' width='550'alt='practical2 output'>


 #3  <br>
 <img src='https://github.com/user-attachments/assets/db977c0b-25a9-4139-8dbb-f881f0b5e835' length='500' width='550'>
<br>
<b>CODE</b> <br>

    #include <iostream>
    #include <cstring>
    using namespace std;

    void showAddresses(const char* str) {
         while (*str) {
              cout << "Character: " << *str << " Address: " << (void*)str << endl;
               str++;
       }
    }

    void concatenate(char* str1, const char* str2) {
        while (*str1) str1++;
        while (*str2) *str1++ = *str2++;
        *str1 = '\0';
    }

    int compareStrings(const char* str1, const char* str2) {
        while (*str1 && *str2 && *str1 == *str2) {
           str1++, str2++;
      }
       return *str1 - *str2;
      }

    int stringLength(const char* str) {
        int length = 0;
        while (*str++) length++;
        return length;
    }

    void toUpperCase(char* str) {
        while (*str) {
            if (*str >= 'a' && *str <= 'z') *str -= 32;
                str++;
       }
    }

    void reverseString(char* str) {
       int len = stringLength(str);
       for (int i = 0; i < len / 2; i++) {
            char temp = str[i];
            str[i] = str[len - i - 1];
            str[len - i - 1] = temp;
        }
    }

    int main() {
       char str1[100], str2[100];
       cout << "Enter first string: ";
       cin.getline(str1, 100);
       cout << "Enter second string: ";
       cin.getline(str2, 100);
     cout << "\n1. Addresses of characters in first string:\n";
    showAddresses(str1);

    char concatenated[200];
    strcpy(concatenated, str1);
    concatenate(concatenated, str2);
    cout << "\n2. Concatenated string: " << concatenated << endl;

    cout << "\n3. String comparison result: " << compareStrings(str1, str2) << endl;

    cout << "\n4. Length of first string: " << stringLength(str1) << endl;

    toUpperCase(str1);
    cout << "\n5. Uppercase string: " << str1 << endl;

    reverseString(str1);
    cout << "\n6. Reversed string: " << str1 << endl;

    return 0;
    }
<b>OUTPUT<b/> <br>
<img src='https://github.com/user-attachments/assets/1ef34c64-a24b-4f95-ba67-dd4a4546777b' length='500' width='550'>
<br>
#4 WAP to Merge two ordered arrays to get a single ordered array. <br>
<b>CODE<b> <br>

    #include <iostream>
    using namespace std;

    void mergeArrays(int arr1[], int size1, int arr2[], int size2, int merged[]) {
          int i = 0, j = 0, k = 0;
          while (i < size1 && j < size2) {
              if (arr1[i] < arr2[j])
                 merged[k++] = arr1[i++];
               else
                  merged[k++] = arr2[j++];
    }
    while (i < size1)
        merged[k++] = arr1[i++];
    while (j < size2)
      merged[k++] = arr2[j++];
    }

    int main() {
        int size1, size2;
        cout << "Enter size of first array: ";
        cin >> size1;
        int arr1[size1];
        cout << "Enter elements of first sorted array: ";
        for (int i = 0; i < size1; i++)
            cin >> arr1[i];

    cout << "Enter size of second array: ";
    cin >> size2;
    int arr2[size2];
    cout << "Enter elements of second sorted array: ";
    for (int i = 0; i < size2; i++)
        cin >> arr2[i];

    int merged[size1 + size2];
    mergeArrays(arr1, size1, arr2, size2, merged);

    cout << "Merged sorted array: ";
    for (int i = 0; i < size1 + size2; i++)
        cout << merged[i] << " ";
    cout << endl;
    
    return 0;
    }
<br>
<b>OUTPUT</b> <br>
<img src='https://github.com/user-attachments/assets/57578a24-e8b9-4e2d-9c79-8cdf2e789972' length='500' width='550'>

#5 Write a program to search a given element in a set of N numbers using Binary search
l) with recumion 2) without recursion. <br>
<b>CODE<b> <br>

    #include <iostream>
    using namespace std;

    int binarySearchRecursive(int arr[], int left, int right, int key) {
        if (left <= right) {
            int mid = left + (right - left) / 2;
        if (arr[mid] == key)
            return mid;
        else if (arr[mid] < key)
            return binarySearchRecursive(arr, mid + 1, right, key);
        else
            return binarySearchRecursive(arr, left, mid - 1, key);
    }
       return -1;
    }

    int binarySearchIterative(int arr[], int size, int key) {
           int left = 0, right = size - 1;
           while (left <= right) {
                int mid = left + (right - left) / 2;
           if (arr[mid] == key)
              return mid;
          else if (arr[mid] < key)
              left = mid + 1;
          else
            right = mid - 1;
    }
      return -1;
    }

    int main() {
         int size, key;
         cout << "Enter size of array: ";
         cin >> size;
         int arr[size];
         cout << "Enter sorted array elements: ";
         for (int i = 0; i < size; i++)
              cin >> arr[i];

    cout << "Enter element to search: ";
    cin >> key;

    int recursiveResult = binarySearchRecursive(arr, 0, size - 1, key);
    int iterativeResult = binarySearchIterative(arr, size, key);

    if (recursiveResult != -1)
        cout << "Element found at index (recursion): " << recursiveResult << endl;
    else
        cout << "Element not found (recursion)" << endl;

    if (iterativeResult != -1)
        cout << "Element found at index (iteration): " << iterativeResult << endl;
    else
        cout << "Element not found (iteration)" << endl;
    
       return 0;
    }
<b>OUTPUT</b> <br>
 <img src='https://github.com/user-attachments/assets/c6d97d15-80ec-47e0-8305-15cd678bb53e' length='500' width ='550'>
<br>
#6 Write a program to calculate GCD of two numbers (i) with recursion (ii) without
recursion. <br>
<b>CODE</b> <br>

    #include <iostream>
    using namespace std;

    int gcdRecursive(int a, int b) {
       if (b == 0)
         return a;
       return gcdRecursive(b, a % b);
    }

    int gcdIterative(int a, int b) {
       while (b != 0) {
          int temp = b;
          b = a % b;
          a = temp;
    }
    return a;
    }

    int main() {
       int num1, num2;
       cout << "Enter two numbers: ";
       cin >> num1 >> num2;

    cout << "GCD (Recursion): " << gcdRecursive(num1, num2) << endl;
    cout << "GCD (Iteration): " << gcdIterative(num1, num2) << endl;
    
    return 0;
    }

<br>
<img src='https://github.com/user-attachments/assets/8ea242a3-e483-4736-b341-73582c63f461' length = '500' width = '550'>
<br>

#7 Create a Matrix class. Write a menu-driven program to perform following Matrix
operations (exceptions should be thrown by the functions if matrices passed to them
are incompatible and handled by the main() function):
a. Sum <br>
b. Product <br>
c. Transpose
<br>
<b>CODE</b> 
<BR>
      
    #include <iostream>
    #include <vector>
    using namespace std;

    class Matrix {
         vector<vector<int>> mat;
         int rows, cols;

        public:
             Matrix(int r, int c) : rows(r), cols(c), mat(r, vector<int>(c)) {}

             void inputMatrix() {
                  cout << "Enter elements of " << rows << "x" << cols << " matrix:\n";
                  for (int i = 0; i < rows; i++) {
                  for (int j = 0; j < cols; j++) {
                  cin >> mat[i][j];
               }
            }
        }

    void displayMatrix() {
        for (const auto &row : mat) {
            for (int val : row) {
                cout << val << " ";
            }
            cout << endl;
        }
    }

    Matrix operator+(const Matrix &other) {
        if (rows != other.rows || cols != other.cols)
            throw invalid_argument("Matrix dimensions must match for addition");
        Matrix result(rows, cols);
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                result.mat[i][j] = mat[i][j] + other.mat[i][j];
            }
        }
        return result;
    }

    Matrix operator*(const Matrix &other) {
        if (cols != other.rows)
            throw invalid_argument("Matrix dimensions are incompatible for multiplication");
        Matrix result(rows, other.cols);
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < other.cols; j++) {
                for (int k = 0; k < cols; k++) {
                    result.mat[i][j] += mat[i][k] * other.mat[k][j];
                }
            }
        }
        return result;
    }

    Matrix transpose() {
        Matrix result(cols, rows);
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                result.mat[j][i] = mat[i][j];
            }
        }
        return result;
    }
    }

    int main() {
         int choice, r1, c1, r2, c2;
         cout << "Enter rows and columns for first matrix: ";
         cin >> r1 >> c1;
         Matrix A(r1, c1);
         A.inputMatrix();

    cout << "Enter rows and columns for second matrix: ";
    cin >> r2 >> c2;
    Matrix B(r2, c2);
    B.inputMatrix();

    do {
        cout << "\nMenu:\n1. Sum\n2. Product\n3. Transpose\n4. Exit\nEnter choice: ";
        cin >> choice;
        try {
            if (choice == 1) {
                Matrix sum = A + B;
                cout << "\nSum of matrices:\n";
                sum.displayMatrix();
            } else if (choice == 2) {
                Matrix product = A * B;
                cout << "\nProduct of matrices:\n";
                product.displayMatrix();
            } else if (choice == 3) {
                cout << "\nTranspose of first matrix:\n";
                Matrix tA = A.transpose();
                tA.displayMatrix();

                cout << "\nTranspose of second matrix:\n";
                Matrix tB = B.transpose();
                tB.displayMatrix();
            }
        } catch (const exception &e) {
            cout << "Error: " << e.what() << endl;
        }
    } while (choice != 4);
    
       return 0;
    }

<br>
<b>OUTPUT</b> <br>
<img src='https://github.com/user-attachments/assets/8a67c583-06c2-4fd7-9c7b-522586b0431b' length = '500' width = '550'> <br>



























