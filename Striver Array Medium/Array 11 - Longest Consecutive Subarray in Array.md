```cpp
bool linearSearch(vector<int>&a, int num) {
    int n = a.size(); //size of array
    for (int i = 0; i < n; i++) {
        if (a[i] == num)
            return true;
    }
    return false;
}
int longestSuccessiveElements(vector<int>&a) {
    int n = a.size(); //size of array
    int longest = 1;
    for (int i = 0; i < n; i++) {
        int x = a[i];
        int cnt = 1;
        while (linearSearch(a, x + 1) == true) {
            x += 1;
            cnt += 1;
        }
        longest = max(longest, cnt);
    }
    return longest;
}
```

```cpp
int longestSuccessiveElements(vector<int>&a) {
    sort(a.begin(), a.end());

    int count = 1,maxCount=1;
    for (int i = 1; i < a.size(); i++) {
        if (a[i - 1] + 1 == a[i]) {
            count++;
            maxCount = max(count, maxCount);
        } 
        else if (a[i-1]==a[i]) continue; 
        else count = 1; 
    }
    return maxCount;
}
```

```cpp
int longestSuccessiveElements(vector<int>&a) {
    int n = a.size();
    if (n == 0) return 0;

    int longest = 1;
    unordered_set<int> st;
    for (int i = 0; i < n; i++) st.insert(a[i]);
    for (auto it : st) {
        if (st.find(it - 1) == st.end()) {
            int cnt = 1;
            int x = it;
            while (st.find(x + 1) != st.end()) {
                x = x + 1;
                cnt = cnt + 1;
            }
            longest = max(longest, cnt);
        }
    }
    return longest;
}
```

