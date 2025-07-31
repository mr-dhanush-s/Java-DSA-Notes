## 11.Functions/Methods in Java

### Why we need to use the functions/methods:
- Function is a block of code.
- 



Structure of the method:

```
access_modifier return_type Method_name(){
    // statement
}
```



![](Images/Screenshot%20(90).png)


After the return statement nothing will executed in the function block

![](Images/Screenshot%20(91).png)



Function with the String return type
![](Images/Screenshot%20(93).png)




Passing the value to the function
![](Images/Screenshot%20(92).png)

NO need the value variable name and method parameter name are same(pass by value not by the reference)
![](Images/Screenshot%20(94).png)


Not changing the object, creating the object
![](Images/Screenshot%20(95).png)





### In primitive data type the value only passed
![](Images/Screenshot%20(9)6.png)

If we change the value in the function then the original value is not changed

### In non primitive data type the ref variable is passed.

![](Images/Screenshot%20(97).png)

If we change the value in the function then the original value is also changed


Strings are not modified and the values of the arrays are modified



### Scoping for method
Varibales inside the method/function will be accessed within the method/function but not the outside of the method(Local Scope).



Varibales created inside the class but outside the methods are called the global varibale(created using the static keyword).


![](Images/Screenshot%20(98).png)
![](Images/Screenshot%20(99).png)
![](Images/Screenshot%20(100).png)







---
### Shadowing:

Shadowing is the process Declaration and Initiallization of the variable with the ==same name== in both the **global** and **local** scope.

- The upper level value is just *shadowed* or *overlapped*.

![](Images/Screenshot%20(101).png)

---
### Variable length arguments

```
static void fun(<datatype> ...v){
    // statements
}
```

Here the ==...v==  things that the array of int, string, etc.. what ever the data type we mention.

- The length is varies when we pass the arguments.
- we can call the function with 0 or more than 0 arguments.

![](Images/Screenshot%20(103).png)

---
#### Multiple varibale length arguments:
we can pass int1, int2, then we can pass the array of string here.

- varibale length argument always at the end.



---
### Function overloading(compile time polymorphism(the compile time only deside which function to run))
![](Images/Screenshot%20(105).png)
Two or more functions with the same name but it will varied based on
1. Data type
![](Images/Screenshot%20(106).png)
2. number of parameters
![](Images/Screenshot%20(107).png)


### Function overriding(runtime polymorphism(which method to run is desided at the runtime))




---

### Print all the 3 digit Amstrong numbers:

![](Images/Screenshot%20(108).png)