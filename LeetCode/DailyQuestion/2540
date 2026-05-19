class Solution:
    def getCommon(self, nums1, nums2):
        first = 0
        second = 0

        # Traverse through both arrays with two pointers
        # Increment the pointer with a smaller value at that index
        # Return the first common element found
        while first < len(nums1) and second < len(nums2):
            if nums1[first] < nums2[second]:
                first += 1
            elif nums1[first] > nums2[second]:
                second += 1
            else:
                return nums1[first]

        # Return -1 if there are no common elements
        return -1
