class Solution:
    def subarraySum(self,n,k):
        c=0
        t=len(n)
        for i in range(t):
            s=0
            for j in range(i,t):
                s=s+n[j]
                if s==k:
                    c=c+1
        return c
        
        
        
    OR
    
class Solution:
    def subarraySum(self, num: List[int], k: int) -> int:
        n=len(num)
        if n==0:
            return 0
        count=0
        d={}
        curr_sum=0
        for i in range(n):
            curr_sum+=num[i]
            if(curr_sum==k):
                count+=1
            if(curr_sum-k in d):
                count+=d[curr_sum-k]
            if(curr_sum in d):
                d[curr_sum]+=1
            else:
                d[curr_sum]=1
        return count
            
