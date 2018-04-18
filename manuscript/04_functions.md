# Writing Functions in R

User Defined Functions (UDFs) are functions beyond the functions that come with R and are written by users. For instance, if you like to repeat a task over and over, instead of running a collection of code each time, you can bundle your code in a funciton and just run the function. Here is an easy example. 

Imagine you need to convert Celsius degree to Fahrenheit. You want to know what 0, 20, and 100 degrees Celsius are in Fahrenheit. If you remember from your science class T(°F) = T(°C) × 9/5 + 32. So to calculate what 0, 20, and 100 degree Celsius are you can do the calculation above for each temperature. But you could also write a simple function that takes a degree Celsius as an input and returns a value in Fahrenheit. So each time you want to know a degree in Fahrenheit, you run your function instead of running the calculations. Here is your function.

```r
cel_to_far <- function(c){
f <- c * (9/5) + 32
return(f)
}
```

`cel_to_far` is the name of the function. You can choose anything else you like. This function takes the value `c` as input, multiplies it by 9 over 5, adds 32 to it, and then return the calculated value as outpyt. The `return` command returns the final value that you are interested in. So now, each time you want to convert Celsius to Fahrenheit just "call" the function and "pass" the Celsius degree as an input to find the degree in Fahrenheit. Something like this:

```r
cel_to_far(70)
```

This is as simple as a function in R can get. You can write more complicated functions the run pages and pages of code but the basic idea is the same. Functions help you avoid running multiple lines of code and instead run the function name. A function has a name, some arguments that are used as input to the function within paranthesis (). The body of the function are included in curly braces {}. 

Now that we know what the basice structure of the function is, let's make it a little bit fancier. For instance, when the function is called, we like it to return a sentence that is more clear. The function `paste` combines the text with the value of variable `f`.

```r
cel_to_far <- function(c){
f <- c * (9/5) + 32
return(paste("The entered Celsius degree in Fahrenheit is", f))
}
```


Functions do not necessarily need inputs. For instance, we can write a function that can only be called by `cel_to_far()` and no input is passed in the function. However, after running the function, a prompt appears asking the user to enter a value.

```r
cel_to_far <- function(){
c <- readline(prompt="Enter a value in Celsius: ")
f <- as.integer(c) * (9/5) + 32
return(paste("The entered Celsius degree in Fahrenheit is", f))
}
```

Here are some important notes about writing functions: a function can require multiple inputs. The can also have one or more return values (the output). When writing functions, make sure that you choose a name that is not already used by R. For instance, you can't use `mean` as a function name since it's already used by R. The return statement in a function is not necessary but it's recommended if you want to access the output value outside of the function. 


### Slides and Video

![Functions in R]()

* [Slides](https://docs.google.com/presentation/d/1Q7pkb4lM8M8MRQzxCCfhXx8ddEi9XeaKSKT82OJAZX8/edit?usp=sharing)


{quiz, id: quiz_04_functions}

### Functions in R quiz

? Which of the following statements is True?

a) A function must have an input and an output
b) A function must have an input but an output is not necessary.
c) A function must have an output but an input is not necessary.
D) Both input and output are not necessary.

? Given the function below, what is the output of the command `simple_calc(2,5)`?

```r
simple_calc <- function(x, y){
a <- x + y
d <- a^2
return(d)
}
```

a) 7
B) 49
c) 25
d) 4

{/quiz}

