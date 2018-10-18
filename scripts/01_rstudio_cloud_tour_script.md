At this point in the course, you've been introduced to R Studio Cloud. You know that it's where you'll be writing code, you've learned how to organize your files within R Studio Cloud for data science projects, and have worked with markdown files within R Studio. While you were introduced to the parts of R Studio previously, we'll review them in this lesson and then go into a little more depth to get you even more comfortable working in R Studio Cloud.

To get started working in R Studio Cloud, you'll want to go to r studio dot cloud and log in using your R Studio Cloud login. You'll be logged into your home screen. As discussed previously, to get started working on a new project, you would click on the "New Project" blue icon toward the top right. This will create a new project. However, all your old projects will be listed at left underneath "Spaces." You can always return to an old project or start a new one.

By starting a new project you'll be brought to a screen where three spaces are available. 

However, if you remember from previously, there are four main quadrants when working in R Studio Cloud. To access the fourth space, you'll have to start a new R Script. To do so, you'll click on File, hover over New File from the drop-down menu that appears, and then click "R Script" from the drop-down menu. 

This will open up a new R Script, which is currently called "Untitled1," which you can see on the tab at the top left of the quadrant has just appeared.

Now that R Studio Cloud is opened and you have access to each of four quadrants, we can discuss and review each quadrant's purpose. We will go through each of the regions and describe some of their main functions, so follow along with each step and make sure you understand the function and how to access each part of R Studio Cloud on your own. But, it would be impossible to cover everything that R Studio can do, so we urge you to explore R Studio Cloud further on your own too! 

In addition to the four main quadrants, there is also a menu bar. The menu bar runs across the top of your screen and should have two rows. The first row should be a fairly standard menu, starting with "File" and "Edit." Below that, there is a row of icons that are shortcuts for functions that you'll frequently use. 

To start, let's explore the main sections of the menu bar that you will use. The first is the File menu. Here we can open new or saved files, save our current document, or close R Studio. As we saw earlier in this lesson, if you mouse over "New File", a new menu will appear that suggests the various file formats available to you. R Script and R Markdown files are the most common file types for use, but you can also generate R notebooks, web apps, websites, or slide presentations. If you click on any one of these, a new tab in the "Source" quadrant will open. We'll spend more time in a future lesson on R Markdown files and their use. 

The Session menu has some R specific functions, in which you can restart, interrupt or terminate R - these can be helpful if R isn't behaving or is stuck and you want to stop what it is doing and start from scratch. 

The Tools menu is a treasure trove of functions for you to explore. For now, you should know that this is where you can go to install new packages (see the next lesson in this course!), set up your version control software (GitHub was discussed in the last course in this series!), and set your options and preferences for how R Studio looks and functions. For now, we will leave this alone, but be sure to explore these menus on your own once you have a bit more experience with R Studio and see what you can change to best suit your preferences! 

Having taken a look at the menus, now let's return to discussing the four main quadrants. First, we'll discuss the Console. This region should look familiar to you - when you opened R, you were presented with the console. This is where you type and execute commands, and where the output of these commands is displayed. To execute your first command, try typing 1 plus 1 in the console. Then, hit enter. You should see the output open brackets 1 closed brackets 2 appear below your command. 

However, often you want to write code and save it so that you can open the code again and re-run it later. This saved file with code in it is referred to as a script. When you want to write code and save it in a script, you'll do this in the Source panel. To get started in your script file, type the code you see here into your Source quadrant. To run this code, you can't just hit enter (as you were able to do in the Console). Hitting enter will just bring your cursor to the next line in the script. Instead, with your cursor in the line of code you want to run, you can click on "Run" at the top right of your script file. This will execute the code in the Console. Alternatively, to run code, with your cursor on the line of code you'd like to run, you could hit control and enter to run that line of code. This will save you a lot of time as you start writing a lot of code and analyzing data. Practice this keyboard shortcut now! What this code does is create an object, which we'll define soon!, called 'example' that has the numbers 1 through 8 in four different rows and two different columns. To see what this object looks like, we'll take a look at the environment quadrant of R Studio Cloud. 

To view this object we've just created, you'll first want to ensure that the object was created. In the Environment quadrant, you should see that 'example' is now there. The object was created!

Then, just click anywhere on the "example" line, and a new tab on the Source quadrant should appear, showing the matrix you created. R Studio Cloud also tells you some information about the object in the environment, like whether it is a list or a data frame or if it contains numbers, integers or characters. This is very helpful information to have as some functions only work with certain classes of data. We'll get into the details of all this later, but for now, knowing that this information is in the Environment tab is enough.

The quadrant has two other tabs running across the top of it. We'll just look at the History tab now. Your history tab should look something like this. Here you will see the commands that we have run in this session of R. 

If you click on any one of them, you can click "To Console" or "To Source" and this will either rerun the command in the console, or will move the command to the source, respectively. 

Do so now for your View example line of code and send it to Source. This code is now in your Source quadrant.

Now that you've created a script with code in it, you may want to save it. To do so, you'll want to click on the save icon. 

In R Studio Cloud this will open a Save File window. 

In the File Organization Course, you learned that code is saved in a directory called code. So, we'll first create a "New Folder". 

We'll name this folder "code" by typing it in the box and clicking "OK". 

After creating this new folder, as discussed in a previous lesson, you'll see along the top that you're now in the "code" directory. Within this folder, we'll create another new folder called "raw_code." 

This is where we'll save this file as "R underscore basics dot R" by typing that in the File name: box and clicking "Save."

This file name 'R underscore basics dot R' will now show up in the tab at the top of the R Source quadrant. You can also see where this file is saved using the fourth and final quadrant in R Studio Cloud that we'll discuss. In this final quadrant you'll see five tabs: Files, Plots, Packages, Help, and Viewer. 

In Files, you can see everything in your current working directory. You should now be able to see the code folder you just created. 

By clicking on that folder, you should then see the raw_code folder you created. 

By clicking on this, you'll see the script file you just saved! 

After you save a file in a folder, if you realize it's not where you wanted it, you do have the option to move it around. To do so, click on the check box of the file you want to move, and click on the "More" icon to expose options. Click through these to move your file to where you actually wanted it.

In the Plots tab, if you generate a plot with your code, it will appear here. You can use the arrows to navigate to previously generated plots. The Zoom function will open the plot in a new window, that is much larger than the quadrant. Export is one way to save the plot. (Saving plots will be discussed in more detail in a future lesson.) The broom icon clears all plots from memory. 

The Packages tab will be explored more in depth in the next lesson on R packages. Here you can see all the packages you have installed, load and unload these packages, and update them. 

The Help tab is where you find the documentation for your R packages and various functions. In the upper right of this panel there is a search function for when you have a specific function or package in question. Navigating this tab will be discussed in more detail in a later lesson in this course.

Throughout the courses in this Course Set, we'll be using something called Swirl modules to practice the R code learned in many of the lessons. These modules will all be run within R Studio Cloud. To make sure that you're comfortable using Swirl, we'll go through the steps on where to go to run Swirl and how to work through a module. This will be important as many of the quizzes accompanying these lessons will require you to use Swirl. Follow the steps in this section of the lesson to get started with your first Swirl module! Throughout this Course Set, whenever you're asked to complete a Swirl module, you'll always start in the same place: the R Studio Cloud Chromebook Data Science Space using the link you see at the bottom on the video. Go to this link now. If prompted, log into your R Studio Cloud account.

Among the projects listed you'll see one called "swirl". To the right of swirl, you'll want to click on "Copy". This project contains *all* of the swirl modules you'll be completing throughout the quizzes in this course set. For each module you're supposed to complete, there will be a quiz question specifying which you're supposed to complete. 

But for now, let's just get comfortable with how swirl works. Any time you are within this space and supposed to complete a swirl module you'll start by running the command swirl. As a reminder, to run code, with your cursor on the line of code you'd like to run, you can hit ctrl and enter to run that line of code. Similarly, if there are multiple lines you want to run, you can highlight the lines you want to run and again hit ctrl and enter' to run those lines of code.

This will bring up a prompt asking you what swirl should call you. Type your first name as a response here and hit "enter." Swirl will often send you some text to read. *Always read the text* as this text will help explain the background information you need *or* will provide you with information you need to answer the question. At this point, swirl is explaining that when you see three dots, that's when you should press "enter" to continue. When you see `the greater than R prompt` or a list of numeric options, that let's you know swirl is looking for something from you! When you see the R prompt that's a prompt letting you know swirl is expecting you to write some code. When you see a list of options, those are the possible answers to a question you're being asked. In these cases, you'll want to select the number corresponding to the right answer. For this practice in swirl, select 1, 2, or 3 and press enter.

You'll then be given a number of options that you can use within `swirl` whenever you see the R prompt. Read the list here, but know that `info` gives you this list of options again, `main` returns you to swirl's main menu, and `bye` saves your progress bug exits swirl.

After this, you will be shown a list of courses. The list will be longer than what you see here, but we're showing this simple example to demonstrate that if you wanted to start on the course "CBDS Introduction to R", you would type 1. You'll be told which course to select throughout the course set. Note that for each quiz question you complete in `swirl`, upon completion, you'll receive a code. This code is to be entered as the answer to the quiz question on Leanpub. That's a basic introduction to using `swirl`. You'll have lots of quiz questions that require you to use swirl in this Course Set, so be sure to walk through this introduction on R Studio Cloud now and get comfortable navigating within swirl.

In this lesson we took a tour of R Studio Cloud. We became familiar with the main menu and its various menus. We looked at the Console, where R code is input and run. We then moved on to the Environment panel that lists all of the objects that have been created within an R session and allows you to view these objects in a new tab in Source. In this same quadrant, there is a History tab, that keeps a record of all commands that have been run. It also presents the option to either rerun the command in the Console, or send the command to Source, to be saved. Source is where you save your R commands. And the bottom right quadrant contains a listing of all the files in your working directory, displays generated plots, lists your installed packages, and supplies help files for when you need some assistance! Take some time to explore R Studio Cloud on your own and get more comfortable navigating swirl!
