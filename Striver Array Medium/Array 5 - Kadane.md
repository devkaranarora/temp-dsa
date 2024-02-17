1-kadane 
2-all subarray sum 
3- optimized subarray sum 

```cpp
long long maxSubarraySum(vector<int> arr, int n) {
    long long sum=0, ans=0;
    for (int i = 0; i < arr.size(); i++) {
        int val = arr[i];
        if(sum<0)sum=0;
        sum = sum + val;
        ans = max(ans,sum);
    }
    return ans;
}
```
