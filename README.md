# PRACTICALS_cpp_SEM2
All the practicals of c++ in syllabus are pushed here 
<br>
##1 WAP to Remove duplicates from Array. <br>
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

##2 wap that prints a table indicating the number of occurrance of each alphabet in the text entered as command line argument.
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


 
