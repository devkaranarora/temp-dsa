1 - using 3 nested loops
2 - using optimal 2 nested loops
3 - using prefix sum

```cpp
int longestSubarrayWithSumK(vector<int> arr, long long k) {
    int ans = 0;
    for(int i=0;i<arr.size();i++){
        for(int j=i;j<arr.size();j++){
            long long sum=0;
            for(int start=i;start<=j;start++){
                sum+=arr[start];
            }
            if(sum==k) ans = max(ans,j-i+1);
        }
    }
    return ans;
}
```

```cpp
int longestSubarrayWithSumK(vector<int> arr, long long k) {
    int ans = 0;
    for(int i=0;i<arr.size();i++){
        long long sum=0;
        for(int j=i;j<arr.size();j++){
            sum += arr[j];
            if (sum==k){
                ans = max(ans,j-i+1);
            }
        }
    }
    return ans;
}
```

```cpp
#include <bits/stdc++.h> 
int getLongestSubarray(vector<int>& a, int k){
    int ans = 0;
    long long currSum=0;
    map<long long,int> mp;
    for(int i=0;i<a.size();i++){
        currSum+=a[i];
        if(currSum==k) ans=max(i+1,ans); 
        // 🚀 here i stuck used i insteed of i+1
        int rem=currSum - k;
        if(mp.find(rem)!=mp.end()){
            ans=max(ans,i-mp[rem]);
        }
        if(mp.find(currSum)==mp.end()){
            mp[currSum] = i;
        }
    }
    return ans;
}
```

```cpp
int longestSubarrayWithSumK(vector<int> a, long long k) {
    // sliding window approch
    int n=a.size();
    int len=0;
    int right=0,left=0;
    long long sum=a[0];
    while(right<n){
        while(right>=left && sum>k){
            sum-=a[left];
            left++;
        }
        if(sum==k){
            len=max(len,right-left+1);
        }
        right++;
        if(right<n) sum+=a[right];
    }
    return len;
}
```


