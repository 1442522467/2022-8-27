# leetcode 1011

传送带上的包裹必须在 days 天内从一个港口运送到另一个港口。

传送带上的第 i 个包裹的重量为 weights[i]。每一天，我们都会按给出重量（weights）的顺序往传送带上装载包裹。我们装载的重量不会超过船的最大运载重量。

返回能在 days 天内将传送带上的所有包裹送达的船的最低运载能力。

```
class  Solution {

public  int  shipWithinDays(int[] weights, int  days) {

int  l = Arrays.stream(weights).max().getAsInt(), r = Arrays.stream(weights).sum();

while(l<r)

{

int  mid=l+(r-l)/2;

if(day(weights,mid)<=days)

{

r=mid;

}

else

{

l=mid+1;

}

}

return l;

  

}

public  int  day(int[] weights, int  k){

int  res=0,day=1;

for(int  i=0;i<weights.length;i++)

{

if((res+weights[i])>k)

{

day++;

res=0;

}

res+=weights[i];

}

return day;

  
  

}

}
```

