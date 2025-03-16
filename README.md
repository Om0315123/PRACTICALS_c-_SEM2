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
 
