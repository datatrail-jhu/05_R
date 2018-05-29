{
course-completeness: 100
course-attempts: 2
default-quiz-attempts: 2
default-random-choice-order: true
}

# What is R?

### Introduction to R

While you completed a project with Leanpub data using [RStudio Cloud](rstudio.cloud) in the intro course to this series, there wasn't a ton of detail about what R, RStudio, and RStudio Cloud actually are in those lessons. We'll discuss a few more details about R here in this introductory lesson and then will get into more and more detail about using R throughout this course. 

### The R programming language

R, most simply, is a programming language. Just like there are many different spoken languages throughout the world, there are many different programming languages. Similar to how each spoken language is used by a subset of the humans on this Earth, each programming language was created for a different group of people who code. You may have heard of other programming languages, such as C++, Java, or HMTL previously. These are all enormously popular programming languages, but each has what it does best along with its own disadvantages. For example, if you're interested in building software that runs really quickly, you may learn C++. If you want to build and edit websites, you would maybe start by learning HTML. And, Java may be most helpful if you want to build video games. 

![R](images/00_what_is_R/00_R_what_is_R-1.png)

Similarly, R has its strengths and weaknesses. R was designed to be helpful to those interested in statistical computing and graphics. That said, in its simplest form, R is a calculator. If you type '3 + 7' into the R console and hit _enter_, R will tell you the answer to that math problem is '10.'

![R is a calculator](images/00_what_is_R/00_R_what_is_R-2.png)
 
However, R is much more than *just* a calculator. It also has the ability to work with data, such as the information in spreadsheets. It's able to tell you how many rows are in your column. It's able to find the average age of individuals across a data set. It's able to create plots to show you how many males or females are included in your data set. And beyond data summary, you can run statistical analyses, write your own software, and carry out complicated analyses start to finish in R. So, while it is a calculator, it is much more than a calculator. It is a place where you can do all of your data analysis. RStudio makes the process of doing an analysis in R easier.

### RStudio

RStudio is a free, integrated development environment (IDE) for R. Generally, IDEs are software applications that allow software developers to program more efficiently, putting everything the programmer needs in one place. With regards to RStudio specifically, RStudio has a space for the programmer to code, a separate space for that code to run (the Console), a place to see all the objects created in the current session (the Workspace), and a place to see Plots that have been generated. All of these spaces are viewable in a single window, simplifying programming and data analysis. Those who work at RStudio seek to develop tools that support analysts to perform trustworthy and high quality analysis. Their singular goal is to make your life programming in RStudio easier! 

![RStudio IDE](images/00_what_is_R/00_R_what_is_R-3.png)

### RStudio Cloud

[RStudio Cloud](rstudio.cloud) is a version of RStudio that can run in the cloud. This means that regardless of what computer you're on, you can access the analysis you were doing previously in your RStudio Cloud session. Other than that, it has many of the same features and is being developed by the same group of people who developed the version of RStudio you download and use on your individual laptop. This means that in RStudio Cloud, like in RStudio, you have four main components, each of which is visible in the same window. To review from the introductory lesson of this series of courses, RStudio Cloud has the following four main components:

1. Scripting - where you write your code
2. Console - where your code runs 
3. Environment - where you can see what objects have been created during your analysis 
4. Files - where you can see all the files that are part of your project

![RStudio Cloud](images/00_what_is_R/00_R_what_is_R-4.png)

There are additional features that you can play around with; however, one important feature to note is that whenever you create a plot in RStudio or RStudio Cloud, it will be visible in the plots tab at the bottom right-hand of your screen. This, and a number of additional features will be discussed in more detail in the next lesson in this course.

![RStudio Cloud plots](images/00_what_is_R/00_R_what_is_R-5.png)

### Basic History 

Knowing the background of a programming language often helps to add some context. So, very briefly, R first appeared in 1993 and was developed to be very similar to another programming language, S. R was initially written by [Ross Ihaka](https://www.stat.auckland.ac.nz/~ihaka/) and [Robert Gentleman](https://www.linkedin.com/in/robert-gentleman-06845098/) in the Department of Statistics at the University of Auckland in New Zealand. Since its inception, many people have contributed code and improvements to R. And, since 1997, the "R Core Team" is responsible for all modifications to the language. R is an **open source language**. This means that the language is free to use and the source code is available to the general public.

As for RStudio, it was first released in 2011. It was founded by [J.J. Allaire](https://www.linkedin.com/in/jjallaire/), who is the company's current CEO. RStudio Cloud, the cloud-based version of RStudio, was first released for alpha testing (meaning it would have bugs and things that still needed to be fixed and will likely be updated significantly in the coming years) in 2017.

![R Basic History](images/00_what_is_R/00_R_what_is_R-6.png)

### Slides and Video

![What is R?](ADD VIDEO)

[Slides](https://docs.google.com/presentation/d/1-GwpqNvTqNtobrgF-o0SCD0SvUwlv1b_MYF8QnyMHJk/edit?usp=sharing)


{quiz, id: quiz_00_what_is_R}

### Welcome to the What is R? quiz

{choose-answers: 4}
? Which of the topics discussed refers to the programming language you'll use throughout this course?

C) R
m) RStudio
o) RStudio Cloud
o) Java
o) History
o) HTML
o) C++
o) Auckland

{choose-answers: 4}
? Which of the following was developed to increase programmers' efficiency using R?

C) RStudio
o) Gentleman 
o) Ihaka
o) Allaire
o) Wickham
o) Java
o) C++
o) HTML

{choose-answers: 4}
? What does it mean if a piece of software is open source?

C) The source code are available to the public, and use of the software is free.
o) The source code are proprietary, but the software is free.
o) The source code are available to the public, but the software costs money to use.
o) The source code are proprietary, and the software costs money to use.
o) The source code are editable by anyone, so anyone who makes edits will make money.
o) The source code are no longer editable. No changes to the language will be made.
o) The source code no longer has any bugs. All bugs have been fixed. 

{/quiz}

