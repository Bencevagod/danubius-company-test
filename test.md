# Danubius Test

## Short questions

- What is GIT? What is it used for and what kind of
situations is it designed to solve/make it easier?

```
Git is a software which can handle versions of given software. It can solve team projects, where people can make branches and then make a whole from the branches, and also helps in managing versions of given software under development as stated above.
```

- What is HTTP? What kind of HTTP methods are you
familiar with? What are their characteristics?

```
HTTP is a protocol used on the internet. GET - browsers usually send this when browsing the net, it is getting data from the server. POST - sending data to the server for future usage e.g. registration or logging in. PUT - sending data to update existing one. DELETE - delete data from server.
```

- What is the difference between HTTP and HTTPS?

```
HTTPS is the Secure type of the normal HTTP protocol, it is basically encrypted communication between the client and the server.
```

- What do you know about the following HTML tags?
What are their characteristics and when do we use them?
  - `<div>`
  - `<span>`
  - `<p>`
  - `<a href="...">...</a>`

  ```
  Div is a container used to store tags in them, it is a block element.
  Span is a container that is meant to wrap text.
  P is stands for paragraph, so it is the body of the text on a webpage. It is a block element.
  <a> is stands for anchor, it provides a link given in the href attribute, and will happily route there if clicked. A div or a span can be put in an <a> tag, so the whole becomes a link.
  ```

- What do you know about dependency injection?
What is it used for? What is its advantage?

```
Dependency injection is made to help with instatiation. For example in Java if we want to use a class' method, first we need an object from that class. Dependeny injection solves this with instatiating an object for us in the background, so we can use the given class' methods.
In backend it is widely used because of the MVC architecture.
```

- Briefly describe a current topic in the IT field
that you are interested in!

```
Webassembly is a great development over Javascript, which can be used for even more powerful web apps.
It can translate other programming laungages to bytecode which the browsers can understand, without the limiting factor of Javascript's one threadedness. This way AutoCad was able to use their c++ code to have a fully working CAD application runing in a browser.
```

## Programming task

Given a table that contains units and multipliers
that belongs to them. The multipliers tell you what
is the number that you need to multiply the value
with if you'd like to calculate the base unit.
The base units for example: liter, meter, etc...
Those that doesn't have a metric prefix.

### Length

| Unit | Value |
|------|-------|
| mm   | 0.001 |
| cm   | 0.01  |
| dm   | 0.1   |
| m    | 1     |
| km   | 1000  |

### Weight

| Unit | Value   |
|------|---------|
| mg   | 0.001   |
| g    | 1       |
| dkg  | 10      |
| kg   | 1000    |
| t    | 1000000 |

### Task

Create a data structure(could be a class but also
any type of combination of primitive types, array,
but also the series of well named variables) which
is suitable to store the values in the table and
makes the implementation of the exercises below easier(You don't have to
implement the actual operations they are just there
as an example).

- List a given type(e.g.: Length) of measurement units.
For example: mm, cm, dm, m, km
- Query of the multipliers.
For example: input -> km, output -> 1000
- Given an actual unit, return the value in the base unit.
For example: input -> "1200 cm", output -> 12

Initialize the datastructure with example inputs.

```java
class Metrics {
  list containing length_units = [mm, cm, dm, m, km]
  list containing length_values = [0.001, 0.01, 0.1, 1, 1000]
  list containing weight_units = [mg, g, dkg, kg, t]
  list containing weight_values = [0.001, 1, 10, 1000, 1000000]

  method to list given type (type) {
    check if type is really existing, then;
    print(type_units);
  }

  method to query multipliers (type, unit) {
    check type existence;
    for (int i = 0; i < type_units.length; i++) {
      check if unit exists, if not return a message;
      if unit exists { 
        return type_values[i];
      }
    }
  }

  method to change to base unit(string) {
    first we split the string by the space;
    it's first will be casted and saved into a variable called int numPart;
    the unit part will be svaed into a variable called unitPart;
    we need a variable called unitIndex to store the index of unitPart in it's list
    String list_of_values = "";

    check _values lists for our unitPart;
    for (int i = 0; i < 2; i++) {
      for (int j = 0; j < length_units.length; j++) {
        if unitPart equals length_units[j] {
          unitIndex = j;
          list_of_values = length_units (splitted by _) + _values;
        }
      }
      for (int j = 0; j < weight_units.length; j++) {
        if unitPart equals weight_units[j] {
          unitIndex = j;
          list_of_values = weight_units (splitted by _) + _values;

        }
      }
    }

    return numPart * list_of_values[unitIndex];

  }
}
```