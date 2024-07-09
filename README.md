# Median-of-Two-Sorted-arrays-Leetcode
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

 

Example 1:

Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.
Example 2:

Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.


 ______________________________________________________________________________________________________________________________________________________________________________


class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        if(nums2.length==0&& nums1.length==0){
            return 0;
        }
        if(nums1.length==0){
            if(nums2.length%2==0){
                double k=nums2[(nums2.length-2)/2];
                double l=nums2[(nums2.length)/2];
                return (k+l)/2;
            }
            if(nums2.length%2!=0){
                return nums2[(nums2.length-1)/2];
            }
        }
        if(nums2.length==0){
            if(nums1.length%2==0){
                double k=nums1[(nums1.length-2)/2];
                double l=nums1[(nums1.length)/2];
                return (k+l)/2;
            }
            if(nums1.length%2!=0){
                return nums1[(nums1.length-1)/2];
            }
        }
        int nums3[]=new int [nums1.length+nums2.length];
        int k=0;
        //sorting
        for(int i=0;i<nums1.length;i++) {
            nums3[k] = nums1[i];
            k++;
            if (i + 1 == nums1.length) {
                for (int j = 0; j < nums2.length; j++) {
                    nums3[k] = nums2[j];
                    k++;
                }
            }}
        System.out.println(Arrays.toString(nums3));
        Arrays.sort(nums3);
        System.out.println(Arrays.toString(nums3));
        if(!(nums3.length%2==0)){
            return  nums3[(nums3.length-1)/2];
        }
        if(nums3.length%2==0){
            double left=nums3[(nums3.length-2)/2];
            double right =nums3[(nums3.length)/2];
            System.out.println(left+" "+right);
            return  (left+right)/2;
        }
        return 576868;
    }

    }


 
