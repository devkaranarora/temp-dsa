```cpp
vector<int> printLeadersBruteForce(int arr[], int n) {
  vector<int> ans;
  for (int i = 0; i < n; i++) {
    bool leader = true;
    for (int j = i + 1; j < n; j++)
      if (arr[j] > arr[i]) {
        leader = false;
        break;
      }
    if (leader)
    ans.push_back(arr[i]);
  }
  return ans;
}
```

```cpp
vector<int> printLeaders(int arr[], int n) {
  vector<int> ans;
 int max = arr[n - 1];
 ans.push_back(arr[n-1]);
  for (int i = n - 2; i >= 0; i--)
    if (arr[i] > max) {
      ans.push_back(arr[i]);
      max = arr[i];
    }
  return ans;
}
```
