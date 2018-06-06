In previous lectures you have learned how to Create a GitHub repository and how to Use R Markdown for combining R code and text. Now we are going to use these two skills to create a website from within R. At the end of this lecture you will have your own personal website made with R!

GitHub has the nice property that it can automatically host websites for you from a repository. While this can de done for any repository, there is a special case: the your Username dot git hub dot com repository that makes setting up your own website a little bit simpler. We will start here because it's the most straightforward case. We'll work through an example for someone whose GitHub username is Jane Everyday Doe, but you should follow along and complete each step using your own GitHub account. To get started, first log in to git hub dot com and create a new repository. 

This new repository needs to use this special name Jane Everyday Doe dot git hub dot com. Yay, we now have our repository to get started!

Now we are going to start putting your website together. We need to keep our files in sync with GitHub, and to do so we will clone the repository to work on it within RStudio Cloud. That is, we will clone the username slash username dot git hub dot com repository. For Jane Everyday Doe that would be Jane Everyday Doe slash Jane Everyday Doe dot git hub dot com. We will do this via the terminal from RStudio Cloud. Once you have are in the terminal, you'll want to run git clone https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com.git We now have completed the necessary GitHub setup!

It's time to start working on our website! In the terminal access the username dot github dot com repository using the change directory command, cd. For Jane Everyday Doe that would be c d jane everyday doe dot git hub dot com.

The directory is empty and we can almost start our website. There is one more piece we need to do that is rather obscure. Something we haven't talked about is that GitHub was initially setup for hosting Jekyll static websites and that is still the default at this time. But we are not using Jekyll and we need to tell git hub that. To do so we need to create the hidden file dot no jekyll and version control it. You can create the file using the touch command in the terminal in RStudio Cloud. We haven't discussed the command touch or hidden files yet, so now is a great time to explain briefly that touch simply creates an empty file and hidden files are files that start with a period in the file name. Despite being hidden, we check the files including the hidden files using the  command l s dash a. l s, as discussed previously, stands for list and the dash a option states that we want to also display hidden files. When we run this command, we see the dot no jekyll file has been created.

Cool, we now have the required dot no jekyll file! But, it's not on Git Hub yet. So, we need to version control it. You can do so in the R Studio Cloud terminal window using the commands you see here.

At this point, if you're following along, your repo should look very similar to what you see here. Ok, now we can make the website! First, web pages display H T M L code. With that knowledge, we are going to take advantage of another nice property of the web.  If a directory contains an index dot h t m l file, then that file is displayed on the web browser when someone accesses the web address. In other words, index dot html is the default H T M L file that is displayed. This means that we need to create an index.html file. How can we do that from R?

Well, we learned that R m d files can be knit into .html documents, so let's start by creating an index dot R m d file inside the username dot git hub dot com directory. Here, lets take advantage of the nice RStudio Cloud menus. Go to File, New File,R Markdown. If you prompted to install packages, click yes to install them. 

Then ensure Document is selected along the left and HTML is selected for the output format. Add a title. Click OK.

Now let's save it as index dot R m d. go to File, Save As then type the index dot R m d in the file name box, making sure that it's saved inside the username dot git hub dot com directory. In JaneEverydayDoe's case, the relative file path would be jane everyday doe dot git hub dot com slash index dot R m d. Now click on the knit button and R to create the index dot h t m l file.

Just so we can see the website in action, lets publish it. What does that mean? Well, we have the index dot h t m l file in our computer but it's not on Git Hub's computers. So we need to version control the index dot h t m l file. And, let's also version control the index dot R m d  source file) by pushing it to GitHub. In the terminal window in RStudio Cloud, run the following commands.

And after a few seconds or a minute or so, you can view your website at https://username.github.io. For JaneEverydayDoe that is https://janeeverydaydoe.github.io/ and it looks like this. Ok, now we have a website that is publicly available and that we made with R. Isn't that awesome!? 

Next lets work on customizing our website. This part is super flexible, and it really depends on what you want to show. In this example, Jane Everyday Doe is going to describe a little about her, her interests, projects, internet work-related profiles, her contact information (her email) and a nice little image that shows her GitHub activity. Take the template you see here and edit your index dot R m d file.  Once you are done editing, click on the knit button to update the index. dot h t m l file in your computer. 

Next, update your files on GitHub using the following git commands.

Your website should look similar to this at this point!

R Markdown has several themes that are available to you. These themes include preset fonts and colors for HTML pages that you can use. Let's try the spacelab theme by editing the YAML front matter, the top of your index dot R m d file from as you see here.

Again, knit and then update the files on Git Hub using these commands.

Your website should look similar to this at this point!

A similar process could be used to add a table of contents. Update your YAML using the code you see here. Then, again, knit and update the files on GitHub.

Your website would now reflect these changes!

Now lets add an image to our website. To keep our files organized, lets make a img directory inside our repository using m k deer, the command to make a directory. In that directory, we'll upload a picture file (any format). In this case, we are uploading a file called Jane dot p n g. You can use ls in the img directory to make sure the file uploaded correctly.

Now that we have the image, add the code you see here to your index dot R m d file using Markdown formatting: This code introduces the image and specifies the width of the image in pixels. We want a small image, so we are setting it to 100 pixels/ 

After knitting and uploading to GitHub, we now have a website with an image!

If you need some inspiration, check this website by Amy Peterson: amy dash peterson dot git hub dot i o. It was made using exactly the same tools. 

In this lesson you learned how to create websites from R and publishing them in Git Hub. You also made your own personal website that you can put in your business cards, Twitter profile, share with friends and anywhere you want. Plus it was all free! You might be interested in going beyond this quick website. For example, you might want to add a visitor's map using clustrmaps.com or track visitor using Google Analytics. You could also be interested in buying your own domain, setting up a multi-page website or even make a blog. All those things are possible but beyond the scope of this lesson. If you want to spend the time learning how to do some of those things, check out the links you see here:
