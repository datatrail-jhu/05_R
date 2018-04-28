# Objects in R

Now that we've gone over what exactly R is and outlined the package functionality that makes it useful for working with data, we are going to cover information needed to actually start working in R. To work with data in R, you'll need an understanding of objects.

### What is an object?

Simply put, an object in R is something that contains information. In R there are a number of basic classes of objects. Five classes that you'll be working with commonly are

- character
- integer
- numeric (real numbers)
- logical (TRUE/FALSE)
- factor (categorical information)

These classes are the building blocks for creating all sorts of objects in R. The simplest type of object in R is called a vector, which is an object that can contain multiple items. Generally, vectors can only contain objects of the same class, but a certain type of vector, called a list, can contain objects of different classes. You will learn about lists in a later lesson. We'll begin this lesson by looking at how to create objects in each of these five basic classes in R.

### Storing objects

In R, as with all programming languages, it is important to be able to store objects that we create so that we can use them in later code. The process of storing an object is called **assignment**, and it entails giving an object a name. For example, the following code creates an object called `min_age` and stores inside it the value 21.

```r
min_age <- 21
```

The `<-` operator is called the assignment operator. The `=` operator can also be used for assignment:

```r
min_age = 21
```

Having this minimum age variable stored in an object can be useful later if we have data where we only want to keep individuals who exceed this minimum age.

### Character

Character objects in R can be created by surrounding a string in either double quotes or single quotes as in the following two examples.

"This is a character object."

'This is also a character object.'

The example below shows how to store the above sentence character object in an object named `my_char`. `my_char` is a character vector of length 1.

my_char <- "This is a character object."

We can create a character vector named `my_char_vec` with multiple character objects using the concatenate function, c:

my_char_vec <- c("char object 1", "char object 2")

We'll discuss functions more in later lessons.

### Integer

Integer objects in R can be created by specifying an integer number followed by the letter "L". The following creates an integer object called `num` and stores the value 1.

```r
num <- 1L
```

Without the letter "L", the number will be recognized as a more general, numeric object. We can create an integer vector with multiple items using the `c` function, the concatenation function. The following creates an integer vector of length 3 with the numbers 1, 10, and 3.

```r
num_vec <- c(1L, 10L, 3L)
```

We can also create an integer vector with the colon operator. The following command creates an integer vector with the numbers 2, 3, 4, and 5.

```r
num_vec2 <- 2:5
```

### Numeric

Numeric objects in R represent real numbers and are created by simply entering a number.

```r
num1 <- 1
num2 <- 1.2
```

We can create a numeric vector with multiple items using the c function.

```r
num_vec <- c(1.2, 9.8)
```

### Logical

Logical objects in R represent true or false conditions and can be created by typing "TRUE" or "FALSE".

```r
check_condition <- TRUE
check_condition <- FALSE
```

We can create a logical vector with multiple items using the c function.

```r
check_condition <- c(TRUE, TRUE, FALSE)
```

### Factor

Factor objects contain information for categorical variables (e.g. color, shape). They have similarities to character objects and integer objects.

The following `colors` object is a character vector containing five pieces of color information. There are only two unique colors present: red and blue. These unique colors are called the **levels** of a factor.

```r
colors <- c("red", "red", "blue", "red", "blue")
```

To create a factor object out of this character vector we can use the `factor` function or the `as.factor` function. Let's try both and look at the objects created.

```text
> colors_factor1 <- factor(colors, levels = c("red", "blue"))
> colors_factor1
[1] red  red  blue red  blue
Levels: red blue
> colors_factor2 <- as.factor(colors)
> colors_factor2
[1] red  red  blue red  blue
Levels: blue red
```

When we used the `factor` function we also specified the levels to be red and blue. The order of the levels we specified is important: first red, then blue. We can see that when we print this object the levels are listed in the order we specified. A quick way to create a factor object is with the coercion function `as.factor`. When we print this object, the levels are opposite to what we specified when we used the `factor` function because by default, the levels are specified in alphabetical order. Here the first level is blue and the second is red. The ordering of levels will be important in future courses when we cover data tidying, plotting, and statistical modeling.

One last topic to cover with factors is labeling. We can control the displayed labels of a factor with another option with the `factor` function. This need often arises if we want to create a factor object from an integer object or from a character object with labels that we don't like. In the example below, we see that we originally had ozone information encoded with integers. When we use the `factor` function to make a corresponding factor object, we specify both the unique levels present in the integer object and the desired labels with a character vector. The order of the specified levels shold correspond to the order of the specified labels. The two examples, `ozone_factor` and `ozone_factor2`, create the same labeling of the original integer vector, but the order of the levels is different between the two approaches. In the first approach, the first level is low, the second is medium, and the third is high, which is the most natural ordering. In the second approach, the first level is medium, the second is low, and the third is high.

```
> ozone_levels <- c(1,2,1,3,1,1)
> ozone_factor <- factor(ozone_levels, levels = 1:3, labels = c("low", "medium", "high"))
> ozone_factor
[1] low    medium low    high   low    low   
Levels: low medium high
> ozone_factor2 <- factor(ozone_levels, levels = c(2,1,3), labels = c("medium", "low", "high"))
> ozone_factor2
[1] low    medium low    high   low    low   
Levels: medium low high
```


### Data frames

Now that we've covered common basic data classes, we will now discuss data frames. Data frames are a more complex data type than the simple vectors than we've seen so far. Data frames organize data into a rectangular format where each column corresponds to a single variable and each row corresponds to an observation. So a row of a data frame contains an observation's values for all variables. An example of a data frame is shown below:

model              mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1

We see along the columns different variables related to car properties, and each row gives information on those properties for a particular car model. Every column in a data frame is a simple vector of values all from the same class.

You will learn more about working with data frames in the next lesson and in later courses.

### Slides and Video

* [Slides](https://docs.google.com/presentation/d/1-1oGr9-phf3fKcezvl_y573tJ_Zvc09u1bhNAnH1CO8/edit?usp=sharing)


{quiz, id: quiz_02_objects}

# R Objects quiz

? Suppose I enter the following code in R: `x <- 2`. What is the class of the `x` object?

a) character
b) integer
C) numeric
d) logical

? What command can be used to create a logical object `y` containing two `TRUE` values?

A) `y = c(TRUE, TRUE)`
b) `y = c("TRUE", "TRUE")`
c) `y = c(1, 1)`
D) `y <- c(TRUE, TRUE)`

? In the following data frame, what atomic class could be represented by the Species column?

 Sepal.Length Sepal.Width Petal.Length Petal.Width Species
          5.1         3.5          1.4         0.2  setosa
          4.9         3.0          1.4         0.2  setosa
          4.7         3.2          1.3         0.2  setosa
          4.6         3.1          1.5         0.2  setosa
          5.0         3.6          1.4         0.2  setosa
          5.4         3.9          1.7         0.4  setosa

A) character
b) integer
c) numeric
d) logical
E) factor

? What will be the ordering of the levels when the following character object is made into a factor object with `as.factor`?

`char_vec <- c("medium", "medium", "high", "low", "low")`

a) low, medium, high
b) low, high, medium
c) medium, low, high
d) medium, high, low
E) high, low, medium
f) high, medium, low

{/quiz}
