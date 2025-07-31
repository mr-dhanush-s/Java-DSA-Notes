## 13 Linear Search Algorithm - Theory + Code + Questions


Linear search is used to iterate over the array to search for a particular element/value.
#### Time complexity
##### Best Case:
O(1)  - here the value is present in the 0 th index

##### Worst Case:
O(n) - We do not find the item/value/element

---

Auxilaury space - Extra space taken like use an another array.

![](Images/Screenshot%20(128).png)
![](Images/Screenshot%20(129).png)
![](Images/Screenshot%20(130).png)


### Search in Array of Integer data

```java

class Main {
    public static void main(String[] args) {
        int arr[] = {1, 4, 3, 2, 5, 7, 8, 6};
        int tar = 5;
        System.out.println(findElement1(arr,tar)); // true
        System.out.println(findElement2(arr,tar)); // 4
        
    }
    public static boolean findElement1(int arr[], int target){
        for(int i:arr){
            if(i==target)
                return true;
        }
        return false;
    }
    
    public static int findElement2(int arr[], int target){
        for(int i=0;i<arr.length;i++){
            if(arr[i]==target)
                return i;
        }
        return -1;
    }
}
```


### Search in Array of String Data:

```java

class Main {
    public static void main(String[] args) {
        String s = "Hello world!";
        char tar = 'r';
        System.out.println(findElement1(s,tar)); // true
        System.out.println(findElement2(s,tar)); // 8
        
    }
    public static boolean findElement1(String s,char tar){
        for(char ch:s.toCharArray()){
            if(ch==tar)
                return true;
        }
        return false;
    }
    
    public static int findElement2(String s, char tar){
        for(int i=0;i<s.length();i++){
            if(tar==s.charAt(i))
                return i;
        }
        return -1;
    }
}

```

---
<br><br><br>

### SEARCH IN RANGE
Q: Search for 3 in the range of index[1,4]
```java

class Main {
    public static void main(String[] args) {
        int arr[] = {1, 4, 3, 2, 5, 7, 8, 6};
        int tar = 5;
        int start = 1;
        int end = 4;
        System.out.println(findElement1(arr,tar)); // true
        System.out.println(findElement2(arr,tar)); // 4
        
    }
    public static boolean findElement1(int arr[], int target){
        for(int i:arr){
            if(i==target)
                return true;
        }
        return false;
    }
    
    public static int findElement2(int arr[], int target){
        for(int i=start;i<end;i++){
            if(arr[i]==target)
                return i;
        }
        return -1;
    }
}
```

---
<br><br><br>

### FIND MINIMUM NUMBER IN ARRAY
```java
class Main {
    public static void main(String[] args) {
        int arr[] = {18, 12, -7, 3, 14, 28};
        System.out.println(findMin(arr));
        
    }
    
    public static int findMin(int n[]){
        int min = Integer.MAX_VALUE;
        for(int i=0;i<n.length;i++){
            if(n[i]<min)
                min = n[i];
        }
        return min;
    }
}
```


### FIND MAXIMUM NUMBER IN ARRAY
```java
class Main {
    public static void main(String[] args) {
        int arr[] = {18, 12, -7, 3, 14, 28};
        System.out.println(findMax(arr));
        
    }
    
    public static int findMax(int n[]){
        int max = Integer.MIN_VALUE;
        for(int i=0;i<n.length;i++){
            if(n[i]>max)
                max = n[i];
        }
        return max;
    }
}
```

--- 
<br><br><br><br>






### SEARCH IN 2D ARRAY
- int arr[][] = new int\[ ]\[ ]{
            {23, 4, 1},
            {18, 12, 3, 9},
            {78, 99, 34, 56},
            {18, 12}
        };  
- or 
- int arr[][] = {
            {23, 4, 1},
            {18, 12, 3, 9},
            {78, 99, 34, 56},
            {18, 12}
        };
- both are same

---
- we need to initialise the array before return so, we can also create the object in the return statement.  
`return new int[]{value1,valueN};`
```java
import java.util.*;
class Main {
    public static void main(String[] args) {
        int arr[][] = {
            {23, 4, 1},
            {18, 12, 3, 9},
            {78, 99, 34, 56},
            {18, 12}
        };
        int tar = 34;
        int ans[] = search2dArray(arr,tar);
        System.out.println(Arrays.toString(ans));
    }
    
    public static int[] search2dArray(int arr[][], int tar){
        for(int i=0;i<arr.length;i++){
            for(int j=0;j<arr[i].length;j++){
                if(tar == arr[i][j])
                    return new int[]{i,j};
            }
        }
        return new int[]{-1,-1};
    }
}
```
---
<br><br><br><br>


### MAXIMUM ELLEMENT IN 2D ARRAY

```java
import java.util.*;
class Main {
    public static void main(String[] args) {
        int arr[][] = {
            {23, 4, 1},
            {18, 12, 3, 9},
            {78, 99, 34, 56},
            {18, 12}
        };
        System.out.println(maxIn2dArray(arr));
    }
    
    public static int maxIn2dArray(int arr[][]){
        int max = Integer.MIN_VALUE;
        for(int i=0;i<arr.length;i++){
            for(int j=0;j<arr[i].length;j++){
                if(arr[i][j]>max)
                    max = arr[i][j];
            }
        }
        return max;
    }
}
```

---

### MINIMUM ELEMENT IN 2D ARRAY

```java
import java.util.*;
class Main {
    public static void main(String[] args) {
        int arr[][] = {
            {23, 4, 1},
            {18, 12, 3, 9},
            {78, 99, 34, 56},
            {18, 12}
        };
        System.out.println(minIn2dArray(arr));
    }
    
    public static int minIn2dArray(int arr[][]){
        int min = Integer.MAX_VALUE;
        for(int i=0;i<arr.length;i++){
            for(int j=0;j<arr[i].length;j++){
                if(arr[i][j]<min)
                    min = arr[i][j];
            }
        }
        return min;
    }
}
```

---
<br><br><br>






### NUMBER OF ELEMENT CONTAINS EVEN DIGITS IN AN ARRAY

```java
class Main {
    public static void main(String[] args) {
        int arr[] = new int[]{12, 345, 2, 6, 7896};
        System.out.println(evenCount(arr));
    }
    
    public static int evenCount(int arr[]){
        int c = 0;
        for(int i:arr){
            if(evenDigit(i))
                c++;
        }
        return c;
    }
    
    public static boolean evenDigit(int n){
    int count = 0;
    while(n!=0){
        count++;
        n/=10;
    }
    if(count%2==0)
        return true;
    return false;
    }
}

```


---
<br><br><br>

### Optimized code 
To optimize and get the number of digits in a number use
`Math.log10(<number>)+1`  
- if we need binary representaion use log2
- for octal use log8

```java
class Main {
    public static void main(String[] args) {
        int arr[] = new int[]{12, 345, 2, 6, 7896};
        System.out.println(findNumbers(arr));
    }
    
    public static int findNumbers(int arr[]){
        int count = 0;
        for(int num:arr){
            if(even(num))
                count++;
        }
        return count;
    }
    
    public static boolean even(int num){
        int numberOfDigits = digits(num);
        digits2(num);
        if(numberOfDigits%2==0)
            return true;
        return false;
    }
    
    
    // To optimise this digits function
    
    public static void digits2(int num){
        System.out.println((int)Math.log10(num)+1);
    }
    
    public static int digits(int num){
        if(num<0)
            num = num * -1;
        if (num==0)
            return 1;
        
        int count = 0;
        while(num>0){
            count++;
            num/=10;
        }
        return count;
    }
}

```

