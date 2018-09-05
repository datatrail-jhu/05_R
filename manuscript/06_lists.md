# Lists and Data Frames

Now that we've covered basic object types and some commands to explore and work with them, we will cover a slightly more complex type of object: lists. Lists have similarities to data frames, which we have introduced briefly in previous lessons. In this lesson, you will learn about the structure of list objects, how to create them, and how to subset them.

### What are lists in R?

Previously, you have learned about basic classes of objects in R. These included character, integer, numeric, logical, and factor objects. In particular, we covered the creation of simple vectors of objects in these classes. These simple vectors are a collection of items all of the same class. In other words, each slot of these simple vectors is a length-1 vector of the same class. The term slot and element are often used interchangeably. They both refer to a particular item within the collection.

Lists are also a type of vector, but they are more complex than the simple vectors we have learned about so far because each slot in a list can contain objects of different classes. The objects in these slots can be simple vectors, lists, or other types of objects.

Lists are a general and flexible way to store information, and it turns out that data frames, which you have learned about in previous lessons, are a special cases of lists. As you learn how to create and work with lists in the remainder of this lesson, we will also cover connections to working with data frames.

![Vectors and Lists](images/06_lists/06_R_lists-1.png)

### Creating a list

The main way to create a list from scratch in R is with the `list` function. The `list` function takes as many arguments as you want to give it and creates a list with each of the specified objects. For example, we could conduct a poll in a first grade classroom and ask students to name some numbers, animals, and colors that come to mind. In the example below, we have created a list with three slots to store the responses for a single student. In the first slot, we have a numeric vector containing three numbers. In the second, we have a character vector containing two animal names. In the third, we have a character vector containing six colors. This will create a list with three slots, where the responses in each slot are a different length.

Within the `list` function, each of these objects is separated with a comma.

```r
responses_student1 <- list(c(4,20,3), c("bear", "giraffe"), c("red", "orange", "yellow", "green", "blue", "purple"))
```

This means that the `length` *of the list* is three (one for the numbers, one for the animal names, and one for the colors), but the lengths of the responses within each list differs for each slot (3 for the numbers, 2 for the animal names, and 6 for the colors). 

When we print this object to the screen, it looks as below. The double square brackets indicate the slot number, or element number. So `[[1]]` indicates the first slot or first element of the list, and we see that this first element is a length-3 numeric vector. The `[[2]]` indicates the second element, and we see that it is a length-2 character vector. The `[[3]]` indicates the third slot, and we see that it is a length-6 character vector. The double bracket notation alludes to one way that we can access certain elements of a list. We will cover this in detail in the next section of this lesson.

```text
> responses_student1
[[1]]
[1]  4 20  3

[[2]]
[1] "bear"    "giraffe"

[[3]]
[1] "red"    "orange" "yellow" "green"  "blue"   "purple"
```

The information contained in this object would be improved with labels for the three list elements. This is achieved by adding **names** to the list. As we learned about in the Basic Commands lesson, we can do this with the `names` function.

```r
names(responses_student1) <- c("numbers", "animals", "colors")
```

Now when we display the object, we can see these labels. The double square brackets have been replaced with `$label` where `label` is one of the names that we just entered. Similar to the double bracket notation, the dollar sign notation here indicates another way that we can access certain elements of a list. We will cover this in detail in the next section of this lesson.

```text
> responses_student1
$numbers
[1]  4 20  3

$animals
[1] "bear"    "giraffe"

$colors
[1] "red"    "orange" "yellow" "green"  "blue"   "purple"
```

We can also specify the names of the list elements from the start in the `list` function. Let's create another list object that contains poll responses for a *second* student. We can specify the names as argument names in the `list` function by stating the name of each slot in the list followed by an equals sign and then the values you want in that slot in the list after. Again, each slot is separated by a comma.

```r
responses_student2 <- list(numbers = 1:5, animals = c("T-rex", "tiger", "lion"), colors = c("red", "green"))
```

When we display this object, we see that the names have been added automatically.

```text
> responses_student2
$numbers
[1] 1 2 3 4 5

$animals
[1] "T-rex" "tiger" "lion" 

$colors
[1] "red"   "green"
```

To highlight the flexibility and complexity of lists, note that lists can be contained within lists! We create a new list object that contains the responses for both students.

```r
responses_all_students <- list(responses_student1, responses_student2)
```

Here we did not specify labels with argument names, so when we print this object, we see the double square bracket notation return:

```text
> responses_all_students
[[1]]
[[1]]$numbers
[1]  4 20  3

[[1]]$animals
[1] "bear"    "giraffe"

[[1]]$colors
[1] "red"    "orange" "yellow" "green"  "blue"   "purple"


[[2]]
[[2]]$numbers
[1] 1 2 3 4 5

[[2]]$animals
[1] "T-rex" "tiger" "lion" 

[[2]]$colors
[1] "red"   "green"
```

![named list of lists](images/06_lists/06_R_lists-6.png)

If we had specified argument names to label this list, the resulting object would look as follows:

```text
> list(st1 = responses_student1, st2 = responses_student2)
$st1
$st1$numbers
[1]  4 20  3

$st1$animals
[1] "bear"    "giraffe"

$st1$colors
[1] "red"    "orange" "yellow" "green"  "blue"   "purple"


$st2
$st2$numbers
[1] 1 2 3 4 5

$st2$animals
[1] "T-rex" "tiger" "lion" 

$st2$colors
[1] "red"   "green"
```

### Lists and data frames

We mentioned at the start of this lesson that data frames are a special case of lists. In particular, data frames are lists where each element (column) is a simple vector of the same length. In the car information data frame subset below, each column from `mpg` to `carb` is a simple vector. They are all either numeric or integer vectors of length 6. Each element (column) in a data frame must be the same length. The car models listed on the left-hand side do not actually form a column in the data frame, but rather, they are the row names of the data frame. This ability to have row names is a special feature of data frames that lists do not have.

![mtcars data frame](images/06_lists/06_R_lists-7.png)

We can see the relationship between data frames and lists by using the coercion function `as.list`. We can see the familiar dollar sign notation indicating that the names of the list correspond to the column names of the data frame. We can also see that the simple vectors in each of these slots has length 6.

```text
> as.list(head(mtcars))
$mpg
[1] 21.0 21.0 22.8 21.4 18.7 18.1

$cyl
[1] 6 6 4 6 8 6

$disp
[1] 160 160 108 258 360 225

$hp
[1] 110 110  93 110 175 105

$drat
[1] 3.90 3.90 3.85 3.08 3.15 2.76

$wt
[1] 2.620 2.875 2.320 3.215 3.440 3.460

$qsec
[1] 16.46 17.02 18.61 19.44 17.02 20.22

$vs
[1] 0 0 1 1 0 1

$am
[1] 1 1 1 0 0 0

$gear
[1] 4 4 4 3 3 3

$carb
[1] 4 4 1 1 2 1
```

Here, when displayed as a list, each column from the data frame is now a different element of the list. This is meant to highlight the fact that data frames and lists are related. All data frames are lists. But, data have the special constraint that each element must contain the same number of items as all the other elements in the data frame and the special ability to have row names. Thus, data frames are less flexible than lists.

### Subsetting lists

It is often the case that we want to work with part of the information in an object, but not all of it. As alluded to in the previous section, we can subset lists using double square bracket or dollar sign notation. Because data frames are a special type of list, data frames can also be subset using double bracket or dollar sign notation. In addition to double bracket and dollar sign notation, we will cover single bracket notation for subsetting, and we will discuss the differences between these approaches.

#### Double square brackets

When using double square brackets, either an integer (i.e. 2) of a character string (i.e. "gear") is specified within the brackets. An integer specifies the index (also referred to as the position) within the list to extract. A character string specifies that the extraction should be done by name. The example below shows how both of these methods can be used to extract the second element of the list `l`. Note that the extracted objects are character vectors, which we can see with the `class` function. This is in contrast to the class of `l` being a list.

```text
> ## create list
> l <- list(a = 1:7, b = c("foo", "bar", "biz"))
> ## extract by index
> res1 <- l[[2]]
> ## extract by character string
> res2 <- l[["b"]]
> res1
[1] "foo" "bar" "biz"
> res2
[1] "foo" "bar" "biz"
> class(l)
[1] "list"
> class(res1)
[1] "character"
> class(res2)
[1] "character"
```

This works similarly for data frames. The example below uses the same idea for a subset of the `iris` data frame object.

```text
> iris_subset <- head(iris, 3)
> iris_subset
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
> iris_subset[[2]]
[1] 3.5 3.0 3.2
> iris_subset[["Sepal.Width"]]
[1] 3.5 3.0 3.2
```

#### Dollar signs

When using dollar sign notation for subsetting, the syntax is `object$name`, where `object` is the name of the list/data frame object, and `name` is the label for the element you want to extract. Here, in contrast to double square bracket notation, we must have names for the elements we want to extract. In the example below, we extract the element named "b" in the list object `l`, and we extract the "Sepal.Width" column in the `iris_subset` data frame.

```text
> l$b
[1] "foo" "bar" "biz"
> iris_subset$Sepal.Width
[1] 3.5 3.0 3.2
```

#### Single square brackets

When using either double square brackets or dollar signs to extract list/data frame elements, the subsetting is **simplifying** the output. That is, the original object was a list/data frame and the extracted object is simpler than a list - it is a simple vector. The opposite of a subsetting operation that **simplifies** the class of the output is a subsetting observation that **preserves** the class of the output. For lists/data frames this means that the output of the subsetting is also a list/data frame. Class preservation is achieved using single square bracket subsetting. As with double square bracket subsetting, an integer index or a character string can be specified with the brackets.

```text
> l[2]
$b
[1] "foo" "bar" "biz"

> l["b"]
$b
[1] "foo" "bar" "biz"

> class(l[2])
[1] "list"
> class(l["b"])
[1] "list"
```

Here we can tell from the printed output that the extracted output is a list because we can see the `$b` printed in the output. We can also verify this with the `class` function. In the example below, we show the same for the `iris_subset` data frame.

```text
> iris_subset[2]
  Sepal.Width
1         3.5
2         3.0
3         3.2
> iris_subset["Sepal.Width"]
  Sepal.Width
1         3.5
2         3.0
3         3.2
> class(iris_subset[2])
[1] "data.frame"
> class(iris_subset["Sepal.Width"])
[1] "data.frame"
```

Here we can tell from the printed output that the extracted output is a list because we can see that it is printed in a column. We can also verify this with the `class` function.

### Summary

Lists are a flexible way to store complex data. We have seen how to create lists using the `list` function in this lesson. As you move through the course, you will learn about ways of getting data and information into R that create list objects automatically.

Working with subsets of data will be a daily part of your work routine, so familiarity with subsetting operations will be vital. Sometimes when data is acquired, labels will be present, and sometimes it won't, so it is important to be comfortable with knowing when integer indices can be used to subset. Knowing the difference between class-simplifying and class-preserving subsetting operations is also important so that you know exactly what type of object you are working with. You will gain an appreciation for this as you move through the courses and work on projects.


### Slides and Video

![Lists](https://www.youtube.com/watch?v=fXZxlG3eEnA)


* [Slides](https://docs.google.com/presentation/d/1aJgqSCcPC_S_hEmcGy8hQGjuk6AwzT6r4ez-9IVsiXk/edit?usp=sharing)


{quiz, id: quiz_06_lists}

# Lists & Data Frames quiz

{choose-answers: 4}
?1 Which of the following statement(s) about lists and data frames is/are true?

C) Not all lists are data frames, and all data frames are lists
C) Not all lists are data frames
C) All data frames are lists
o) All lists are data frames, and all data frames are lists
o) All lists are data frames, and not all data frames are lists
o) Not all lists are data frames, and not all data frames are lists
o) Data frames are never lists, and lists are never data frames
o) Data frames are sometimes lists, but lists are never data frames

{choose-answers: 4}
? 2The following snapshot of the `iris` data frame shows the first six rows of the 5 column data frame. How can I extract the `Petal.Length` column as a simple vector (as opposed to a single column data frame)?

![iris dataframe snapshot](images/iris.png)

C) iris[["Petal.Length"]]
C) iris$Petal.Length
o) iris[[Petal.Length]]
o) iris[Petal.Length]
o) iris["Petal.Length"]
o) iris$$Petal.Length
o) iris&Petal.Length
o) iris[$Petal.Length]
o) iris[[Sepal.Length]]
o) iris[Sepal.Length]
o) iris["Sepal.Length"]
o) iris$$Sepal.Length
o) iris&Sepal.Length
o) iris[$Sepal.Length]
o) iris[["Sepal.Length"]]
o) iris$Sepal.Length

{choose-answers: 4}
?2 The following snapshot of the `iris` data frame shows the first six rows of the 5 column data frame. How can I extract the `Sepal.Length` column as a simple vector (as opposed to a single column data frame)?

![iris dataframe snapshot](images/iris.png)

C) iris[["Sepal.Length"]]
C) iris$Sepal.Length
o) iris[[Sepal.Length]]
o) iris[Sepal.Length]
o) iris["Sepal.Length"]
o) iris$$Sepal.Length
o) iris&Sepal.Length
o) iris[$Sepal.Length]
o) iris[[Petal.Length]]
o) iris[Petal.Length]
o) iris["Petal.Length"]
o) iris$$Petal.Length
o) iris&Petal.Length
o) iris[$Petal.Length]
o) iris[["Petal.Length"]]
o) iris$Petal.Length

{choose-answers: 4, points: 2}
?3 I create a list object `li` with `li <- list(a = 1:3, c("aa", "cc", "dd"))`. How can I extract the second element of the list so that the resulting object is a list?

C) li[2]
m) li[1]
o) li[[2]]
o) li[["aa"]]
o) li["aa"]
o) li["dd"]
o) li[["dd"]]
o) li[3]


{choose-answers: 4, points: 2}
?3 I create a list object `li` with `li <- list(a = 1:3, c("dd", "aa", "cc"))`. How can I extract the first element of the list so that the resulting object is a list?

C) li[1]
m) li[2]
o) li[[2]]
o) li[["aa"]]
o) li["aa"]
o) li["cc"]
o) li[["dd"]]
o) li[3]


{choose-answers: 4}
?4 Which of the following statements is TRUE?

C) The number of slots in a list is specified in the `list` function by the number of elements included and separated by commas
C) The names of each element in the list can be specified within the `list` function to the left of the equals sign.
C) The length of each element in a data frame must be the same across all elements in the data frame.
o) Within a list, the length of each list element must be consistent across the list
o) For a list, each list element must contain the same type of object as the other elements in the list
o) Lists can only contain one type of object
o) Simple vectors often contain many different types of objects in a single vector
o) Elements of a list can only be extracted using integer notation.

{/quiz}
