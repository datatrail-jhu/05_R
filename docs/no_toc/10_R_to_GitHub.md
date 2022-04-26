---
title: "Untitled"
output: html_document
date: '2022-04-11'
---



# Pushing Code from R to GitHub

In the previous course in this series, you learned the basics of version control using git commands and GitHub. Through the lessons in this course you learned the basics of coding in R. Throughout the rest of the courses in the Cloud-based Data Science series we will continue to use R and GitHub extensively, so we figure it's best to get some practice with this workflow now, before any projects are due.

### GitHub repository: `my_first_project`

In the Version Control course you set up a GitHub repository called `my_first_project` where there were a number of directories with the following file structure:

* data/
  * raw_data/
  * tidy_data/
* code/
  * raw_code/
  * final_code/
* figures/
  * exploratory_figures/
  * explanatory_figures/
* products/
  * writing/

If you created that project in RStudio Cloud and pushed it to GitHub, go to that project on RStudio Cloud now.

{format: png}
![RStudio Cloud project](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_157)

If you haven't yet created the `my_first_project` project on RStudio Cloud and pushed it to GitHub, do that now.

Before we move on, a quick reminder: you won't see the folder structure that you created on GitHub. Unfortunately, a folder structure won't be pushed to GitHub unless the folders contain at least a file. No worries though! We're about to start populating this project with some code right now! Then, you'll start to see some of the folders you've created!

{format: png}
![`my_first_project`](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_75)

### Adding code to your GitHub project

Now that you've made your way back to your `my_first_project` repository, you can go to the "Terminal" in RStudio Cloud. Here, if you haven't made any changes since the last time you pushed to GitHub, when you type `git status` you should get a message letting you know that "Your branch is up-to-date."

{format: png}
![`git status`](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_150)

#### Adding an R script

To get started adding some code to this repository, let's just first create an R Script (.r file), and add some code.

To do so, in the menu along the top within RStudio Cloud click on File > New File > R Script.

{format: png}
![New R Script](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_162)

This will open a blank file (currently titled "Untitled1") in the scripting area of RStudio Cloud.

As this is just an example, add two lines of code to this file:

```r
# Let's get started
summary(mtcars$mpg)
```

{format: png}
![R Script in RStudio Cloud](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_167)

Now that there is some code in that R Script file, let's save it by going to File > Save As...

{format: png}
![Save As...](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_172)

We'll save this file in the code/raw_code directory.  Navigate to this directory. Then save the file as "mtcars_code.r" by typing this in the "File name" box at the top of the save File window. Click "Save". The new file name will show up along the tab at the top in the scripting are of RStudio Cloud.

{format: png}
![Save file in code/raw_code](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_177)


#### Adding an .Rmd file

In this course we also learned how to generate R Markdown files (.Rmd). So, we might as well generate one of them now before pushing our changes to GitHub.

To get started go to File > New File > R Markdown...

{format: png}
![New R Markdown File](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_182)


In the window that pops up, add the title "mtcars" and your name in the Author box. Click 'OK'.

{format: png}
![Info for Rmd file](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_187)

Replace the default text you see in the .Rmd document with the text and code you see here in this 'Untitled1' .Rmd document.

{format: png}
![New Rmd document](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_191)

Once that's completed, save your file as "mtcars.Rmd", again in the code/raw_code directory.

Tabs for both the .r file and .Rmd file you created in this lesson should now be visible in the scripting area of R Studio Cloud.

{format: png}
![Save and knit file](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_196)

Before we push these changes to GitHub, let's knit the .Rmd file to an HTML document. To do so, click "Knit" at the top of your .Rmd file tab.

The rendered HTML document should pop up in a new window.

{format: png}
![HTML document](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_202)

Additionally, there should now be a "mtcars.html" file in the "Files" window of RStudio Cloud along with "mtcars.Rmd" and "mtcars_code.r."

{format: png}
![Files tab in RStudio Cloud](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_206)

#### Pushing to GitHub

If you were to go back to the Terminal and type `git status` and hit "enter", the output should indicate that three new files have been created that are not yet being tracked by git.

{format: png}
![`git status`](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_213)


To add these to GitHub, you'll want to run:

```
git add .
git commit -m "add mtcars scripts"
git push
```

{format: png}
![add, commit, push](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_221)


In this process, however, git may ask you who you are. It will tell you that you have to configure your GitHub identity, using commands similar to these, but where you replace the email address and username below with the email address used to set up your GitHub account and your GitHub username:

```
git config --global user.email jane.everyday.doe@gmail.com
git config --global user.name janeeverydaydoe
```

{format: png}
![git config](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3bb9271f0d_0_28)


One this has been established, you can then rerun:

```
git commit -m "add mtcars scripts"
```
The output will indicate that those three files have been committed to GitHub.

{format: png}
![`git commit`](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3bb9271f0d_0_33)


When you then go to run `git push`, you may be asked for your Username and GitHub password. After entering them, you will get output that indicates that your files have been successfully pushed to GitHub.

{format: png}
![input username and password to push](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_228)

You can now go to your repository on GitHub. You'll see the commit message you just specified and will find the files you pushed within code/raw_code on your GitHub repository!

{format: png}
![code has been pushed to GitHub repository](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/export/png?id=1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ&pageid=g3ba6176ae9_0_237)

### Summary

In this lesson we went through all the steps of making changes to a project in RStudio Cloud and how to push those changes to an existing GitHub repository that you had previously cloned into RStudio Cloud. The more comfortable you are with the steps in this lesson, the easier it will be for you to carry out future data science projects using RStudio Cloud and GitHub.

### Slides and Video

![Pushing Code from R to GitHub](https://youtu.be/X38P9vn3NNM)

* [Slides](https://docs.google.com/presentation/d/1nNKiebsQieBUr645KDfMmbBFr26J2HQ0FAFH8WuSBQQ/edit?usp=sharing)
