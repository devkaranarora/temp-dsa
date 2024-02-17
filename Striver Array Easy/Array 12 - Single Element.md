1 - using bits
2 - using 2 loops
3 - using array hashing
4 - using map data structure

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int ans = 0;
        for(int i=0;i<nums.size();i++){
            ans=ans^nums[i];
        }
        return ans;
    }
};
```

```cpp
#include <bits/stdc++.h>
using namespace std;
int getSingleElement(vector<int> &arr) {
    int n = arr.size();
    int maxi = arr[0];
    for (int i = 0; i < n; i++) {
        maxi = max(maxi, arr[i]);
    }
    vector<int> hash(maxi + 1, 0);
    for (int i = 0; i < n; i++) {
        hash[arr[i]]++;
    }
    for (int i = 0; i < n; i++) {
        if (hash[arr[i]] == 1) return arr[i];
    }
    return -1;
}

int main(){
    vector<int> arr = {4, 1, 2, 1, 2};
    int ans = getSingleElement(arr);
    cout << "The single element is: " << ans << endl;
    return 0;
}
```

```cpp
int getSingleElement(vector<int> &arr) {
    int n = arr.size();
    map<int, int> mpp;
    for (int i = 0; i < n; i++) {
        mpp[arr[i]]++;
    }
    for (auto it : mpp) {
        if (it.second == 1)
            return it.first;
    }

    return -1;
}

int main(){
    vector<int> arr = {4, 1, 2, 1, 2};
    int ans = getSingleElement(arr);
    cout << "The single element is: " << ans << endl;
    return 0;
}

```

```cpp
#include <bits/stdc++.h>
using namespace std;
int getSingleElement(vector<int> &arr) {
    int n = arr.size();
    for (int i = 0; i < n; i++) {
        int num = arr[i],cnt = 0;
        
        for (int j = 0; j < n; j++) {
            if (arr[j] == num) cnt++;
        }
        if (cnt == 1) return num;
    }
    return -1;
}
int main(){
    vector<int> arr = {4, 1, 2, 1, 2};
    int ans = getSingleElement(arr);
    cout << "The single element is: " << ans << endl;
    return 0;
}
```


