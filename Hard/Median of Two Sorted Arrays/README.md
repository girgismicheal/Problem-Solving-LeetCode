# 4. Median of Two Sorted Arrays [Problem link](https://leetcode.com/problemset/all/?difficulty=HARD&page=1&status=AC)
- O(log(m+n) * log(max - min)) [video](https://leetcode.com/problems/median-of-two-sorted-arrays/discuss/1641789/Binary-Search-Explained)
```Python
import bisect
def findMedianSortedArrays(nums1, nums2):
        self_min = float("inf")
        self_max = float("-inf")

        if nums1:
                self_min = min(self_min, nums1[0])
                self_max = max(self_max, nums1[-1])
        if nums2:
                self_min = min(self_min, nums2[0])
                self_max = max(self_max, nums2[-1])   


        def find_nth(nth):
            left = self_min
            right = self_max

            while left < right:
                mid = left + right >> 1
                idx = bisect.bisect(nums1, mid) + bisect.bisect(nums2, mid)
                # print(left," ",right," ",right>>1," ",idx," ",bisect.bisect(nums1, mid)," ",bisect.bisect(nums2, mid))
                if idx <= nth:
                    left = mid + 1
                else:
                    right = mid
            return left

        n = len(nums1) + len(nums2)

        if n & 1:
            return 1.0 * find_nth(n//2)

        return (find_nth(n//2) + find_nth(n//2 - 1))/2.0
```
- O(n+m) solution
```Python

def findMedianSortedArrays(nums1: List[int], nums2: List[int]) -> float:
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

        if count%2:
            return Nums[-1]
        
        else:
            return ((Nums[-2]+Nums[-1])/2)
```
