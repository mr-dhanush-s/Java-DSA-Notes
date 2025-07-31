# 15 Binary Search Interview Questions - Google, Facebook, Amazon


LEET CODDE  
Q1: 162. Find the Peak Element  
Q2: 852. Peak index in a Mountain Array  
Q3: 744. Find the smallest letter greater than target [link](#q3-744-find-the-smallest-letter-greater-than-target)  
Q4: First and last positon of the element in sorted array [link](#q4-34-first-and-last-positon-of-the-element-in-sorted-array)

patterns like
- sliding window
- hash maps
- binary search
- 2 pointers
- n sorted arrays
- 0 1 nap sac
- based on heaps
- kv merge
- interval problems

### Q:1 FIND THE CEILING OF A NUMBER
- Find the minimum number and check which is greater than or equal to target number.

![](Images/Screenshot%20(1).png)


### MY SOLUTION
```java
public class Main {
	public static void main(String[] args) {
		int a[] = {2, 3, 5, 9, 14, 16, 18};
		System.out.println(ceil(a, 15));
	}
	public static int ceil(int a[], int tar) {
		int s = 0;
		int e = a.length-1;
		int m = 0;
		while(s<=e) {
			m = (s+(e-s)/2);
			if(tar == a[m])
				return a[m];
			else if(tar<a[m])
				e = m-1;
			else if(tar>a[m])
				s = m+1;
		}
		if(m<a.length-1)
		    return a[m+1];
		return -1;
	}
}
```


![](Images/Screenshot%20(3).png)
### KUNAL SOLUTION
```java
public class Main {
	public static void main(String[] args) {
		int a[] = {2, 3, 5, 9, 14, 16, 18};
		System.out.println(ceil(a, 15));
	}
	public static int ceil(int a[], int tar) {
		if(target > arr[arr.length-1])
			return -1;
		int start = 0;
		int end = a.length-1;
		int mid = 0;
		while(start<=end) {
			mid = (start+(end-start)/2);
			if(tar == a[mid])
				return a[mid];
			else if(tar<a[mid])
				end = mid-1;
			else if(tar>a[mid])
				start = mid+1;
		}
	    return start;
	}
}
```

<br><br>


### Q:2 FIND FLOOR OF A NUMBER
Floor is a greater number which is smaller or equal to target


![](Images/Screenshot%20(4).png)
![](Images/Screenshot%20(5).png)

### KUNAL SOLUTION
```java
public class Main {
	public static void main(String[] args) {
		int a[] = {2, 3, 5, 9, 14, 16, 18};
		System.out.println(ceil(a, 15));
	}
	public static int ceil(int a[], int tar) {
		int start = 0;
		int end = a.length-1;
		int mid = 0;
		while(start<=end) {
			mid = (start+(end-start)/2);
			if(tar == a[mid])
				return a[mid];
			else if(tar<a[mid])
				end = mid-1;
			else if(tar>a[mid])
				start = mid+1;
		}
	    return end;
	}
}
```


### Q3: 744. Find the smallest letter greater than target
1. Excatly same approach for ceiling of a number
2. Ignore the target = what we are looking for
3. Arr = ['c', 'd', 'f', 'j'] , target = 'j'
   1. Then return the 1st element

![](Images/Screenshot%20(6).png)
![](Images/Screenshot%20(7).png)

### KUNAL SOLUTION
```java
public class Main {
	public static void main(String[] args) {
		char a[] = {'c', 'd', 'f', 'j'};
		System.out.println(ceilChar(a, 'j'));
	}
	public static char ceilChar(char a[], char tar) {
		int start = 0;
		int end = a.length-1;
		int mid = 0;
		while(start<=end) {
			mid = (start+(end-start)/2);
			if(tar < a[mid])
				end = mid - 1;
			else
				start = start + 1;
		}
	    return a[start % a.length];
	}
}
```


<br><br>

### Q:4 34 First and last positon of the element in sorted array


BRUTE FORCE APPROACH  
1. Start searching the target from o to end and end to last(uses 2 pointer approach)
   1.  Time complexity is O(N)
2. use the count variables and if conditions

OPTIMISED SOLUTION/ APPROACH
1. Here we are going to run the **Binary Search** twice where as it is also **log N** where **(log N + log N) = 2log N**, If the constants are ignored then **log N** only.

### KUANL SOLUTION
```java
import java.util.*;

class Main{
	public static void main(String args[]){
		int a[] = {5, 7, 7, 8, 8, 10};
		int res[] = searchRange(a, 7);
		System.out.println(Arrays.toString(res));		
	}
    public static int[] searchRange(int[] nums, int target) {
        int ans[] = {-1, -1};
        ans[0] = solve(nums, target, true);
        // if we don't know the 1st occurance then we no need to search for 2nd occurance
        if(ans[0]!=-1)
        ans[1] =  solve(nums, target, false);
        return ans;
    }
    // this function returns the index of target
    public static int solve(int nums[], int target, boolean findFirstOccurance){
        int res = -1;
        int start = 0;
        int end = nums.length - 1;
        while(start<=end){
            int mid = start + (end - start)/2;
            if(target<nums[mid])
                end = mid - 1;
            else if(target > nums[mid])
                start = mid + 1;
            else{
                res = mid;
                if(findFirstOccurance){
                    end = mid - 1;
                }
                else {
                    start = mid + 1;
                }
            }
        }
        return res;
    }
}
```