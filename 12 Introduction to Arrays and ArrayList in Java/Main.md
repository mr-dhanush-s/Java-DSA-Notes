# 12 Introduction to Arrays and ArrayList in Java

### Why we need Arrays

Q1: To store a roll number  
`int roll = 10;`

Q2: To store a person's name  
`String name = "michael";`

Q3: To store a 5 roll numbers  
```
int roll1 = 23;
int roll2 = 34;
itn roll3 = 343;
```

### Arrays:
- Array is a collection of similar type of data.
###### Syntax:
==datatype[] variable_name = new datatype[size];==

![](Images/Screenshot%20(109).png)

Note:
1. datatype --> it represents what type of data to be stored in an array.
2. There is no other type of data to be stored. And there is no combination of other data are stored like {int, int, string, char};
---

- New keyword is used to create the memory at the runtime or 
- Creating the object in the Heap memory.

---


![](Images/Screenshot%20(110).png)
- In other languages c, c++ for **array** there will be a continous memory allocation for each and every block of an array.
- In java there no concept of pointers. It totally depends on the JVM wheather it will be stored continously or not.
1. Array objects are stored in the Heap memory.
    - JLS - Java Language Specification ---> They mentioned that the heap memory are not continous.
2. The heap memory are not continous.
3. Dynamic Memory Allocation.
#### Hence: May not be continous ---> it depends on the JVM

---

The data/elements of the array are accessed using the index.

- For the Integer array by default 0 is stored internally for all the elements
like `[0, 0, 0, 0, 0]`

- In the String array by default 0 is stored internally for all the elements
like `[null, null, null, null, null]`
    - *null* is not a keyword, it is a special literal/(type of value) of null type.
    - We can't assign it to the **primitive** but we can assign it to the **non-primitive datatype**
    - **none** in python


---
We can use the for loops in array:

for loop and for each loop

for each loop -> enhanced loop

1. Array of Primitives

![](Images/Screenshot%20(111).png)


`System.out.println(Array.toString(arr))`
It is the **toString** method inside the **array class** to print the array

2. Array of Objects(String,etc...)
![](Images/Screenshot%20(112).png)




- Arrays are mutalble in java
    - If we change the object arr[0] th value then it will change in the original array too.

![](Images/Screenshot%20(113).png)
![](Images/Screenshot%20(114).png)

---

### Multi Dimentional array
1. 2D array
![](Images/Screenshot%20(115).png)
![](Images/Screenshot%20(116).png)
![](Images/Screenshot%20(117).png)


- The size of the inner array can be varry.


![](Images/Screenshot%20(118).png)
![](Images/Screenshot%20(1179).png)
![](Images/Screenshot%20(120).png)

### Enhanced for loop for an array:
![](Images/Screenshot%20(121).png)
- In an array then nested array is a array(non primitive) type of data.


--- 
--- 
# Arraylist

- It is in the util package
`import java.util.ArrayList;`

### why we need an Arraylist
1. Array is of fixed size length but In arraylist the length of the arraylist is handled by the java so, we can input N number of element.
2. It is the part of the colleciton framework but in c,c++ it is similar to vector.

SYNTAX:

`ArrayList<DataType> variable_name = new ArrayList<Datatype optional>();`

`ArrayList<Integer> list = new ArrayList<>();`  
\------------------------------------------constructor-----




### what is collection:
    - Collection is a framework in java it contains the classess and interfaces which is used to handle the data effectively in a data structure
    - data structures like hashmap, map, set, linked list, stack, queue, etc...


---
`ArrayList<Integer> list = new ArrayList<>(10);`  
here we can pass the default size(inital capacity   ) as well which is 10 here  

`ArrayList<> list = new ArrayList<>(10);`  
- Not mentioning the type of data is ok but it is not a good practice.
- we cannot pass the primitives we need to pass the ==warpper classess==

![](Images/Screenshot%20(122).png)

### To add the values
```
list.add(1);
list.add(2);
list.add(3);
list.add(4);
```

### The value is present or not
```
System.out.println(list.contains(4));
// true
```

### Insert value at specific index
```
list.set(INDEX, VALUE);
list.set(0, 99);
```


### Remove the value
```
list.remove(INDEX);
list.remove(0);
```


### Add the values and print it using for loop and 
![](Images/Screenshot%20(123).png)

- pass index here, **list[index]** will not work here.


---
## How the arraylist is working internally:
- In array we have talked about the list of references.
- Array of objects.

1. In reality the size of the ArrayList is fixed.
2. Says arraylist is fixed with some amount(half full)
    - It will create a new Arraylist of double the size
    - old elements are copied in the new Arraylist and the old arraylist is deleted.

### why this is constant time complexity O(1) or (amountized time complexity)

----


### Multiple Dimensional ArrayList
```
ArrayList<ArrayList<Integer>> list = new ArrayList<>();
```



![](Images/Screenshot%20(124).png)

- we need to initallize the inner ArrayList using ==for loop==


---

### swaping the elements in an array
![](Images/Screenshot%20(125).png)



### Maximum of an arrray

### Maximum of an array in a particular index range (1,5)

### reverse the array
![](Images/Screenshot%20(126).png)
