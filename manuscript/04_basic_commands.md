# Basic Commands in R

Now that we've covered some essentials about R objects, we'll go over some basic commands that will be helpful in working with data.

### Functions

In working with data, we will be making substantial use of **functions**. Functions in R carry out some task. They are always a word (or set of words connected by underscores or periods followed by a set of parentheses, so the general structure of a function in R would look something like this:

```text
function(input)

function_name(input)
```

The input to a function in R is known as an **argument**. Functions require *at least one* argument, but can require multiple different arguments, depending on the function. These inputs are often objects and other variables detailing how you wish to view, summarize, or manipulate these objects. Function outputs come in a variety of formats. They can return information about the contents of an object; they can return a manipulated version of an object; and they can create entirely new objects. In this lesson, we will cover some essential functions for exploring data. This will only consist of functions that return information about the contents of an object. As you learn more about R, you will learn about functions that can manipulate objects or create entirely new objects.

To visually understand the anatomy of a **function call** (a term that describes the using of a function), let's look at the following example:

```r
mean(x, trim = 0.1)
```

We have an object `x` that presumably contains numbers, and we want to compute the mean of these numbers with the `mean` function. As stated above, all of the information inside the parentheses are function inputs (also called **arguments**), and they are separated by commas. In this command, I have supplied the object x and an additional argument `trim` that I set to be 0.1. The `trim` argument calls for a number between 0 and 0.5 and specifies the fraction of the observations in `x` to trim from the upper and lower ends of the data. Here, by including the trim argument, I am specifying that I want to take the mean of the middle 80% of the data.

### What is this object?

If someone were to write down a mystery noun for us to guess, our first question would likely be: "Is it a person, place, or thing?" When working with R objects, we will initially want similar types of information. Here we will go over some functions that can help in this regard.

As discussed briefly in the last lesson, the `class` function returns the class of an R object. This is useful for determining if an object is an atomic vector, list, or some other type of object. If it is an atomic vector, this function tells you the type.

```text
> x <- 1:10
> class(x)
[1] "integer"
> y <- c(1.1,2.2)
> class(y)
[1] "numeric"
> class(mtcars)
[1] "data.frame"
```

The `str` function stands for "structure", and it returns a description of the structure of an object. It tells you the class of an object, its size, and a preview of different components of the object. For example, when we call the `str` function on a data frame object (`mtcars`), we see that its class is `data.frame`, it has 32 rows and 11 columns, and a preview of each of the 11 columns, including the class of each column. In this example, all of the columns are numeric variables relating to features of different models of cars.

```text
> str(mtcars)
'data.frame':	32 obs. of  11 variables:
 $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
 $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
 $ disp: num  160 160 108 258 360 ...
 $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
 $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
 $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
 $ qsec: num  16.5 17 18.6 19.4 17 ...
 $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
 $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
 $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
 $ carb: num  4 4 1 1 2 1 4 2 2 4 ...
```

### How big is this object?

After we determine generally what an object is, it is useful to know how much information it contains, how big it is.

The `dim` function returns the dimensions of a rectangular object, such as a matrix or a data frame. The output is an integer vector with two components: first is the number of rows (which can also be obtained with `nrow()`), and second is the number of columns (which can also be obtained with `ncol()`). We saw previously that the `str` function provides the same information and more, so why would we use these functions instead? The `str` function provides this information by printing it to the screen for us to visually see, but it does not extract this information directly. If we need to use the dimensions later in the analysis as a variable, these functions provide a direct way to store this information.

```text
> dim(mtcars)
[1] 32 11
> nrow(mtcars)
[1] 32
> ncol(mtcars)
[1] 11
```

The `length` function returns the number of items in a vector object. We talked about this briefly last lesson that the number of things in your object is referred to as its length. Here, we can quickly calculate the length of an object by calling the `length` function.

```text
> x <- c(1, 10, 3)
> length(x)
[1] 3
```

### Are there named features of this object?

Another way to explore an object in R is to see what components it has. In R, these components are designated with names.

The `names` function can be used to get and set the names of an R object, most often an atomic vector or a list. For example, we can create an R object called `prize_money` that contains the prize money for first, second, and third places:

```r
prize_money <- c(1000, 500, 250)
```

If we want to label this vector with the prizes, we can use `names` combined with the assignment operator `<-` and a character vector of labels:

```r
names(prize_money) <- c("first", "second", "third")
```

Later in our work, if we want to remind ourselves of the labels, we can use the `names` function by itself, which will print the names for the object.

```text
> names(prize_money)
[1] "first"  "second" "third"
```

Note that in many situations, it will be better practice to encapsulate the above information in a two-column data frame instead of a named vector as below.

```r
prize_info <- data.frame(
    money = c(1000,500,250),
    place = c("first", "second", "third")
)
```

This is more convenient for further work if you have other objects that have information on first, second, or third placing, but not prize money information. You'll learn more about these concepts when you learn about "tidy data" in a later course.

The `colnames()` and `rownames()` functions act analogously to the `names` function but are used for the column labels and row labels of a matrix or data frame. The numbers in square brackets at the beginning of the lines of printed output indicate the index of the first observation on the line. So for the row names, we can see that "Duster 360" is the seventh element.

```text
> colnames(mtcars)
 [1] "mpg"  "cyl"  "disp" "hp"   "drat" "wt"   "qsec" "vs"   "am"   "gear"
[11] "carb"
> rownames(mtcars)
 [1] "Mazda RX4"           "Mazda RX4 Wag"       "Datsun 710"         
 [4] "Hornet 4 Drive"      "Hornet Sportabout"   "Valiant"            
 [7] "Duster 360"          "Merc 240D"           "Merc 230"           
[10] "Merc 280"            "Merc 280C"           "Merc 450SE"         
[13] "Merc 450SL"          "Merc 450SLC"         "Cadillac Fleetwood" 
[16] "Lincoln Continental" "Chrysler Imperial"   "Fiat 128"           
[19] "Honda Civic"         "Toyota Corolla"      "Toyota Corona"      
[22] "Dodge Challenger"    "AMC Javelin"         "Camaro Z28"         
[25] "Pontiac Firebird"    "Fiat X1-9"           "Porsche 914-2"      
[28] "Lotus Europa"        "Ford Pantera L"      "Ferrari Dino"       
[31] "Maserati Bora"       "Volvo 142E"
```

{format: png}
![`colnames()` and `rownames()` functions](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g3778484ff5_0_78)

### What does this object look like?

Sometimes we may just want to see the information contained in an object. Here we will discuss functions that allow you to see parts of objects.

The `print` function displays the entire contents of an object.

```r
print(mtcars)
```

Recall that in R, the **Console** is where commands can be typed and entered for R to run. When R is ready to accept a command a greater than sign will be displayed. An alternative to calling the `print` function is to simply type the name of the object in the Console and press enter. In general printing an entire object is not advisable just in case the object is quite large. In this case your screen would overflow with text!

```r
mtcars
```

{format: png}
![printing objects' contents to the screen](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g3778484ff5_0_93)

Safer alternatives to printing are the `head` and `tail` functions. The `head` function displays the beginning of an object. By default, it shows the first 6 items. If the object is a vector, `head` shows the first 6 entries. If the object is a rectangle, such as a matrix or a data frame, `head` shows the first 6 rows. The `tail` function is analogous to `head` but for the end of the object.

```text
> head(mtcars)
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1

> tail(mtcars)
                mpg cyl  disp  hp drat    wt qsec vs am gear carb
Porsche 914-2  26.0   4 120.3  91 4.43 2.140 16.7  0  1    5    2
Lotus Europa   30.4   4  95.1 113 3.77 1.513 16.9  1  1    5    2
Ford Pantera L 15.8   8 351.0 264 4.22 3.170 14.5  0  1    5    4
Ferrari Dino   19.7   6 145.0 175 3.62 2.770 15.5  0  1    5    6
Maserati Bora  15.0   8 301.0 335 3.54 3.570 14.6  0  1    5    8
Volvo 142E     21.4   4 121.0 109 4.11 2.780 18.6  1  1    4    2
```

{format: png}
![head() and tail() can be used to see a portion of the data](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g3778484ff5_0_98)


The `summary` function computes summary statistics for numeric data and performs tabulations for categorical data, which are called **factors** in R.

```text
> summary(iris)
  Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
       Species  
 setosa    :50  
 versicolor:50  
 virginica :50  
```

{format: png}
![The summary() function summarizes data](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g3778484ff5_0_103)


The `unique` function shows only the unique elements of an object. For vectors, this returns the set of unique elements. For rectangles such as matrices and data frames, this returns the unique rows. This function is useful if we want to check the coding of our data. If we have sex information, then we expect the result of unique to be two elements. If not, there is likely some data cleaning that must be done. The `unique` function is also useful for simply exploring the values that a variable can take. In the example below, we can see that in the `mtcars` data frame, there are only cars with 6, 4, and 8 cylinders. Note that to extract the column corresponding to cylinders, we used a dollar sign followed by the column name: `$cyl`. This is an example of subsetting that you will learn in later lessons.

```text
> unique(mtcars$cyl)
[1] 6 4 8
> dat <- data.frame(a = c(1,1), b = c(2,2))
> dat
  a b
1 1 2
2 1 2
> unique(dat)
  a b
1 1 2
```

{format: png}
![The unique() shows unique elements of an object](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g3778484ff5_0_108)


### Errors, Warnings, and Messages

In R, there are three types information that R may return to you to your screen to provide you with additional information. These come in the form of **errors, warnings, and messages**. While they will often *look* similar to one another, it's important to understand the difference between them.

The most serious of these messages is an error message. **Errors** indicate that the code you tried to run **did not run successfully**. If you receive an error message, you should carefully look back at your code to see what went wrong. Error messages cannot be ignored as they indicate that there was no way for the code to run. Something has to be fixed before moving forward. For example, the code here produces an error, since `mtca` is *not* a data frame or object in R.

```r
unique(mtca$cyl)
```

{format: png}
![errors](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g451659353d_0_0)


**Warnings** are generally less serious than error messages. They are generated when the **code executes** (meaning, it runs without producing an error and stopping), **but produces something unexpected**. Warning messages should always be read, and then you, the person writing the code, has the option to decide whether or not the code that has generated the warning needs to be re-written. For example, the log function is only defined for numbers greater than zero. If, in R, you try to take the log of a negative number, you get an output (`NaN`):

```r
log(-1)
```

This output means the code executed (there was no error), but you also get a warning letting you know that NaNs were produced. If you meant to take the log of a negative number, you would leave the code as is. However, if you did not intend to do this, the warning message helps clue you into the fact that you may want to revisit your code.

{format: png}
![warnings](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g451659353d_0_22)


Last but not least, **messages**, in general, are simply there to **provide you with more information**. They do not indicate that you have done anything wrong. For example, if you were to run a function that creates a directory if it does not yet exist, the function may provide you a message informing you whenever a new directory has been created. This message would just be there to provide you with more information. No further action is generally necessary when a message is provided.

{format: png}
![messages](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/export/png?id=1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM&pageid=g451659353d_0_29)

Note that all three are in the same font and same color, so they'll look similar in your RStudio Cloud console. Over time, you'll get more comfortable dealing with and understanding the difference between the three. For now, be sure that to remember if you get an error, your code did not execute successfully. Go back and find what caused the error.

### Summary

In this lesson, you have been introduced to a number of commonly-used commands (functions) that are available to you in R. These will help you to determine the class of objects (`class()`), figure out how big an object is (`length()`, `dim()`, `nrow()`, `ncol()`), get an idea of what the object looks like (`str()`, `head()`, `tail()`), and summarize the data contained in the object (`summary()`, `unique()`), among many others. Understanding the functions discussed in this lesson and becoming very comfortable with what each of these does is incredibly important for moving forward and programming in R. Finally, we discussed errors, warnings, and messages in R. This is the foundation of what we'll use throughout the rest of the course, so spend some time here and ensure that you understand what the code does in each example before moving on!

### Slides and Video

![Basic commands in R](https://youtu.be/OfsyXMY2sAw)

* [Slides](https://docs.google.com/presentation/d/1ew_I5lM283x6Xxlywznp-02tvCKcwxcvNMJeFM4gXUM/edit?usp=sharing)


{quiz, id: quiz_04_basic_commands}

# Basic Commands in R quiz

{choose-answers: 4, points: 2}
?1 Within R, you have access to an object called `airquality` that contains data on New York air quality. You can work with it in the same way that we have worked with the `mtcars` and `iris` objects in this lesson. What is the value in the "Ozone" column in the third to last row?

C) 14
m) 14.3
o) 12
o) 18
o) 20
o) NA
o) 16
o) 10

{choose-answers: 4, points: 2}
?1 Within R, you have access to an object called `airquality` that contains data on New York air quality. You can work with it in the same way that we have worked with the `mtcars` and `iris` objects in this lesson. What is the value in the "Wind" column in the third to last row?

C) 14.3
m) 14
o) 12
o) 18
o) 20
o) NA
o) 16
o) 10


{choose-answers: 4, points: 2}
?2 How many rows and columns are in `airquality`?

C) 153 rows, 6 columns
m) 153 columns, 6 rows
o) 154 rows, 7 columns
o) 153 rows, 7 columns
o) 154 rows, 6 columns
o) 1 row, 153 columns
o) 1 column, 153 rows

{choose-answers: 4, points: 2}
?2 What are the dimensions of the `airquality` dataframe?

C) 153 rows, 6 columns
m) 153 columns, 6 rows
o) 154 rows, 7 columns
o) 153 rows, 7 columns
o) 154 rows, 6 columns
o) 1 row, 153 columns
o) 1 column, 153 rows
 
{choose-answers: 4, points: 2}
?3 How many months of the year are represented in this `airquality` dataset?

C) 5
m) 31
o) 7
o) 3
o) 9
o) 12
o) 0
o) 2
o) 4
o) 5

{choose-answers: 4, points: 2}
?3 How many different days are represented in this `airquality` dataset?

C) 31
m) 7
m) 5
o) 2
o) 9
o) 12
o) 0
o) 2
o) 4

{choose-answers: 4, points: 2}
?4 What is the median temperature (Temp column) in this `airquality` dataset?

C) 79
m) 9.7
o) 56
o) 72
o) 85
o) 97
o) 77
o) 5.6
o) 10
o) 15

{choose-answers: 4, points: 2}
?4 What is the median mph of Wind (Wind column) in this `airquality` dataset?

C) 9.7
m) 79
o) 56
o) 72
o) 85
o) 97
o) 77
o) 5.6
o) 10?
o) 15

{points:3}
?5 Within the swirl project in the [Cloud-based Data Science Space on RStudio Cloud](https://rstudio.cloud/spaces/20345/join?access_code=n4b8J1s0XmWctSy83%2BEXbGAwj7rKcuFMI7WJEJFD) use the `swirl()` function and navigate to the course: `CBDS Introduction to R`. Then, navigate to the lesson `L04 Basic Commands Q01 Swirl`. Complete this swirl module. Once complete, paste the code provided at the end of the swirl module here.

! /.+(vDw3|1PL2|AsAn|5hmz|vSfW|HlrI|BfuF|z3AD|J6lF|XvlN).+/i

{points:3}
?6 Within the same project: `CBDS Introduction to R`, navigate to the lesson `L04 Basic Commands Q02 Swirl`. Complete this swirl module. Once complete, paste the code provided at the end of the swirl module here.

! /.+(RPJS|MURb|GTxZ|j9H6|Zv3E|3rbq|UuDU|5Lxd|rJZh|Txkt).+/i

{points:3}
?7 Within the same project: `CBDS Introduction to R`, navigate to the lesson `L04 Basic Commands Q03 Swirl`. Complete this swirl module. Once complete, paste the code provided at the end of the swirl module here.

! /.+(miVw|9Dmv|n3dE|eSO7|WUDZ|LpE6|VObz|uuV6|jMcj|RGIU).+/i

{points:3}
?8 Within the same project: `CBDS Introduction to R`, navigate to the lesson `L04 Basic Commands Q04 Swirl`. Complete this swirl module. Once complete, paste the code provided at the end of the swirl module here.

! /.+(jN5M|RHCY|0rQl|DR0K|0abr|509O|KzAH|nWBh|IEm0|khcd).+/i


{/quiz}

