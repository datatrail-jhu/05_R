In the previous course in this series, you learned the basics of version control using git commands and git hub. Through the lessons in this course you learned the basics of coding in R. Throughout the rest of the courses in the Chromebook Data Science series we will continue to use R and git hub extensively, so we figure it's best to get some practice with this workflow now, before any projects are due.

In the Version Control course you set up a git hub repository called my underscore first underscore project where there were a number of directories with the following file structure. 

If you created that project in R Studio Cloud and pushed it to git hub, go to that project on R Studio Cloud now. 

If you haven't yet created the `my underscore first underscore project` project on R Studio Cloud and pushed it to git hub, do that now. Before we move on, a quick reminder: you won't see the folder structure that you created on git hub. Unfortunately, a folder structure won't be pushed to git hub unless the folders contain at least a file. No worries though! We're about to start populating this project with some code right now! Then, you'll start to see some of the folders you've created! Now, go to the  project in R Studio Cloud where you've cloned this git hub repository.

Now that you've made your way back to your `my underscore first underscore project` project, you can go to the "Terminal" in R Studio Cloud. Here, if you haven't made any changes since the last time you pushed to git hub, when you type `git status` you should get a message letting you know that "Your branch is up-to-date."

To get started adding some code to this repository, let's just first create an R Script, and add some code. To do so, in the menu along the top within R Studio Cloud click on File, New File, R Script.

This will open a blank file currently titled "Untitled1" in the scripting area of R Studio Cloud. As this is just an example, add the two lines of code you see here to this file.

Now that there is some code in that R Script file, let's save it by going to File, Save As.

We'll save this file in the raw underscore code directory within the code directory.  Navigate to this directory. Then save the file as "m t cars underscore code dot r" by typing this in the "File name" box at the top of the save File window. Click "Save". The new file name will show up along the tab at the top in the scripting are of R Studio Cloud.

In this course we also learned how to generate R Markdown files. So, we mine as well generate one of them now before pushing our changes to git hub. To get started go to File, New File, R Markdown.

In the window that pops up, add the title "m t cars" and your name in the Author box. Click 'OK'.

Replace the default text you see in the dot R m d document with the text and code you see here in this 'Untitled1' dot R m d document.

Once that's completed, save your file as " m t cars dot R m d", again in the code raw underscore code directory. Tabs for both the dot r file and dot R m d file you created in this lesson should now be visible in the scripting area of R Studio Cloud. Before we push these changes to git hub, let's knit the dot r m d file to an H T M L document. To do so, click "Knit" at the top of your dot r m d file tab.

The rendered HTML document should pop up in a new window.

Additionally, there should now be a "m t cars dot h t m l" file in the "Files" window of R Studio Cloud along with "m t cars dot r m d" and "m t cars underscore code dot r."

If you were to go back to the Terminal and type `git status` and hit "enter", the output should indicate that three new files have been created that are not yet being tracked by git. 

To add these to git hub, you'll want to run git add dot. Then, you'd want to run git commit dash m quotes add m t cars scripts end quotes. Finally, you'd run git push.

In this process, however, git may ask you who you are. It will tell you that you have to configure your git hub identity, using commands similar to these, but where you replace the email address and username here with the email address used to set up your git hub account and your git hub username:

One this has been established, you can then rerun git commit dash m quotes add m t cars scripts end quotes. The output will indicate that those three files have been committed to git hub.

When you then go to run `git push`, you may be asked for your Username and git hub password. After entering them, you will get output that indicates that your files have been successfully pushed to git hub.

You can now go to your repository on git hub. You'll see the commit message you just specified and will find the files you pushed within code/raw_code on your git hub repository! In this lesson we went through all the steps of making changes to a project in R Studio Cloud and how to push those changes to an existing git hub repository that you had previously cloned into R Studio Cloud. The more comfortable you are with the steps in this lesson, the easier it will be for you to carry out future data science projects using R Studio Cloud and git hub.
