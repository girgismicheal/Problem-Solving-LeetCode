# Problem-solving
In this repo, i am trying to solve some problems with the most efficient and clear way.


```Python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        L1,L2 = 0,0  # sort the median
        L_N1 = len(nums1)
        L_N2 = len(nums2)
        count = L_N1+L_N2
        Nums = list()

        for _ in range((count)//2 +1):

            if L1 < L_N1 and L2 < L_N2:
                if nums1[L1]<=nums2[L2]:
                    Nums.append(nums1[L1])
                    L1+=1
                else:
                    Nums.append(nums2[L2])
                    L2+=1
            elif  L1 < L_N1:
                Nums.append(nums1[L1])
                L1+=1
            else:
                Nums.append(nums2[L2])
                L2+=1
        print(Nums, count)
        if count%2:
            # print(Nums[-1])
            return Nums[-1]
        
        else:
            # print((Nums[-2]+Nums[-1])/2)
            return ((Nums[-2]+Nums[-1])/2)
```
