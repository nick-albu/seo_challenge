An array is a collection of variables of the same type. Arrays are data structures primarily used to store and manipulate data.  

It is important to remember arrays are Objects. (We'll cover Objects in depth shortly.)

![](https://platform.codingnomads.co/learn/draftfile.php/5/user/draft/502500267/array1.png)  

When we create an array, we will specify the type of data it will hold, its name and its size.  

To declare a 1D-array we use the following form:

```type\[\] array\_name = new type\[size\];

```

The array name will help us to make references and manipulate the array as we would do with any other variable.  

For example, to create an array to store test scores for ten students, we could declare an array of ints as:

```int\[\] scores = new int\[10\];

```

Each spot in an array has a specific index. Indexes start at 0 and go to the length of the array minus one.  

For example, an array of size ten, has indexes 0-9. To access an array index we use the name of the array followed by brackets with the index inside. For example, to access the second element in the array scores, we use the statement:

```int x = scores\[1\];

```

  

  

#### Initialization:

In the previous example, we created an array with 10 spots however, we did not assign any values to the indexes. We can assign values after the declaration of an array or, we can initialize the array with values when we create it. To initialize the array scores with values:  

```int\[\] scores = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

```

Now, accessing the second index of array scores, gives the value 2:

```scores\[1\]; // returns the value 2

```

#### Arrays and For Loops - A match made in heaven :)

For loops are perfect for iterating through arrays because they have a built in counter that we can use as an index for our arrays.  

Take a look at the example below:

```public static void main(String\[\] args) {

    int\[\] vals = {456, 234, 987, 876, 123};

    for (int i = 0; i < vals.length; i++){

        // here, we'll use the counter variable "i" from the for loop to access an element in the array

        System.out.println(vals\[i\]);

    }

}

/* OUTPUT

\--------------------

456

234

987

876

123

*/ ```

  

#### Array.length:

A very useful and common functionality built into the Array class is the ".length" attribute. Notice it is not a method, ie "getLength()". It does not have parenthesis behind it. The ".length" attribute is a variable that contains the total length of the array.  

```public class Example {

    public static void main(String\[\] args){

        // instantiate new int array with length of 5

        int\[\] vals = new int\[5\];

        // print out the length of the array

        System.out.println("the length of the array is: " + vals.length);

        // loop through the array

        for (int i = 0; i < vals.length; i++){

            // populate each index of the array with the value of "i"

            vals\[i\] = i;

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