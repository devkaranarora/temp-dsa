1- nested loops
2- hashing
3- 2  pointer + sorting

```cpp
string read(int n, vector<int> book, int target) {
    for(int i=0;i<book.size();i++){
        for(int j=i+1;j<book.size();j++){
            if(book[i]+book[j]==target){
                return (string)"YES";
            }
        }
    }
    return (string)"NO";
}
```

```cpp
#include <bits/stdc++.h>
string read(int n, vector<int> book, int target){
    map<int,int> mp;
    for(int it=0;it<book.size();it++)mp[book[it]]=it;
    for(auto it:book){
        int rem=target-it;
        if(mp.find(rem)!=mp.end()){
            return (string)"YES";
        }
    }
    return (string)"NO";
}
```

```cpp
string read(int n, vector<int> book, int target){
    sort(book.begin(),book.end());
    int i = 0,j=book.size()-1;
    while(i<j){
        int sum = book[i]+book[j];
        if(sum==target) return (string)"YES";
        if(sum<target) i++;
        if(sum>target) j--;
    }
    return (string)"NO";
}
```

