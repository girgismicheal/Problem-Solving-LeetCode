# Median of Two Sorted Arrays

- O(n+m) solution
```Python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        L1,L2 = 0,0           # Two pointers to iter on each list
        L_N1 = len(nums1)     # Size of list 1
        L_N2 = len(nums2)     # Size of list 2
        count = L_N1+L_N2     
        Nums = list()         # New list to sort both lists in

        for _ in range((count)//2 +1):
            if L1 < L_N1 and L2 < L_N2: # compare and assign
                if nums1[L1]<=nums2[L2]:
                    Nums.append(nums1[L1])
                    L1+=1
                else:
                    Nums.append(nums2[L2])
                    L2+=1
            elif  L1 < L_N1:          # add rest from List 1
                Nums.append(nums1[L1])
                L1+=1
            else:                     # add resr from List 2
                Nums.append(nums2[L2])
                L2+=1

        # calculate the Median
        if count%2: 
            return Nums[-1]
        return ((Nums[-2]+Nums[-1])/2)
```
