1- more voting algorithms
2- n^2 nested loops
3 - hashmap and counter 

```cpp
int majorityElement(vector<int> v) {
    int i=0,n=v.size();
    int temp;
    int count=0;
    while(i<n){
        if(count==0) temp=v[i];
        // handle counter
        if(temp==v[i]){count++;}
        else{count--;}
        i++;
    }
    return temp;
}
```
