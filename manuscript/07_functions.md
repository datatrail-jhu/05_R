# Writing Functions in R

Up to this point, you've come across a number of functions. `length()` will tell you the length of an object. `names()` will allow you assign names to your object. And, `nrow()` will tell you the number of rows in your data frame. These are all functions within R. Very generally, all of these functions take some input (often, an object in R), do something using that input when the function runs, and then provide the user (you!) some output. 

In addition to built-in functions, R allows for users to write code and develop additional functions that will work in addition to these included functions. We talked about these types of functions when we talked about packages in an earlier lesson. In these cases, developers wrote code to accomplish a task that was not included the base functions that come with R.

While R packages are a great way to add functionality to your work in R, functions can be written outside of packages. You can write your own functions at any point in time in R. When you write code to carry out a function, you generate a **User-Defined Function** (UDF). UDFs are functions beyond the set of functions that come built-in to R, and are written by users. 

UDFs are incredibly helpful as you code. While they may seem intimidating now, take your time working through this lesson. It's worth the time investment now to really understand how to write a function

### When to write a function

Writing functions can be a daunting task as you learn to code. As you get more comfortable coding, you'll naturally get more comfortable writing functions. However, you will always learn better and more efficient ways to write functions. This means that the learning never stops, which can be a lot of fun! But, if this is a difficult lesson, you're not alone. Functions take a while to get the hang of but are incredibly helpful once you do!

That said, when you're new to coding, it often *seems* easier to avoid writing functions and just copy and paste code over and over again each time you have to carry out the task that that chunk of code carries out. However, a really important rule of thumb is that you should **write a function whenever you've copy and pasted code more than once**. So, if you've written a chunk of code and then used it in at least two more places, write a function. It will save you time in the long run!

### How will writing functions help me? 

Writing functions for tasks that you carry out multiple times is helpful because:

1. **It makes your code more readable.** - By having a single function such as, for example, `summarize_samples( samples )`, instead of requiring some twenty lines of code to summarize your samples in the middle of your script file, readers (and you later on when you come back to this code!) will quickly and easily be able to determine what that part of your code accomplishes by that single function call.
2. **You only have to update code in one place.** - After writing a function, to update this code in the future (and trust me, you always end up editing code), you only have to update the function code once. Alternatively, if you had copy and pasted this code all over your script files, you'd have to find each instance, and edit the code in each individual case. From personal experience, save yourself the hassle, and write a function!
3. **You'll avoid accidental errors.** Inevitably, as you copy and paste you'll decide you want to change an object name here or there. However, if you do this in one place, but forget to do this in another place where you've copy and pasted the code, you'll run into errors. By writing functions, this issue is avoided!

### How to write a function

There are three main components to a function. Each function has a:
1. name
2. argument(s)
3. body

We'll break down each of these three parts in this section, but know that generally every function in R will use this format:

```text
name <- function(arguments){
	body
}
```

You will assign a name to each function you write. This will go to the left of the assignment operator: `<-`. Note that to create a function you will then call the built-in R function `function` (what a perfect function name!). The arguments of the function you're writing will go inside the parentheses after you call `function`. This will be followed by curly braces. All the code you want your function to execute will go within these curly braces. Now that you have an idea of what the basic components of a function in R are, we'll discuss each in greater detail.

#### Naming your function

Naming your function may seem trivial but is an important step in writing a function. To be clear, R doesn't *really* care what you name your function. You could name your function "asdfklj," and as long as the code in the body of the function is correct, R will know what to do and run your function correctly. So, if R doesn't care about the name, why should you? Well, honestly, you aren't naming your function well for R, you're naming it well for humans (including your future self!). 

Good function names in R explain what the function does **clearly and succinctly**. Thus, you'll want to choose function names that are the shortest possible names but still clearly describe what the function does. Additionally, function names are *generally* verbs, or action words. This is because functions are usually *doing something*, so it makes sense to have the function name reflect that. Above I mentioned you may often want to summarize some details about the samples in your dataset. Thus, you would likely want to write a function called `summarize_samples`. This is a reasonable function name. It clearly describes *what the function does*. It may be a *tad* long, but it's better than the alternatives. `ss` is way too short for a function name, and `summarize` doesn't do the trick here because it's not specific enough. So, `summarize_samples` is a reasonably good function name.

You may have noticed that the two words summarize and samples is joined by an underscore. Function names, like objects in R, cannot contain spaces. So, I could have chosen `summarizesamples`, but that's hard to read quickly. Or, I could have chosen `SummarizeSamples`, but that's harder to type, having to capitalize two letters. Thus, it's generally best to use what is known as **snake case** for functions. Snake case means that all words include only lowercase letters and that separate words are connected by an underscore (_). No spaces are allowed in snake case.

Lastly, you'll want to choose a name that is not already a function that exists in R. For instance, you would want to avoid naming a function `mean`, as a function name since it's already used by R.

To recap, the best function names are:
* short
* clear
* descriptive
* verbs (action words)
* "snake case" 
* not already R functions

#### Function arguments

Now that we've discussed how to name the functions you write, we have to discuss the **arguments**, or **inputs** to your functions. Arguments go within the parentheses after `function`. A function can have multiple arguments, but every function must have **at least one argument**. Arguments tell the function on what input values the function should act. 

For example, let's return now to a function you're already familiar with: the `length` function. This function tells you the length of an object. Thus, the argument to this function is the object for which you want to get the length.

Take the following code into consideration:

```r
x <- c(1, 3, 7, 19)
length(x)
```
The object `x` contains four numbers. When you want to run the `length` function, you have to tell R what you want the length of. Thus, the argument required is the object, which in this case is the object `x`. 

For functions you write, you will have to tell the function what the inputs are for the function by defining at least one argument within the parentheses after you call `function`. We'll work through an example of this later in the lesson, but for now it's important to note that unlike functions (which are verbs), arguments tend to be nouns. Generally, arguments describe on what object the function (verb) should be carried out. Nouns are good words to accomplish this. 

#### Body of your function

Finally, the code you want to run using the input you've defined as an argument is included in the body of the function. While the name of the function was for the humans using the function or reading your code, this section is primarily for the computer. This section will only run properly if the R code is correctly written.

### Commenting your function

So, it was just mentioned that the body of your function is for the computer. While that's true (the computer will know what to do if your R code is correct!), to make your function *even better* the code within your function should include comments that make sense to humans.

By including lines in your code that start with a pound sign (#) and are followed by human-readable text, you make your function easily understandable to anyone trying to figure out what your code does. See examples of this as we work through an example function below.

Additionally, for long functions with a lot of steps, it's helpful to break up the sections of your code with dashes (`-`) that visually separate the sections for others when reading the function. For example, below, <YOUR CODE HERE> represents lines of code that carry out the task explained in the comment above. The comment lines (#) with dashes (-) help visually separate out the sections for anyone looking at this code. Note, the computer will skip over any line of code that starts with a pound sign (#), so these comments are *only helpful to humans*. *But* they are incredibly helpful to humans. **Always take the time to comment your code**, especially in functions.

```text
# Read in sample --------------------------------------------------------

<YOUR CODE HERE>

# Calculate sample information --------------------------------------

<YOUR CODE HERE>

# Generate summary table --------------------------------------------

<YOUR CODE HERE>
```

### Function Output

In R, the default for any function is to **return the last statement evaluated**. If the last bit of code computes a value, the function will return the last value that was computed.  So, if you write code and the last value calculated in the body of your function is what you want, then you're all set.

If, however, you want the function to return *something else* as its output (such as an object you created earlier in the function or multiple values as the functions' output), you'll need to specify that using the `return` function. The argument of the return function is the object you want the function to return. So generally, you would include something like the following at the end of the body of your function (still within the curly braces):

```
return(object_you_want_to_return)
```

### An example function: Converting from Celsius to Fahrenheit

Now that we've covered the basics components to writing a function in R, we can walk through this using an example function.

Specifically, imagine you need to convert Celsius degree to Fahrenheit. You want to know what 0, 20, and 100 degrees Celsius are in Fahrenheit. We can write a function to accomplish this!

If you were to Google how to convert Celsius to Fahrenheit, you'd find that the conversion formula is: T(F) =  (9/5) * T(C)  + 32. So to calculate what 0, 20, and 100 degree Celsius are you can do the calculation above for each temperature by hand. You could take zero degrees celsius, multiply it by (9/5) and then add 32 to it. Then, you could repeat this for 20 C and then again for 100 C. The more temperatures you need to convert, the longer this will take you. But, as you're repeating a task (a calculation) multiple times and just changing the input for each calculation, it is the perfect time to write a function. Instead of doing something over and over by hand (or by copy and pasting code), you can just write a function in R to do the work for you!

Take for example this function:

```r
celsius_to_fahrenheit <- function(C){
	C * (9/5) + 32
}
```

To recap:
* `celsius_to_fahrenheit` is the name of the function. 
* `C` is the argument (or input) 
* `C * (9/5) + 32` is the body, and tells R what to do to the input

Specifically, this code says, take whatever input C is, multiply it by (9/5) and then add 32 to that number. This is exactly what we want to do to convert from Celsius to Fahrenheit! So, just copy and paste this code into R, and then try running the following code!

#### Running a Function

To run a function, you take the function name (here, our function name is `celsius_to_fahrenheit` and then put the values for the input arguments within the parentheses. Here, our input is a temperature in degrees Celsius, and specifically, we'll use 70 degrees Celsius as our input for this example.

```r
> celsius_to_fahrenheit(70)
[1] 158
```

Here, the output lets us know that 70 degrees Celsius (our input argument) is 158 degrees Fahrenheit (the output from running the function). 

Additionally, this example demonstrates that sometimes a function can carry out a necessary and important task with only a single line of code.  But, what about our initial question? What about calculating what 0, 20, and 100 degree Celsius is in Fahrenheit? 

```r
> celsius_to_fahrenheit(c(0, 20, 100))
[1]  32  68 212
```
By including these three values into our functions arguments, we quickly and easily calculate the three temperatures values in Fahrenheit! And, we didn't have to do each by hand!

While the goal of this function is pretty straightforward and only accomplishes one task, functions can and do get a lot more complicated and include a lot more code. However, even when this is the case, the overall structure of the function in R will not change. The function will still have a name, at least one argument, and code in the body of the function. Let's take a look at how functions can get a little more complicated.

#### Customizing the function's output: `return()`

Now that we know what the basic structure of the function is, let's make it a little bit fancier. We mentioned it briefly above, but the `return` function can help customize what your function returns. In the example above, we took advantage of the fact that R will automatically return the last statement evaluated (which in this case is the last value calculated).  For instance, when the function is called, we like it to return a sentence that is more clear.

```r
celsius_to_fahrenheit <- function(C){
F <- C * (9/5) + 32
return(paste("The entered Celsius temperature is", F, "degrees Fahrenheit."))
}
```

Here, the first line of code takes the input argument, the degrees celsius (`C`) and converts it to degrees Fahrenheit, as the function did above. However, this time, that line of code is assigned to an object `F`. The additional line of code uses the `return` function to explicitly state what the function should return. Here,  the function `paste` is used within return to combine the text "The entered Celsius temperature is" with the value of variable `F` followed by "degrees Fahrenheit", where each is separated by a comma.  

Note that the text we want `paste` to display is in quotes while the object `F` is *not* in quotes. This is how R knows that the text is supposed to be displayed as text while F is supposed to be the value of that object.
 
Now if we were to call this updated function, the output would provide a sentence that makes explicitly clear what the output of the function means:
 
```r
> celsius_to_fahrenheit(70)
[1] "The entered Celsius temperature is 158 degrees Fahrenheit."
```

Just as we wanted, we have a clear sentence output with the conversion of 70 C  to 158 F!

#### Required arguments

Earlier we stated that functions require at least one argument. That wasn't *quite* true. You *can* write a function that does not have an argument explicitly stated, but that instead requires input from the user. While we'll include an example here, we won't go into explicit detail as these types of functions are not frequently used in R code. For instance, we can write a function that can only be called by `celsius_to_fahrenheit()` and no input is passed in the function. When this function is run, a prompt appears asking the user to enter a value.

```r
celsius_to_fahrenheit <- function(){
  C <- readline(prompt="Enter a value in Celsius: ")
  F <- as.integer(C) * (9/5) + 32
  return(paste("The entered Celsius temperature is", F, "degrees Fahrenheit."))
}
```
When this is run, the output would look as follows:

```r
> celsius_to_fahrenheit()
Enter a value in Celsius: 70
[1] "The entered Celsius temperature is 158 degrees Fahrenheit."
```

#### Functions with multiple arguments

Functions can be a lot more advanced. For example, while we stated earlier that functions can have multiple inputs, we haven't exactly shown what that would look like. So, going back to our Celsius/Fahrenheit example, let's write a function that takes a temperature and can convert it both from Celsius to Fahrenheit (as it did above) *and* can go the other direction, taking a temperature from Fahrenheit to Celsius. To use this function, you'll not only have to provide the temperature you want to convert as an argument (as above), but you'll have to tell the function whether or not that temperature you're inputting is in Fahrenheit or Celsius. Specifically, is if the user passes the values of 10 and C (for Celsius) to the function, it will convert it to Fahrenheit and return the value and if the user passes the values of 10 and F (for Fahrenheit), it will convert it to Celsius and return the value.

```r
convert_temp <- function(temp, unit){
if (unit=="C"){
    D <- temp * (9/5) + 32
} else if (unit=="F") {
    D <- (temp - 32) * (5/9)
} else {
    D <- message("Please enter a correct unit -- either F or C")
}
return(D)
}
```

Ok, admittedly, this function has a lot going on! No need to worry we'll break it down now.

Let's first identify the three parts of the function that we know will always be there for every function.

* name: `convert_temp`
* argument(s) `temp` *and* `unit`
* body: all that code in there!

This function is similar to the previous function, but has a few extra bells and whistles. 

First, instead of having the argument `C`, for a temperature in degrees Celsius, we've now changed that argument to `temp`, as the input temperature can be in either degrees Celsius *or* degrees Fahrenheit. There's also that additional argument `unit`, which, as discussed above, will specify what temperature our `temp` input is.

Additionally, the function now has a conditional statement based on the argument `unit`. What those `if`s and `else if` statements say is *if* the argument `unit` is "C" (meaning the temperature is in Celsius"), then convert the value to Fahrenheit. *But*, if the argument `unit` is "F" (stating the input temp is in Fahrenheit), well, in that case convert the value to Celsius. Finally, if the argument unit is neither "F" nor "C" tell the user that they haven't entered that unit correctly by displaying the message "Please enter a correct unit -- either F or C".

When we run this new function `convert_temp`, the output looks as follows! Feel free to copy that function above and then test it out yourself! Go ahead and convert a few temperatures!

```r
> convert_temp(70, "C")
[1] 158
> convert_temp(158, "F")
[1] 70
> convert_temp(158, "degrees")
Please enter a correct unit -- either F or C
NULL
```
### Functions with default arguments 

So far, we have required the user to state what each argument is every time they run one of the functions. However, arguments can have default values. This is helpful when most of the time an argument will take one value (the default) but you want to make the other input value available. 

For example, the author of this lesson *happens* to live in the US, where we mostly think in degrees Fahrenheit. But, working with someone from pretty much *anywhere else in the world* requires understanding temperatures in degrees Celsius. Thus, if I were writing this function for myself or co-workers in the states who like to cook, I would likely set the default in the function to Celsius, as we're much more likely to be looking at a temperature on a recipe that's in Celsius but that we need in Fahrenheit to set our ovens to the correct temperature.

To accomplish this, when you write the function, you can assign a default value to the argument `unit` for instance `unit = "C"`. This means that if the user does not have to explicitly state what the value of the argument `unit` is. Instead, the function will assume will be that its value is `"C"`, unless the user states otherwise. This is how we modify the function:

```r
convert_temp <- function(temp, unit = "C"){
if (unit=="C"){
    D <- temp * (9/5) + 32
} else if (unit=="F") {
    D <- (temp - 32) * (5/9)
} else {
    D <- message("Please enter a correct unit -- either F or C")
}
return(D)
}
```

Now, if we run that function without the specified unit, the function assumes the input is in degrees Celsius. Note, if you specify `unit="C"`, the output doesn't change. Additionally, the function can still go in the other direction ( F -> C), but to do so, it must be specified in the arguments:

```r
> convert_temp(70)
[1] 158
> convert_temp(70, unit = "C")
[1] 158
> convert_temp(158, unit = "F")
[1] 70
> convert_temp(158, "degrees")
Please enter a correct unit -- either F or C
NULL
```

#### Commenting your function 

Earlier in this lesson we discussed the importance of commenting your function for others' who read your code. So, let's practice that now with the function we just worked with: 

```r
convert_temp <- function(temp, unit = "C"){
if (unit=="C"){
    # if temp in C, convert to F
    D <- temp * (9/5) + 32
} else if (unit=="F") {
    # if temp in F, convert to C
    D <- (temp - 32) * (5/9)
} else {
    D <- message("Please enter a correct unit -- either F or C")
}
return(D)
}
```

Here, to make clear to anyone looking at the code, we've added two lines of comments to make explicitly clear what the code is doing. The longer your functions get, the more critical commenting your code will become.

### Summary

In this lesson, we've covered the components of a function in R (name, argument(s), and body) and broken down each of them using an example of converting temperatures between Celsius and Fahrenheit. We've discussed when to write a function, best practices for naming functions, how to run a function, and how to appropriately comment a function. The more you practice with functions early on as you learn R, the better you'll be as you start to write longer and longer pieces of code and analyze data. 

### Additional Resources
* [Chapter 19: Functions in r4ds](http://r4ds.had.co.nz/functions.html), by Hadley Wickham

### Slides and Video

![Writing Functions in R](https://www.youtube.com/watch?v=uPeWe16VyMA)

* [Slides](https://docs.google.com/presentation/d/1Q7pkb4lM8M8MRQzxCCfhXx8ddEi9XeaKSKT82OJAZX8/edit?usp=sharing)


{quiz, id: quiz_07_functions}

### Writing Functions in R quiz

{choose-answers: 4}
?1 If not defined explicitly within the function, what does a function return?

C) The last statement evaluated
m) `return()`
o) The first value calculated
o) Nothing
o) NA
o) The length of the function
o) An error message

{choose-answers: 4}
?1 To define what a function should return, what function do you use?

C) `return()`
m) The last statement evaluated
o) `pass()`
o) `output()`
o) `error()`
o) `help()`
o) `function()`
o) `returns()`
o) `user()`

{choose-answers:4}
?2 Which of the following statements is TRUE?

C) Function names may not contain spaces
o) UDFs can only take one input argument
o) Functions require comments (#) in the body to run
o) It's best to name functions with the name of existing functions
o) Default values for arguments cannot be specified
o) To run a function, the value provided for an argument must be numeric
 
{choose-answers: 4}
?3 To use the following function to determine the squared sum of the values 5 and 10, what would the function call look like?

```r
square_sum <- function(x,y) {
  (x + y)^2
}
```

C) square_sum(5,10)
C) square_sum(x = 5, y=10)
o) square_sum(x,y)
o) square_sum(x y)
o) square_sum(5 10)
o) function(square_sum(5,10)
o) function(square_sum(5 10)
o) function_square_sum(5, 10)
o) function_square_sum(5, 10)


{choose-answers: 4}
?3 To use the following function to determine the squared sum of the values 6 and 4, what would the function call look like?

```r
square_sum <- function(x,y) {
  (x + y)^2
}
```
C) square_sum(6,4)
C) square_sum(x = 6,y = 4)
o) square_sum(x,y)
o) square_sum(x y)
o) square_sum(6 4)
o) function(square_sum(6,4)
o) function(square_sum(6 4)
o) function_square_sum(6, 4)
o) function_square_sum(6, 4)


{choose-answers: 4, points: 2}
?4 Which of these is the BEST name for a function that predicts someone's birthday?

C) `predict_birthday`
o) `pb`
o) `predictbirthday`
o) `PredictBirthday`
o) `predict`
o) `birthday`
o) `Predict`
o) `Birthday`
o) `predbir`
o) `pred_bir`
o) `Predict_Birthday`

{choose-answers: 4, points: 2}
?4 Which of these is the BEST name for a function that predicts someone's age?

C) `predict_age`
o) `pb`
o) `predictage`
o) `PredictAge`
o) `predict`
o) `age`
o) `Predict`
o) `Age`
o) `preda`
o) `pred_a`
o) `Predict_Age`


{choose-answers: 4, points 3}
?5 Given the function below, what is the output of the command `simple_calc(2,5)`?

```r
simple_calc <- function(x, y){
a <- x + y
d <- a^2
return(d)
}
```

C) 49
m) 16
m) 64
o) 7
o) 25
o) 4
o) 1
o) 98
o) 3.5


{choose-answers: 4, points 3}
?5 Given the function below, what is the output of the command `simple_calc(3,5)`?

```r
simple_calc <- function(x, y){
a <- x + y
d <- a^2
return(d)
}
```

C) 64
m) 49
m) 16
o) 7
o) 25
o) 4
o) 1
o) 98
o) 3.5


{choose-answers: 4, points 3}
?5 Given the function below, what is the output of the command `simple_calc(1,3)`?

```r
simple_calc <- function(x, y){
a <- x + y
d <- a^2
return(d)
}
```

C) 16
m) 64
m) 49
o) 7
o) 25
o) 4
o) 1
o) 98
o) 3.5

{/quiz}


