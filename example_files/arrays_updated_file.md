# What are Java Arrays?
The `Arrays` class is used to create an array, which is a collection of variables of the same type. Arrays are data structures primarily used to store and manipulate data.  

It is important to remember that `Arrays` are part of the `Object` class. (We'll cover `Object`s in depth shortly.)

## How to Create an Array in Java?
When you create an array, you will specify three things:
1. The type of data it will hold
2. Its name
3. Its size

Therefore to declare a 1D array you use the following syntax:
```java
type[] array_name = new type[size];
```

### Java Array Example
The array name will help us to make references and manipulate the array as you would do with any other variable, so it is important to choose a self-explanatory name.

For example, to create an array to store test scores for 10 students, you could declare an array of `int` as:

```java
int[] scores = new int[10];
```

## How do you Insert Data into a Java Array?
In the previous example, you created an array with 10 spots, however, you did not assign it any values. We can assign values after the declaration of an array or, you can initialize the array with values when you create it. To initialize the array `scores` with values:  

```java
int[] scores = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

Now, accessing the second index of array `scores`, gives the value 2:

```java
scores[1]; // returns the value 2
```

So the second index is 1? Great question! 

### What is a Java Array Index?
Each spot in an array has a specific index. Indexes start at 0 and go to the length of the array minus one. 

For example, an array of size 10, has indexes 0 to 9. The following image illustrates this example.

<img alt='An infographic displaying how an array with 10 elements is counted and indexed' class='cn_image img_responsive' src='https://raw.githubusercontent.com/CodingNomads/static/main/java_programming/arrays/array_description.png?raw=true'/>

To access an array index you use the name of the array followed by brackets with the index inside. To access the third element in the array `scores`, you use the statement:

```java
int x = scores[2];
```

The trick is to remember, is that the index is always the number of the element that you want minus 1 - that's what happens when you start counting with 0!

## What Can you Do with Java Arrays?
`Arrays` in Java come built with several functions that can be called to get information or manipulate the array.


### Arrays and For Loops
`Arrays` and `for` loops are a match made in heaven :)

`for` loops are perfect for iterating through `Arrays` because they have a built-in counter that you can use as an index for your `Arrays`.  

Take a look at the example below:

```java
public static void main(String[] args) {

    int[] vals = {456, 234, 987, 876, 123};

    for (int i = 0; i < vals.length; i++){

        // here, we'll use the counter variable "i" from the for loop to access an element in the array

        System.out.println(vals[i]);

    }

}

/* OUTPUT

\--------------------

456

234

987

876

123

*/ 
```

As you can see, the iterator `i` can be placed at the index spot for the array, so that each loop will move to the following index in the array; pretty awesome isn't it! 

### How to Get the Length of an Array
A very useful and common functionality built into the `Arrays` class is the `.length` attribute. Notice it is **not a method**, (i.e. you don't write `getLength()`) and therefore does not have a parenthesis behind it. The `.length` attribute is a variable that contains the total length of the array.  

```java
public class Example {

    public static void main(String[] args){

        // instantiate new int array with length of 5

        int[] vals = new int[5];

        // print out the length of the array

        System.out.println("the length of the array is: " + vals.length);

        // loop through the array

        for (int i = 0; i < vals.length; i++){

            // populate each index of the array with the value of "i"

            vals[i] = i;

        }

        // for each int in "vals"

        for (int i : vals){

            // print out the value

            System.out.print(i);

        }

    }

}

/*

Output:

\-----------------------------------------------

the length of the array is: 5

01234*/  

```

## Summary: What are Java Arrays
- `Arrays` are collections of variables of the same type
- `Arrays` are created by defining their type, name and size
- `Arrays` come with several built-in functionalities
- The index of an array is the numerical address of each value, starting from 0 instead of 1
- The `for` loop is perfect for iterating through `Arrays`
- The `.length` attribute returns the length of the array

### Syntax
Here's the syntax for creating an array, where you can substitute the variables starting with `your_`  with your values.
```java
your_type[] your_array_name = new your_type[your_size];
```