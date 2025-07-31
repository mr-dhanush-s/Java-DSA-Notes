## 14 Binary Search Algorithm - Theory + Code

### Very very important topic

It is mostly possible in the sorted array either in ascending or descending order.


- In linear search the worst case is O(n) where we need to traverse the entire array.

![](Images/Screenshot%20(132).png)

Search for 36 in the array
![](Images/Screenshot%20(133).png)

![](Images/Screenshot%20(134).png)
![](Images/Screenshot%20(135).png)

Now search for 12

![](Images/Screenshot%20(136).png)
![](Images/Screenshot%20(137).png)


---
### WHY WE NEED BINARY SEARCH
Q: find the maximum number of search comparisions in the worst case 
![](Images/Screenshot%20(138).png)
![](Images/Screenshot%20(139).png)
![](Images/Screenshot%20(140).png)
- we can remove the constant 2 which in the base


1. BEST CASE TIME COMPLEXITY IS O(1)
2. WORST CASE TIME COMPLEXITY IS O(log N)


---
<br>
<br>
<br>
<br>


### My solution
```java
class Main {
    public static void main(String[] args) {
        int arr[] = {2,4,6, 9, 11, 12, 14, 20, 36, 40};
        int tar = 6;
        System.out.println(binarySearch(arr,tar));
    }
    
    public static int binarySearch(int arr[], int target){
        int start = 0;
        int end = arr.length-1;
        while(start<=end){
            int mid = (start+end)/2;
            if(arr[mid] == target)
                return mid;
            else if (target<arr[mid])
                end = mid-1;
            else if(target>arr[mid])
                start = mid+1;
        }
        return -1;
    }
}
```


### Kunal solution:
```java
    public class Main{
        public static void main(String args[]){
            int arr[] = {-18, -12, -4, 0, 2, 3, 4, 15, 16, 18, 22, 45, };
            int answer = binarySearch(arr, 22);
            System.out.println(answer);
        }
        
        // return the index if exist
        // return -1 element not exist
        public static int binarySearch(int arr[], int target){
            int start = 0;
            int end = arr.length-1;
            while(start<=end){
                // find the middle
                //int mid = (start+end) / 2; // may be possible that (start+end) will exceeds the integer data type range
                // to optimize this mid value
                int mid = start + (end-start) / 2;
                
                if(target < arr[mid])
                    end = mid - 1;
                else if(target > arr[mid])
                    start = mid + 1;
                else
                    // answer found 
                    return mid;
            }
            return -1;
        }
    }
```
![](Images/Screenshot%20(143).png)
---
<br>
<br>
<br>
<br>


### MODIFIED CODE FOR DESCENDING ORDER SORTED ARRAY

![](Images/Screenshot%20(144).png)







---
<br>
<br>
<br>
<br>

### ORDER AGNOSTIC BINARY SEARCH
Here we don't know that an array is sorted ascending or descending order.

![](Images/Screenshot%20(145).png)


```java
public class Main{
    public static void main(String args[]){
        int arr[] = {-18, -12, -4, 0, 2, 3, 4, 15, 16, 18, 22, 45, };
        //int arr[] = {5, 4, 3, 2, 1};
        int target = 2;
            int answer = arr[0]<arr[arr.length-1]?aBinary(arr, target):dBinary(arr,target);
            System.out.println(answer);
    }
    public static int aBinary(int arr[], int target){
       int start = 0;
        int end = arr.length-1;
        while(start<=end){
            int mid = start + (end-start) / 2;
            if(target<arr[mid])
                end = mid - 1;
            else if(target > arr[mid])
                start = mid + 1;
            else
                // answer found 
                return mid;
            }
            return -1; 
    }
    
    public static int dBinary(int arr[], int target){
        int start = 0;
        int end = arr.length-1;
        while(start<=end){
            int mid = start + (end - start) / 2;
            if(target>arr[mid])
                end = mid - 1;
            else if(target < arr[mid])
                start = mid + 1;
            else
                return mid;
        }
        return -1;
    }
}
```

--- 
### Kunal Solution:
```java
public class Main{
    public static void main(String args[]){
        //int arr[] = {-18, -12, -4, 0, 2, 3, 4, 15, 16, 18, 22, 45, };
        int arr[] = {5, 4, 3, 2, 1};
        int target = 2;
        int answer = binary(arr, target);
        System.out.println(answer);
    }
    
    public static int binary(int arr[], int target){
        int start = 0;
        int end = arr.length-1;
        boolean isAsc = arr[0]<arr[arr.length-1];
        while(start<=end){
            int mid = start + (end-start) / 2;
            if(arr[mid] == target)
                return mid;
            if(isAsc){
                if(target<arr[mid])
                    end = mid - 1;
                else
                    start = mid + 1;
            }
            else{
                if(target>arr[mid])
                    end = mid - 1;
                else
                    start = mid + 1;
            }
            
            }
            return -1; 
    }
}
```