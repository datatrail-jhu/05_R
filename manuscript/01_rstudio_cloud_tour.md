# RStudio Cloud Tour 

At this point in the course, you've been introduced to RStudio Cloud. You know that it's where you'll be writing code, and you've been briefly introduced to RStudio and RStudio Cloud. You've learned how to organize your files within RStudio Cloud for data science projects. And, you have worked with markdown files within RStudio Cloud. While you were introduced to the parts of RStudio previously, we'll review them in this lesson and then go into a little more depth to get you even more comfortable working in RStudio Cloud.

### Getting Started in RStudio Cloud

To get started working in [RStudio Cloud](rstudio.cloud), you'll want to go to [rstudio.cloud](rstudio.cloud) and log in using your RStudio Cloud login. You'll be logged into your home screen. As discussed previously, to get started working on a new project, you would click on the "New Project" blue icon toward the top right. This will create a new project. However, all your old projects will be listed at left underneath "Spaces." You can always return to an old project or start a new one.

![RStudio Cloud Home Screen - New Project ](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-1.png)

By starting a new project you'll be brought to a screen where three spaces are available. 

![RStudio Cloud Project](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-2.png)

However, if you remember from previously, there are four main quadrants when working in RStudio Cloud. To access the fourth space, you'll have to start a new R Script. To do so, you'll click on File, hover over New File from the drop-down menu that appears, and then click "R Script" from the drop-down menu. 

![Open up a new R Script](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-3.png)

This will open up a new R Script, which is currently called "Untitled1," which you can see on the tab at the top left of the quadrant has just appeared.

![RStudio Cloud](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-4.png)


### The Tour

Now that RStudio Cloud is opened and you have access to each of four quadrants, we can discuss and review each quadrant's purpose. We will go through each of the regions and describe some of their main functions, so follow along with each step and make sure you understand the function and how to access each part of RStudio Cloud on your own. But, it would be impossible to cover everything that RStudio can do, so we urge you to explore RStudio Cloud further on your own too! 

![RStudio's quadrants](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-5.png)


#### The menu bar

In addition to the four main quadrants, there is also a menu bar. The menu bar runs across the top of your screen and should have two rows. The first row should be a fairly standard menu, starting with "File" and "Edit." Below that, there is a row of icons that are shortcuts for functions that you'll frequently use. 

![The commonly used options of the main menu bar](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-6.png)

To start, let's explore the main sections of the menu bar that you will use. The first is the File menu. Here we can open new or saved files, save our current document, or close RStudio. As we saw earlier in this lesson, if you mouse over "New File", a new menu will appear that suggests the various file formats available to you. R Script and R Markdown files are the most common file types for use, but you can also generate R notebooks, web apps, websites, or slide presentations. If you click on any one of these, a new tab in the "Source" quadrant will open. We'll spend more time in a future lesson on R Markdown files and their use. 

![The File menu](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-7.png)

The Session menu has some R specific functions, in which you can restart, interrupt or terminate R - these can be helpful if R isn't behaving or is stuck and you want to stop what it is doing and start from scratch. 

![The Session menu](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-8.png)

The Tools menu is a treasure trove of functions for you to explore. For now, you should know that this is where you can go to install new packages (see the next lesson in this course!), set up your version control software (GitHub was discussed in the last course in this series!), and set your options and preferences for how RStudio looks and functions. For now, we will leave this alone, but be sure to explore these menus on your own once you have a bit more experience with RStudio and see what you can change to best suit your preferences! 

![The Tools menu](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-9.png)

#### Console

This region should look familiar to you - when you opened R, you were presented with the console. This is where you type and execute commands, and where the output of these commands is displayed. 

![The console](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-10.png)

To execute your first command, at the `>` prompt, try typing `1 + 1`. Then, hit enter. You should see the output `[1] 2` below your command. 

![Typing into the console and getting an output](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-11.png)

### Source: script editor panel 

However, often you want to write code and save it so that you can open the code again and re-run it later. This saved file with code in it is referred to as a **script**. When you want to write code and save it in a script, you'll do this in the Source panel.

To get started in your script file, copy and paste the following into your Source quadrant (top-right).

```r
example <- matrix(c(1, 2, 3, 4, 5, 6, 7, 8), nrow = 4, ncol = 2)
```

To run this code, you *can't* just hit enter (as you were able to do in the Console). Hitting enter will just bring your cursor to the next line in the script. Instead, with your cursor in the line of code you want to run, you can click on "Run" at the top right of your script file. This will execute the code in the Console.

**Note** Alternatively, to run code, with your cursor on the line of code you'd like to run, you could **hit 'ctrl + enter' to run that line of code**. This will save you *a lot* of time as you start writing a lot of code and analyzing data. Practice this keyboard shortcut now!

What this code does is create an object (we'll define what that is soon!) called 'example' that has the numbers 1 through 8 in four different rows and two different columns. To see what this object looks like, we'll take a look at the environment quadrant of RStudio Cloud. 

#### Environment (& History)

To view this object we've just created, you'll first want to ensure that the object was created. In the Environment quadrant, you should see that 'example' is now there. The object was created!

![The environment quadrant](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-12.png)

Then, just click anywhere on the "example" line, and a new tab on the Source quadrant should appear, showing the matrix you created.

![Your newly made object, opened in a new tab of the source panel](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-13.png)

RStudio Cloud also tells you some information about the object in the environment, like whether it is a list or a data frame or if it contains numbers, integers or characters. This is very helpful information to have as some functions only work with certain classes of data. We'll get into the details of all this later, but for now, knowing that this information is in the Environment tab is enough.

The quadrant has two other tabs running across the top of it. We'll just look at the History tab now. Your history tab should look something like this: 

![The history tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-14.png)

Here you will see the commands that we have run in this session of R. If you click on any one of them, you can click "To Console" or "To Source" and this will either rerun the command in the console, or will move the command to the source, respectively. 

![From History to Source](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-15.png)

Do so now for your `View(example)` object and send it to Source. 

![Sending 'View(example)' from History to Source](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-16.png)

This line of code is now in your Source document. When you save this document, you'll also have this line of code saved for future use.

#### Saving Script Files

Now that you've created a script with code in it, you likely want to save it. To do so, you'll want to click on the save icon. 

![Save Icon](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-17.png)

In RStudio Cloud this will open a Save File window. 

![Save File Window](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-18.png)

In the File Organization Course, you learned that code is saved in a directory called code. So, we'll first create a "New Folder". 

![New Folder](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-19.png)

We'll name this folder "code" by typing it in the box and clicking "OK". 

![Create code folder](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-20.png) 

After creating this new folder, as discussed in a previous lesson, you'll see along the top that you're now in the "code" directory. Within this folder, we'll create another new folder called "raw_code." 

![Create raw_code folder](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-21.png)

This is where we'll save this file as "R_basics.R" by typing that in the File name: box and clicking "Save."

![Save file by typing file name in "File name:" box](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-22.png)

This file name 'R_basics.R' will now show up in the tab at the top of the R Source quadrant.

### Files/Help/Plots/Packages/Viewer 

#### Files

You can also see where this file is saved using the fourth and final quadrant in RStudio Cloud that we'll discuss. In this final quadrant you'll see five tabs: Files, Plots, Packages, Help, and Viewer. 

![Files, Plots, Packages, Help, Viewer](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-23.png)

In Files, you can see everything in your current working directory. You should now be able to see the code folder you just created. 

![code directory in Files tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-24.png)

By clicking on that folder, you should then see the raw_code folder you created. 

![raw_code folder in Files tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-25.png)

By clicking on this, you'll see the script file you just saved! 

![R_basics.R is saved in code/raw_code/](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-26.png)

After you save a file in a folder, if you realize it's not where you wanted it, you do have the option to move it around. To do so, click on the check box of the file you want to move, and click on the "More" icon to expose options. Click through these to move your file to where you actually wanted it.

![The "More"" icon](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-27.png)

#### Plots 

In the Plots tab, if you generate a plot with your code, it will appear here. You can use the arrows to navigate to previously generated plots. The Zoom function will open the plot in a new window, that is much larger than the quadrant. Export is one way to save the plot. (Saving plots will be discussed in more detail in a future lesson.) The broom icon clears all plots from memory. 

![The plots tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-28.png)

#### Packages 

The Packages tab will be explored more in depth in the next lesson on R packages. Here you can see all the packages you have installed, load and unload these packages, and update them. 

![The packages tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-29.png)

#### Help 

The Help tab is where you find the documentation for your R packages and various functions. In the upper right of this panel there is a search function for when you have a specific function or package in question. Navigating this tab will be discussed in more detail in a later lesson in this course.

![The help tab](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-30.png)

### Swirl

Throughout the courses in this Course Set, we'll be using something called [Swirl modules](https://swirlstats.com/) to practice the R code learned in many of the lessons. These modules will all be run within RStudio Cloud. To make sure that you're comfortable using Swirl, we'll go through the steps on where to go to run Swirl and how to work through a module. This will be important as many of the quizzes accompanying these lessons will require you to use Swirl. Follow the steps in this section of the lesson to get started with your first Swirl module!

Throughout this Course Set, whenever you're asked to complete a Swirl module, you'll always start in the same place: the [RStudio Cloud Chromebook Data Science Space](http://bit.ly/cbds_projects). Click on [this link now](http://bit.ly/cbds_projects). If prompted, log into your RStudio Cloud account.


![Chromebook Data Science on RStudio Cloud](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-31.png)

Among the projects listed you'll see one called "swirl" (You may have to scroll down on the list to see it.). To the right of swirl, you'll want to click on "Copy".

![make a copy of "swirl" project](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-32.png)

This project contains *all* of the swirl modules you'll be completing throughout the quizzes in this course set. For each module you're supposed to complete, there will be a quiz question specifying which you're supposed to complete. 

But for now, let's just get comfortable with how swirl works.

Any time you are within this space and supposed to complete a swirl module you'll start by first loading the swirl package (it has already been installed in that space for you) and running the command `swirl()`:

```
## load package
library(swirl)

## start swirl
swirl()
```

As a reminder, to run code, with your cursor on the line of code you'd like to run, you can **hit 'ctrl + enter' to run that line of code**. Similarly, if there are multiple lines you want to run, you can highlight the lines you want to run and again hit 'ctrl + enter' to run those lines of code.

This will bring up a prompt asking you what swirl should call you. Type your first name as a response here and hit "enter."

![starting `swirl`](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-33.png)

Swirl will often send you some text to read. *Always read the text* as this text will help explain the background information you need *or* will provide you with information you need to answer the question. At this point, swirl is explaining that when you see `...`, that's when you should press "enter" to continue.

When you see `>` or a list of options (like `1:`, `2:`, `3`), that let's you know swirl is looking for something from you! When you see `>` that's a prompt letting you know swirl is expecting you to write some code. When you see a list of options, those are the possible answers to a question you're being asked. In these cases, you'll want to select the number corresponding to the right answer. For this practice in swirl, select 1, 2, or 3 and press enter.

![Getting started in `swirl`](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-34.png)

You'll then be given a number of options that you can use within `swirl` whenever you see the `>` prompt. Read the list here, but know that `info()` gives you this list of options again, `main()` returns you to swirl's main menu, and `bye()` saves your progress bug exits swirl.

![`swirl` menu options](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-35.png)

After this, you will be shown a list of courses. The list will be longer than what you see here, but we're showing this simple example to demonstrate that if you wanted to start on the course "CBDS Introduction to R", you would type 1. You'll be told which course to select throughout the course set.

![Selecting a course](images/01_rstudio_cloud_tour/01_R_rstudio_cloud_tour-36.png)

Note that for each quiz question you complete in `swirl`, upon completion, you'll receive a code. This code is to be entered as the answer to the quiz question on Leanpub.

That's a basic introduction to using `swirl`. You'll have lots of quiz questions that require you to use swirl in this Course Set, so be sure to walk through this introduction on RStudio Cloud now and get comfortable navigating within swirl.

### Summary

In this lesson we took a tour of RStudio Cloud. We became familiar with the main menu and its various menus. We looked at the Console, where R code is input and run. We then moved on to the Environment panel that lists all of the objects that have been created within an R session and allows you to view these objects in a new tab in Source. In this same quadrant, there is a History tab, that keeps a record of all commands that have been run. It also presents the option to either rerun the command in the Console, or send the command to Source, to be saved. Source is where you save your R commands. And the bottom right quadrant contains a listing of all the files in your working directory, displays generated plots, lists your installed packages, and supplies help files for when you need some assistance! Take some time to explore RStudio Cloud and get more comfortable navigating swirl on your own!

### Slides and Video

![RStudio Cloud Tour](https://www.youtube.com/watch?v=j9PcRpc8Tqc)

* [Slides](https://docs.google.com/presentation/d/17gq_-4nXwZRznS6OVxCwcZ6uYI_ym5mrO_3oNqqNFk4/edit?usp=sharing)


{quiz, id: quiz_01_rstudio_cloud_tour}

### RStudio Cloud Tour quiz

{choose-answers: 4, points: 2}
? How do you see a command you have previously run and save it to source?  

C) History tab > click on command to highlight > To Source
C) History tab > highlight command > To Source
o) Source > Save 
o) Console > Save as...
o) History tab > Save as...
o) Console > highlight code > To Source
o) Source > highlight code > To Console
o) Source > highlight code > 'cntrl + enter'
?
{choose-answers: 4}
? What is the name of the quadrant in the bottom left corner of RStudio Cloud, in the default layout? 

C) Console  
o) Source  
o) Environment  
o) Plots  
o) Help  
o) Files  
o) Packages  
o) History


{choose-answers: 4, points: 2}
? Which of the following is **not** one of the options available under the Global Options menu in Tools? 

C) Versions
C) Viewer
C) Console
C) Source
o) Packages  
o) Appearance   
o) Pane Layout
o) R Markdown  
o) Sweave  
o) Spelling
o) Git/SVN  
o) Publishing  
o) Terminal  
o) General  


{/quiz}
