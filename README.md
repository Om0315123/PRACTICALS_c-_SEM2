# PRACTICALS_cpp_SEM2
All the practicals of c++ in syllabus are pushed here 
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


 #3 practical <br>
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
