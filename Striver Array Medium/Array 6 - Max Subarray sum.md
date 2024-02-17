```cpp
void printMx(int a[] , int l){
    int start=0,end=0;
    int sum=0,ans=0;
    for(int i=0;i<l;i++){
        if(sum<0) {
            sum=0;start=i;
        }
        int val = a[i];
        sum = sum+val;
        if(sum>ans){
            ans = sum; end = i;
        }
    }
    int temp=0;
    for(int i=start;i<=end;i++){
        temp=temp+a[i];
        cout << " " << a[i];
    }
    cout << endl << "sum " << temp;
}
```

