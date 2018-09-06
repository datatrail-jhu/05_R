# Working with Logicals

Earlier in this course, you learned that one of the basic classes of objects in R is the class of logical objects which contain TRUE and FALSE values. Logicals come up very frequently in data management and analysis because they form the basis of conditional operations (if a condition is met, perform a task) and are instrumental in data exploration, visualization, and analysis. In this lesson, we will cover the tools you will need to work with logical values in R.

As you work through this lesson, you'll be inundated with TRUE and FALSE a lot. That is because there are only two options when it comes to logicals. *However*, these are incredibly important and helpful class of objects. So, take your time to understand each example. Copying and pasting the code into your own RStudio, running it, and spending time to understand the output will really help you understand how to work with logicals!

### Logical operators

One of the most common ways to create and combine logical objects is to use **logical operators**. Broadly speaking, **operators** are symbols that indicate some action. We introduced arithmetic operators in an earlier lesson for performing routine arithmetic calculations. There was `+` for addition, `-` for subtraction, `*` for multiplication, `/` for division, and `^` for exponentiation. Logical operators in R perform actions relating to logic checking and include the following:

- `!`: the "not" operator
- `&`: the "and" operator
- `|`: the "or" operator (_Shift_ + _backslash(\)_ )
- `==`: the "equals" operator
- `!=`: the "not equal" operator
- `>`: the "greater than" operator
- `>=`: the "greater than or equal to" operator
- `<`: the "less than" operator
- `<=`: the "less than or equal to" operator
- `%in%`: the "contained in" operator

Logical operators are used with one to several R objects in order to create logical objects. These logical objects are the result of checking conditions, and they store the answers to yes/no questions that you may ask throughout your work. Let's look at several examples.

We have data on ages of some students, and we have stored this information in the `ages` object. We have information on a common age cutoff that is applied to all students for a particular activity. This is stored in the `common_cutoff` object. For another activity, we have individualized age cutoffs for each student. This is stored in the `indiv_cutoffs` object. Let's ask several yes/no questions relating to this data.

```r
ages <- c(12, 17, 16, 13, 14)
common_cutoff <- 13
indiv_cutoffs <- c(12, 12, 14, 14, 14)
```

Do the students' ages equal the cutoff? To answer this, we would use the "equals" operator `==`. (*Note*: the equals operator requires two equals signs (`==`). You'll recall that a single equals sign (`=`) is used for object assignment and is equivalent to `<-` . Whenever you want to ask if two things are equal be sure you have both equals signs in your code!) Here, each number in the `ages` object is compared to 13. Only the fourth student meets this condition.

```text
> ages==common_cutoff
[1] FALSE FALSE FALSE  TRUE FALSE
```

The output from this code prints "TRUE" for the individual (the fourth person) who meets this condition.

Do the students' ages equal the individualized cutoffs? Here, each number in the `ages` object is compared to the corresponding number in the `indiv_cutoffs` vector. Only the first and fifth students meet this condition.

```text
> ages == indiv_cutoffs
[1]  TRUE FALSE FALSE FALSE  TRUE
```

This is obvious in the output from R, where the first and the fifth values are TRUE, while the rest are FALSE.

Usually cutoffs are a bound rather than a specification of an equality, so we may instead ask if the students older than the cutoff by using the "greater than" operator `>`.

```text
> ages > common_cutoff
[1] FALSE  TRUE  TRUE FALSE  TRUE
> ages > indiv_cutoffs
[1] FALSE  TRUE  TRUE FALSE FALSE
```

Are they at least as old as the cutoff? We can answer this with the "greater than or equal to" operator `>=`.

```text
> ages >= common_cutoff
[1] FALSE  TRUE  TRUE  TRUE  TRUE
> ages >= indiv_cutoffs
[1]  TRUE  TRUE  TRUE FALSE  TRUE
```

If the cutoffs are upper bounds instead of lower bounds, we can answer similar questions as above using the "less than" `<` and "less than or equal to" `<=` operators.

```text
> ages < common_cutoff
[1]  TRUE FALSE FALSE FALSE FALSE
> ages < indiv_cutoffs
[1] FALSE FALSE FALSE  TRUE FALSE
> ages <= common_cutoff
[1]  TRUE FALSE FALSE  TRUE FALSE
> ages <= indiv_cutoffs
[1]  TRUE FALSE FALSE  TRUE  TRUE
```

So far we have treated the common cutoff and the individualized cutoffs separately, and we have thus only used one logical operator at the time. We can use several logical operators simultaneously to answer more complex yes/no questions. Are the students older than the common cutoff **and** the individualized cutoffs? We can combine the "greater than" operator with the "and" `&` operator.

```text
> ages > common_cutoff & ages > indiv_cutoffs
[1] FALSE  TRUE  TRUE FALSE FALSE
```

Are the students older than the common cutoff **or** the individualized cutoffs? We can combine the "greater than" operator with the "or" `|` operator.

```text
> ages > common_cutoff | ages > indiv_cutoffs
[1] FALSE  TRUE  TRUE FALSE  TRUE
```

Are the students older than the common cutoff but not the individualized cutoffs? We can answer this with the "not" operator or without it by reasoning through with the inequalities. In using the "not" operator, it is a good idea to wrap the condition that you are negating in parentheses to enhance clarity and avoid errors.

```text
> ages > common_cutoff & !(ages > indiv_cutoffs)
[1] FALSE FALSE FALSE FALSE  TRUE
> ages > common_cutoff & ages <= indiv_cutoffs
[1] FALSE FALSE FALSE FALSE  TRUE
```

When working with complex logical expressions, it can help to store different parts of the expression in their own objects. In reproducing the example above, we have stored the result of the logical operation dealing with the common cutoff in the `meets_common_cut` logical object. We have also stored the result of the logical operation dealing with the individual cutoffs in the `not_meets_indiv_cut` logical object. These two objects can be combined at the end in a more readable expression.

```text
> meets_common_cut <- ages > common_cutoff
> not_meets_indiv_cut <- !(ages > indiv_cutoffs)
> meets_common_cut
[1] FALSE  TRUE  TRUE FALSE  TRUE
> not_meets_indiv_cut
[1]  TRUE FALSE FALSE  TRUE  TRUE
> meets_common_cut & not_meets_indiv_cut
[1] FALSE FALSE FALSE FALSE  TRUE
```

Although these examples have all used numbers, logical operators can also be used for character and factor objects. Let's start with character objects. For comparing character objects, you will primarily use the "equals" `==` and "not equal" `!=` operators. For example, we have a character vector of colors. Are the colors "red"?

```text
> colors <- c("red", "red", "green", "orange", "blue")
> colors == "red"
[1]  TRUE  TRUE FALSE FALSE FALSE
```

Are the colors not "blue"?

```text
> colors != "blue"
[1]  TRUE  TRUE  TRUE  TRUE FALSE
```

Here it is useful to introduce the "contained in" operator `%in%`. This operator checks if the elements in the left hand object are contained in the right hand object. Are "red" and "purple" contained in this set of colors? The length of the output is the same as the length of the left hand side. We ask about two colors, "red" and "purple", and we see that "red" is contained in the `colors` object but "purple" is not.

```text
> c("red", "purple") %in% colors
[1]  TRUE FALSE
```

If we had reversed the command, we would instead be asking, "Are the colors in the `colors` object contained in the red and purple set?" Only the instances of "red" will be marked as TRUE.

```text
> colors %in% c("red", "purple")
[1]  TRUE  TRUE FALSE FALSE FALSE
```

When dealing with logical operations with factors, we can only use the "equals" `==` and "not equal" `!=` operators. Usually we will want to compare factor objects with values of their labels. Let's look at logical operations for the following factor object containing height category information.

```text
> height_factor <- factor(c(2,1,2,3,1), levels = 1:3, labels = c("short", "average", "tall"))
> height_factor
[1] average short   average tall    short  
Levels: short average tall
```

Although we create this factor object from integers, comparing it to the value 1 will not give desired results. The intention in comparing it to the integer 1 is to mark the short individuals with TRUE. We can do this by either coercing the factor object to an integer object with `as.integer` or by comparing the factor to the string label "short".

```text
> height_factor == 1
[1] FALSE FALSE FALSE FALSE FALSE
> as.integer(height_factor)
[1] 2 1 2 3 1

## coerce object to be an integer
> as.integer(height_factor) == 1
[1] FALSE  TRUE FALSE FALSE  TRUE

## compare to label directly
> height_factor == "short"
[1] FALSE  TRUE FALSE FALSE  TRUE
```

When we coerce the object to e an integer, we get the expected output. The second and final outputs are TRUE, corresponding to the values of "1" in the height_factor object. The output is the same for when the labels are directly compared. The output here returns TRUE for any places in the height_vector object where the factor label is (equal to) "short".

### Logical functions

So far we have used logical operators to ask yes/no questions on a unit-by-unit basis. That is, asking the question for each data observation. This has given us TRUE/FALSE answers for each unit. We might also want to summarize the results of these multiple responses with questions such as "Do all units meet the condition?" or "Do any (at least one) units meet the condition?"

For the first question, "Do all units meet the condition?", we can use the `all` function. The `all` function takes a logical object as input and returns TRUE if all values in the logical object are TRUE, and it returns FALSE otherwise. Are all student ages equal to the individual cutoffs? Are all ages greater than or equal to zero?

```text
> all(ages == indiv_cutoffs)
[1] FALSE
> all(ages >= 0)
[1] TRUE
```

For the second question, "Do any units meet the condition?", we can use the `any` function. The `any` function takes a logical object as input and returns TRUE if at least one of the values in the logical object is TRUE, and it returns FALSE otherwise. Are any of the student ages equal to the common cutoff? Are any ages greater than 100?

```text
> any(ages == common_cutoff)
[1] TRUE
> any(ages > 100)
[1] FALSE
```

Often we will want to combine the asking of yes/no questions with "who" and "how many" questions. Who meets the condition? How many units meet the condition? For the first question, "Who meets the condition?", we can use the `which` function. The `which` function takes a logical object as input and returns the indices of TRUE values. In this example, we see that the first and second colors are the ones that are contained within the red and purple set.

```text
> colors %in% c("red", "purple")
[1]  TRUE  TRUE FALSE FALSE FALSE
> which(colors %in% c("red", "purple"))
[1] 1 2
```

To answer, "How many units meet this condition?", we can make use of the `sum` and `mean` functions. The idea here is that logical values have a correspondence with the integer values of 0 and 1. TRUE values correspond to 1, and FALSE values correspond to 0. Thus when we create a logical object, we can use `sum` to count the number of TRUE values, and we can use `mean` to compute the fraction of TRUE values.

```text
## assign logical to ages that are greater than
## or equal to indiv_cutoffs
> meets_indiv_cut <- ages >= indiv_cutoffs
> meets_indiv_cut
[1]  TRUE  TRUE  TRUE FALSE  TRUE
## sum that object
> sum(meets_indiv_cut)
[1] 4
## get the mean of that object
> mean(meets_indiv_cut)
[1] 0.8
```

Here, the sum of the `meets_indiv_cut` is 4. When you sum a logical, R returns the number of TRUE responses. Similarly, when you take the `mean()` of an object of class logical, you get the proportion of responses that were TRUE. Here, that's 4 out of 5, or 0.8.

### Summary

This lesson walked you through how to work with operators and logical objects. This will be incredibly helpful as you start to manipulate and clean data. Having a thorough understanding of this class of objects and how to work with them will serve you well going forward.

### Slides and Video

![Working with Logicals](https://www.youtube.com/watch?v=g_PNXI-VMUc)

* [Slides](https://docs.google.com/presentation/d/1xsqzqb-2-RHDGO03aVm_Ky3y6rXlGIn4NdBviF29F3U/edit?usp=sharing)


{quiz, id: quiz_06_logicals}

# Working with Logicals quiz

For this quiz, you will be working with the `iris` data set available within R. You can look at this data frame by entering `iris` at the R prompt. This dataset has information on sepal and petal length and with for three iris species. Each row contains information on one iris flower.

?1 Are there any irises with a sepal length greater than 5.5?

A) Yes
b) No

?1 Are there any irises with a sepal length less than 4.1?

a) Yes
B) No

?1 Are there any irises with a sepal width less than 1.3?

a) Yes
B) No

?1 Are there any irises with a sepal width greater than 3.3?

A) Yes
b) No

{choose-answers: 4, points: 2}
?2 How many irises of the versicolor species have a petal width of at most 1.5?

C) 45
m) 50
o) 35
o) 86
o) 98
o) 0
o) 5
o) 150 

{choose-answers: 4, points: 2}
?2 How many irises of the setosa species have a petal width of at most 1.5?

C) 50
m) 45
o) 35
o) 86
o) 98
o) 0
o) 5
o) 150 

{choose-answers: 4, points: 2}
?3 What fraction of the irises have sepal or petal length greater than 5?

C) 78.7%
m) 15.3%
o) 12.4%
o) 28.0%
o) 40.7%
o) 12.2%
o) 92.5%
o) 88.3%
o) 18.2%

{choose-answers: 4, points: 2}
?3 What fraction of the irises have sepal or petal width greater than 2?

C) 15.3%
m) 78.7%
o) 12.4%
o) 28.0%
o) 40.7%
o) 12.2%
o) 92.5%
o) 88.3%
o) 18.2%

{choose-answers: 4, points: 3}
?4 Which of the commands below will give the same result as `(iris$Sepal.Length == 5.0) | (iris$Sepal.Length == 5.1)`? 

*Note*: The `identical()` command, which has not been discussed yet, may help you answer this question. Feel free to look at the documentation for this function by typing ?identical into the console or by Googling how to use this function if you're struggling.

C) `(iris$Sepal.Length >= 5.0) & (iris$Sepal.Length <= 5.1)`
o) `!(iris$Sepal.Length == 5.0 | iris$Sepal.Length == 5.1)`
o) `!(iris$Sepal.Length == 5.0) & !(iris$Sepal.Length == 5.1)`
o) `!(iris$Sepal.Length %in% c(5,5.1))`
o) `(iris$Sepal.Length == 5.0 | !iris$Sepal.Length == 5.1)`

{points:3}
? Within the swirl project in the [Chromebook Data Science Space on RStudio Cloud](https://rstudio.cloud/spaces/3919/join?access_code=RUUQ%2BeEgKea0oMF7EJy4UePldyBBMu7d0amv2KFC) use the `swirl()` function and navigate to the course: `CBDS Introduction to R`. Then, navigate to the lesson `L05 Working With Logicals Q01 Swirl`. Complete this swirl module. Once complete, paste the code at the end of the lesson here.

!/.*[xLkM||tFEk||URwF||INGX||ao4u||usgN||7eFS||8G27||Sw1Y||x8o6].*/i

{points:3}
? Within the same project: `CBDS Introduction to R`, navigate to the lesson `L05 Working With Logicals Q02 Swirl`. Complete this swirl module. Once complete, paste the code at the end of the lesson here.

!/.*[WRg8||TEBb||poxc||MYfT||PcH6||3C0S||JICo||GJYk||3AeE||Gk2u].*/i


{/quiz}
