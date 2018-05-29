# Getting Help in R

In a lesson in an earlier course, we discussed some basic guidelines for carrying out an effective Google Search. Now that you've been introduced to the basics of R, we wanted to guide you to some *incredibly* helpful resources that can help you work through issues when you're trying to write your own R code.

### R Help: `?`

To access documentation directly within RStudio, you can type a question mark followed by the function, dataset, or object within the R Console directly. The output for this documentation will display in the Help window at the bottom-right hand of RStudio. 

For example, earlier in this course, you were introduced to the function `summary()` in R. If you later can't remember what this function does, but you can remember the function, you can always type `?summary` in your Console. The following will display in the Help tab:

![?summary documentation](images/11_help_in_R/11_R_help_in_R-6.png)

In this documentation we see:
* A general description of what the summary() function can be used for
* what package the function is from -- "base" means it's part of the base installation in R, rather than from a specific package
* the syntax you should use to carry out this function
* some sample code

As you work in R, you'll find that some documentation is more helpful than others. Some packages and functions have incredibly helpful documentation pages. Others are less helpful. A thing to remember is that humans are responsible for writing this documentation. It's great when someone who's really great at documenting software or who has the time to do so write great documentation pages. However, for those times when the documentation proves less than helpful, there are other places you can look to for help.

### Stack Overflow

[Stack Overflow](stackoverflow.com) is an "online community for programmers." Stack Overflow is not just a place for R programmers, but rather, is a place to ask and answer questions about any programming language. That said, Stack Overflow has hundreds of thousands of questions and and answers from R users. 

#### How Stack Overflow works

On Stack Overflow, people (who have logins on the website) can ask questions. Then, others on the site can provide answers. The user who originally posed the question can mark one answer as the "accepted" answer. Any user, however, can up-vote an answer, helping it rise to the top of the answer section. This means that when someone else comes across this question, they come across the best answers first. 

Additionally, questions can be tagged with their subject area. For example, a user looking for help coding in R would tag their question with the "r" tag to help direct this question to the right community for answering.

![Stack Overflow Homepage](images/11_help_in_R/11_R_help_in_R-7.png)

#### Getting Answers

Stack Overflow is a place for specific coding questions and answers. It is *not* a discussion board nor is it a place for polling. This design is intended to help you quickly get an answer. In that spirit, anyone can search questions and answers, regardless of whether they have an account on the site. All that said, before asking a question on Stack Overflow, it's best to check to see if someone else has already asked a similar question. 

For example, if you were trying to learn more about how to work with objects in R, you would maybe type "objects in R" into the search bar. The results would look something like this:

![Stack Overflow Search Output](images/11_help_in_R/11_R_help_in_R-8.png)

For each search result, you will see:
* the question posed
* the tags accompanying that post
* the number of responses for the question
* when the question was posted and by whom.

Clicking on the link will provide you with the full question and the posted answers. You'll most often find that the question you have has already been answered on Stack Overflow, which is great. This way you get an answer immediately and don't have to wait!

If, after searching questions that already exist, you still cannot find an answer to your question, you can post a question on Stack Overflow. this will require you to Sign Up for an account.

Once you've created an account and logged in, you will see a blue "Ask Question" box in the top right-hand of your screen.

![Ask Question](images/11_help_in_R/11_R_help_in_R-9.png)

Clicking on "Ask Question" will bring you to an additional screen reminding you of how to proceed before posting a question (search for existing answers!) and how to post a question

![Posting a Question Guidelines](images/11_help_in_R/11_R_help_in_R-10.png)

#### Reproducible Examples (reprex)

When posting a question on Stack Overflow, or anywhere really, it's always best to post what is known as a reproducible example, or **reprex**.

A reprex is the simplest bit of code possible needed to ask your question from start to finish. By including this code in your question on Stack Overflow, others can see what issue you have run into and hopefully help you find a solution!

By simplest bit of code possible, this means that the code:
1. Must be **reproducible** -- it must run start to finish, up until the part where you're running into trouble (This includes any packages you've loaded and all necessary objects)
2. Should be **minimal** -- Remove any code that is in your script but that is not directly related to the problem at hand. Often this requires making a smaller dataset than the one you're working with.

By generating a reprex, you'll often figure out the answer to your question in the process, which is great! The rest of the time, by creating the reprex and including it in your question, others are able to help you as quickly as possible, which is also great!

#### Providing Help to Others

Stack Overflow allows users with a login to ask **and answer** questions on Stack Overflow. While in the beginning you'll likely just be searching for (and getting) answers to questions, as you become more of an expert, answering others' questions is a great way to help the community! 

That said, it's probably no surprise that sometimes people can be mean to others on the Internet. The R community does its best to be a welcoming community. Hopefully, you will never run into people who are mean on Stack Overflow, and even more importantly, when you become an expert in R and answer others' questions online, it's important to remember that everyone starts as a beginner. If someone's question isn't perfectly asked or their reprex isn't perfect, let it pass. Be as helpful and kind as you can as you interact with others online.

### RStudio Community

In addition to Stack Overflow, [RStudio Community](https://community.rstudio.com/) is an online community for questions and answers that is specifically geared toward R users.

![RStudio Community](images/11_help_in_R/11_R_help_in_R-13.png)

With this interface, in addition to the Topic, you can see the Category (similar to tags in Stack Overflow) and the number of Replies and Views for each topic. You can sort by any of these categories by clicking on the label at the top. Or, you can search specific questions or topics. Clicking on any topic will direct you to a new window where you can sort through the answers for each question. 

### Additional Community Resources

The R community is a welcoming and helpful community. Many people go years as R users before they learn what a rich community there is out there. We're hoping to change that by introducing new users to a number of resources that will help them feel more welcome to the large community of individuals using R! Below is a short list of ways to connect with the R community:

* [R for Data Science Learning Community](https://www.jessemaegan.com/post/r4ds-the-next-iteration/) - a welcoming and helpful community for those new to R and data science
* [Twitter](https://twitter.com) - Using or searching the hashtag #rstats can be incredibly helpful and can connect you to others who use R
* [ROpenSci](https://ropensci.org/) - an online community of developers developing tools for open science
* [R Project Help in R](https://www.r-project.org/help.html)


### Slides and Video

![Getting Help in R](UPDATE LINK)

* [Slides](https://docs.google.com/presentation/d/1xDXjuZZ8OifFKW3MzKhQL0kI5f3XcCfHn9oHgyhpyMk/edit?usp=sharing)
   
{quiz, id: quiz_11_help_in_R}
   
### Getting Help in R quiz
   
? When you get stuck in R, what's the first thing you should do?

a) Create a reprex
B) Search for an existing answer on the Internet
c) Ask a question on Stack Overflow
d) Ask a question on the RStudio Community

? When answering a question on Stack Overflow, what should you avoid?

A) being a jerk
b) being kind
c) being helpful
d) putting yourself in the questioners shoes
e) being considerate

? What is a reprex?

a) the code from your complicated script copy and pasted onto Stack Overflow
b) a way to pattern match used across programming languages
C) the simplest piece of example code possible that reproduces an issue you're having 
d) the code from your complicated script copy and pushed to GitHub

{/quiz}
