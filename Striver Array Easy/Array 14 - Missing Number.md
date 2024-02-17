1 - dual for loop 
2 - sorting loops and comparing previous 
3 - hashmap and loop traversal
4 - sum approach
5 - XOR 1-n and all array element 

```cpp
#include <bits/stdc++.h>
using namespace std;
int missingNumber(vector<int>&a, int N) {
    int xor1 = 0, xor2 = 0;
    for (int i = 0; i < N - 1; i++) {
        xor2 = xor2 ^ a[i]; // XOR of array elements
        xor1 = xor1 ^ (i + 1); //XOR up to [1...N-1]
    }
    xor1 = xor1 ^ N; //XOR up to [1...N]
    return (xor1 ^ xor2); // the missing number
}
```

```cpp
#include <bits/stdc++.h>
using namespace std;
int missingNumber(vector<int>&a, int N) {
    int sum = (N * (N + 1)) / 2;
    int s2 = 0;
    for (int i = 0; i < N - 1; i++) {
        s2 += a[i];
    }
    int missingNum = sum - s2;
    return missingNum;
}
```

