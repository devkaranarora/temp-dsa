1 - using sorting elements and returning last and first element 
2 - using a max variable and storing max in it 

 ### **Code**
 
```cpp
#include<bits/stdc++.h>
using namespace std;
 
int sortArr(vector<int>& arr) {
    sort(arr.begin(),arr.end());
    return arr[arr.size()-1];
}
 
int main() {
	vector<int> arr1 = {2,5,1,3,0};
	vector<int> arr2 = {8,10,5,7,9};
   
	cout<<"The Largest element in the array is: "<<sortArr(arr1)<<endl;
	cout<<"The Largest element in the array is: "<<sortArr(arr2);
   
	return 0;
}

```

```javascript
function sortArr(arr) {
  arr.sort((a, b) => a - b);
  return arr[arr.length - 1];
}

const arr1 = [2, 5, 1, 3, 0];
const arr2 = [8, 10, 5, 7, 9];

console.log("The Largest element in the array is: " + sortArr(arr1));
console.log("The Largest element in the array is: " + sortArr(arr2));
```


