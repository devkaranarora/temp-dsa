```cpp
class Solution {
public:
    vector<int> solve(vector<int>&v){
        int n = v.size();
        int ind = -1;
        for(int i=n-2;i>=0;i--){
            if(v[i] < v[i+1]){
                ind = i;
                break;
            }
        }
        if(ind == -1){
            reverse(v.begin(), v.end());
            return v;
        }
        for(int i = n-1;i>ind;i--){
            if(v[i] > v[ind]){
                swap(v[ind], v[i]);
                break;
            }
        }
        reverse(v.begin()+ ind+1, v.end());
        return v;
    }
    void nextPermutation(vector<int>& nums) {
        solve(nums);
    }
};
```

```cpp
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        next_permutation(nums.begin(),nums.end());
    }
};
```

