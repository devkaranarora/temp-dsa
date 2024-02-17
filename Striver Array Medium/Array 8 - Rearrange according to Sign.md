```cpp
class Solution {
public:
    vector<int> rearrangeArray(vector<int>& nums) {
        vector<int> ans(nums.size());
        int pos = 0, neg = 1;

        for (auto it : nums) {
            if (it>0){
                ans[pos] = it; pos += 2;
            }else{
                ans[neg] = it; neg += 2;
            }
        }
        return ans;
    }
};
```

```cpp
class Solution {
public:
    vector<int> rearrangeArray(vector<int>& nums) {
        int n = nums.size();
        vector<int> ans(n);
        int i=0,j=1;
        for(int k=0;k<n;k++){
            if(nums[k]>0){
                ans[i] = nums[k];
                i+=2;
            }
            else{
                ans[j] = nums[k];
                j+=2;
            }
        }
        return ans;
    }
};
```

```cpp
#include<bits/stdc++.h>
using namespace std;
  vector<int> RearrangebySign(vector<int>A, int n){
  vector<int> pos;
  vector<int> neg;
  for(int i=0;i<n;i++){
      if(A[i]>0) pos.push_back(A[i]);
      else neg.push_back(A[i]);
  }
  
  // If positives are lesser than the negatives.
  if(pos.size() < neg.size()){
       for(int i=0;i<pos.size();i++){
          A[2*i] = pos[i];
          A[2*i+1] = neg[i];
      }
      int index = pos.size()*2;
      for(int i = pos.size();i<neg.size();i++){
          A[index] = neg[i];
          index++;
      }
  }
  // If negatives are lesser than the positives.
  else{
      for(int i=0;i<neg.size();i++){
	      A[2*i] = pos[i];
	      A[2*i+1] = neg[i];
	  }
	  int index = neg.size()*2;
	  for(int i = neg.size();i<pos.size();i++){
      A[index] = pos[i];
      index++;
      }
  }
  return A; 
}
```

