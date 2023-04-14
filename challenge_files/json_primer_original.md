Think back to the web services lesson from two chapters ago. Remember the part which
discussed the possible data formats that a RESTful service supports? It listed things like plain text
and binary, but also JSON. This lesson covers JSON (pronounced Jay-son), a very common and elegant way of formatting data.


Even though it sounds like it, JSON was not created and named by someone called Jason. Instead, JSON is short for JavaScript
Object Notation. The acronym may specify JavaScript, but JSON is widely adopted and is used
far beyond the world of JavaScript. One of the reasons it is so widely adopted is because of its simplicity.
JSON assigns roles and meaning to a few different symbols to create a standalone & comprehensive data format.
We'll cover these symbols and the formatting rules in this lesson.

<div class="alert alert-info" role="alert">
  <strong>Info:</strong> One of JSON's biggest pros is that it plays exceptionally well with the
  Object Oriented Paradigm. Before JSON web-services used XLM (Extensible Markup Language) which does this
  much less gracefully, is less expressive and is harder to read.
</div>

Below you can see a sample of some JSON. Take a look but don't be overwhelmed. We'll pick it apart bit by bit.

```json
  {
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
      "street": "Kulas Light",
      "suite": "Apt. 556",
      "city": "Gwenborough",
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  }
```

JSON indicates the beginning and end of data with curly brackets. You can see this in the example above.
Make sure you don't ignore these tags. It can cause some confusing errors.

Starting with the basics, you can see that the actual data is stored in key-value pairs.
Like the username line in the example above, the key is a variable name and must be surrounded
with quotation marks. The key is then followed with a colon which tells
JSON **parsers** that the data assigned to that key begin here.

<div class="alert alert-info" role="alert">
  <strong>Info:</strong> A parser is a service which can pull apart and translate certain data
  formats like JSON.
</div>

After the colon the data begins. Depending on the data type, you may have to surround
it with quotation marks. The general rule is if the datatype is anything other than a
number, a boolean or null, it needs quotes.

Putting this together, the key-value format is:

`"{insert_key}": {insert_number}`

OR

`"{insert_key}": "{insert_String}"`

OR

`"{insert_key}": {true/false}`

OR

`"{insert_key}": null`


You just learnt how to express a single piece of data in JSON, but we want to be
able to save more than just one field in a file. In order to do this, JSON employs commas
to separate fields. Here's what it looks like:

"{insert_key}": {insert_number},
"{insert_key}": "{insert_String}",
"{insert_key}": {true/false}

Notice how the final key-value pair does not have a comma.

As you know, Arrays are some of the most intensely used coding data structure out there. They are great
tools and so JSON needs a way to express them as well. Arrays in JSON are begin and end with square brackets and
each piece of data in the array is separated by a comma. Here's an example:

```json
[
1573857,
2573852,
3573959
]
```

Keep in mind that the same quotation datatype rules laid out for key-value pairs still hold
true for data embedded in an Array. An array with String values it would look
like this:

```json
[
"this is part of the example",
"this is another part of the example",
"this is another another part of the example"
]
```

<div class="alert alert-info" role="alert">
  <strong>Info:</strong> Arrays can contain any type of data. You can mix and match data types within Arrays
  (even though this is not recommended. You'll see why later.) and can even embed an array within an array.
</div>

You now know what a JSON array looks like, but how do they fit it into the overall key-value structure?
To do this, it may be easier to imagine that Arrays are just another datatype like String and booleans. Following this reasoning,
Strings or numbers in JSON key-value pairs only need to be replaced by an Array. Take a look:

```json
{
"thisIsAKey": null,
"thisIsAlsoAKey": [
  "this",
  "is",
  "an",
  "array",
  "of",
  "strings"
]
}
```

This lesson previously mentioned that JSON plays very well with the Object Oriented Paradigm, but so far
we haven't mentioned or seen the JSON equivalent of an object. Let's fix that and really bring JSON to life.

To indicate the start of an object and end of an object JSON uses **{** and **}** respectively.
This is similar to an array except that a JSON object is much more flexible. Instead of just storing
data points a JSON object can store key-value pairs. This means that I can embed objects within objects and
arrays within objects. Let's see what this looks like:

```json
{
"name": "Ben",
"firstObject": {
      "embeddedKey": true,
      "embeddedArray": [
            1,
            2,
            3,
            4
      ],
      "embeddedObject": {
            "embeddedKeyWithinAnObjectWithinAnObject": 4759385,
            "thatLastKeyWasLong": "very long"
      }
}
}
```

The above JSON begins with a simple key-value pair with key "name" and value "Ben". The next key-value pair
is called firstObject and it stores an object with 3 fields, a key-value pair called embeddedKey with value true,  
an array named embeddedArray which stores the values 1,2,3 and 4, and another object named embeddedObject. 
embeddedObject in turn contains 2 primitive key-value pairs.


To understand how to send single values in JSON, we need to revisit the opening ({) and closing (})
tags for JSON data. To kickstart this JSON explanation it was easier to call these
curly brackets opening and closing tags. However, they are not really tags. Instead, they
indicate the start of an object. So almost anything you send in JSON is technically an object.

There are 2 exceptions to this rule:

When sending a primitive variable, you are not required to include these two brackets.
But if you decide to omit them, you won't be able to include a key. You can only enter a value. This
isn't really JSON anymore, but it works.

When sending a single array you can also leave out the two curly brackets. They are
effectively replaced by square brackets to indicate the beginning of the array, but just like sending a
primitive datatype you can no longer include a key. Here's an example (enjoy the captivating lorem ipsum):

```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum temporen debitis possimus qui neque nisi nulla"
  },
  {
    "userId": 1,
    "id": 3,
    "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
    "body": "et iusto sed quo iure voluptatem occaecati omnis eligendi"
  },
  {
    "userId": 1,
    "id": 4,
    "title": "eum et est occaecati",
    "body": "ullam et saepe reiciendis voluptatem luptatem rerum illo velit"
  }
]
```

The example above not only illustrates how to express a single array in JSON but also how to
store objects within arrays.

