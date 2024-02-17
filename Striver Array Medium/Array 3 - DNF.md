1 - sorting 
2 - hashing
3 - dnf


```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        sort(nums.begin(),nums.end());   
    }
};
```

```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int arr[]={0,0,0};
        for(int i=0;i<nums.size();i++){
            int val=nums[i];
            if(val==0) arr[0]++;
            if(val==1) arr[1]++;
            if(val==2) arr[2]++;
        }
        int index=0;
        while(arr[0]>0) {nums[index]=0;index++;arr[0]--;}
        while(arr[1]>0) {nums[index]=1;index++;arr[1]--;}
        while(arr[2]>0) {nums[index]=2;index++;arr[2]--;}
    }
};
```

```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int r=nums.size()-1,l=0,mid=0;
        while(mid<=r){
            if(nums[mid]==0){
                swap(nums[mid],nums[l]);
                mid++;l++;
            }else if(nums[mid]==1){
                mid++;
            }else{
                swap(nums[r],nums[mid]);
                r--;
            }
        }
    }
};
```

