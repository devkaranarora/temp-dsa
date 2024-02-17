
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int mxpro = 0;
        for(int i=0;i<prices.size();i++){
            for(int j=i+1;j<prices.size();j++){
                int buy = prices[i];
                int sell = prices[j];
                mxpro = max(mxpro,sell-buy);
            }
        }

        return mxpro;
	}
};
```


```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int minBuy=prices[0];
        int ans=0;
        for(int i=1;i<prices.size();i++){
            int val = prices[i];
            int profit = val-minBuy;
            ans = max(profit,ans);
            minBuy=min(minBuy,val);
        }
        return ans;
    }
};
```
