# Creating Websites with R

![](images/06_website/05_R_website_Page_01.png)

In previous lectures you have learnt how to:

* Create a GitHub repository
* Use R Markdown for combining R code and text

Now we are going to use these two skills to create a website from within R. At the end of this lecture you will have your own personal website made with R!


### Create your website repository

GitHub has this nice property that it can automatically host websites for you in the repositories. While this can de done for any repository, there is a special case: the `yourUsername.github.com` repository. We will start here because it's the most straightforward case.

![](images/06_website/05_R_website_Page_02.png)

If your username is `JaneEverydayDoe`, first log in to [github.com](http://github.com). Next create a new repository (that nice green button). This new repository needs this special name `JaneEverydayDoe.github.com` which you can find [here](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com).

Yay, we now have our repository!

### Sync files with GitHub

![](images/06_website/05_R_website_Page_03.png)

Now we are going to start putting your website together. We need to keep our files in sync with GitHub, and to do so we will clone (download) the repository to our computer. That is, we will clone the `username/username.github.com` repository. For `JaneEverydayDoe` that would be `JaneEverydayDoe/JaneEverydayDoe.github.com`. We will do this via the _terminal_ from RStudio. That is, from `Tools` -> `Terminal` -> `New Terminal`. Once you have opened a _terminal_ (optionally navigate to the directory where you want to clone the repo), run:

```
git clone https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com.git
```

We now have completed the necessary GitHub setup!

### One last setup step

It's time to start working on our website! In the terminal access the `username.github.com` repository using the `cd` (change directory) command. For `JaneEverydayDoe` that would be:

```
cd janeeverydaydoe.github.com/
```

The directory is empty and we can almost start our website. There is one more piece we need to do that is rather obscure. Something we haven't talked about is that GitHub was initially setup for hosting _Jekyll_ static websites and that is still the default at this time. But we are not using Jekyll and we need to tell that to GitHub. To do so we need to create the hidden file `.nojekyll` and version control it. You can create the file using the `touch` command in the terminal or from RStudio (`New File` -> `Save as` -> choose `.nojekyll` and save it inside `janeeverydaydoe.github.com`).

```
touch .nojekyll
```

If we check the files including the hidden files using the `ls -a` (`ls` stands for _list_ and the `-a` options displays hidden files) command in the terminal we should see it.

```
$ ls -a
.  ..  .git  .nojekyll
```

Cool, we now have the required `.nojekyll` file but it's not on GitHub yet. So we need to version control it. You can do so with the RStudio git interface or using the following commands in the terminal window:

```
git add .nojekyll
git commit -m "This is not a Jekyll website"
git push
```

![](images/06_website/05_R_website_Page_04.png)

Using the `JaneEverydayDoe` example you can [see here](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/a5f889e3c9749720ee0435e95f77d0b4eaeea8d9) how the repository looked at this point in time.

![](images/06_website/05_R_website_Page_05.png)

### Make the website

Ok, now we can make the website!

We are going to take advantage of another nice property of web. If a directory (say `hello`) contains a `index.html` file, then that file is displayed on the web browser when someone accesses `hello/`. In other words, `index.html` is the default HTML file that is displayed. Meaning that we need to create an `index.html` file. How can we do that from R?

Well, lets create a `index.Rmd` file inside the `username.github.com/` directory. Here, lets take advantage of the nice RStudio menus. Go to `File` -> `New File` -> `R Markdown`.

![](images/06_website/05_R_website_Page_06.png)

Then select `Document` and choose the `HTML` output format.

![](images/06_website/05_R_website_Page_07.png)

Now lets save it as `index.Rmd`. Select the `Untitled1` tab, then go to `File` -> `Save As` then type the `index.Rmd` name and make sure that it's saved inside the `username.github.com` directory. In `JaneEverydayDoe`'s case, that would be `janeeverydaydoe.github.com/index.Rmd`.

![](images/06_website/05_R_website_Page_08.png)

Now click on the `knit` button and R will create the `index.html` file.

### Publish the website

Just so we can see the website in action, lets publish it. What does that mean? Well, we have the `index.html` file in our computer but it's not on GitHub's computers. So we need to version control the `index.html` file (lets also version control the `index.Rmd` source file) and upload (`git push`) to GitHub.

In the terminal window or with RStudio's git tools, run the following commands.

```
## Tell git to version control the index.* files
git add index.html
git add index.Rmd

## Make a save point in Git
git commit -m "First version of the website"

## Upload the files to GitHub
git push
```

And after a few seconds or a minute or so, you can view your website at https://username.github.io. For `JaneEverydayDoe` that is https://janeeverydaydoe.github.io/ and it looks like this:

![](images/06_website/05_R_website_Page_09.png)

You can check `JaneEverydayDoe` [files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/6ef6468c9fb0dc93ed436b056ddd602e13658377) and compare them against yours.

### Customize the website

Ok, so now we have a website that is publicly available and that we made with R. Isn't that awesome!? Next lets work on customizing our website. This part is super flexible and it really depends on what you want to show. In this example, `JaneEverydayDoe` is going to describe a little about her, her interests, projects, internet work-related profiles, her contact information (her email) and a nice little image that shows her GitHub activity. Take the template below and edit your `index.Rmd` file. 

```
## About

Describe who you are. For example, what you are currently studying.

Summarize your trajectory. You could mention what you've done. Like what you've studied or where you've worked.

## Interests

* Interest 1
* Interest 2
* etc

## Projects

* List some of your recent projects
* You could include this website as a project!

## Profiles 

* [LinkedIn](https://www.linkedin.com/in/yourprofile/)
* ...
* [GitHub](http://github.com/username)

## Contact

* [youremail@email](mailto:youremail@email)
```

Once you are done editing, click on the `knit` button to update the `index.html` file in your computer. Next, update your files on GitHub using the following commands.

```
git add index.*
git commit -m "Add my initial information"
git push
```

![](images/06_website/05_R_website_Page_10.png)

Check `JaneEverydayDoe`'s files at [this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/c0b15cf33e3fe88322d46e9f35def6c485eb0fee).


### Change the theme

R Markdown has several _themes_ which are presets of fonts and colors for HTML pages. You can find them all listed at [rmarkdown.rstudio.com/html_document_format.html#appearance_and_style](https://rmarkdown.rstudio.com/html_document_format.html#appearance_and_style). Let's try the `spacelab` theme by editing the YAML front matter (the top section) of the `index.Rmd` file from:

```
---
title: "JaneEverydayDoe’s website"
output: html_document
---
```

to

```
---
title: "JaneEverydayDoe’s website"
output:
  html_document:
    theme: spacelab
---
```

Again, `knit` then update the files on GitHub.

```
git add index.*
git commit -m "Use spacelab"
git push
```

![](images/06_website/05_R_website_Page_11.png)

[JaneEverydayDoe's files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/33db3fac9619ef32bdb032b56e0ca5836b5e28c5).

### Adding a table of contents

```
---
title: "JaneEverydayDoe’s website"
output:
  html_document:
    theme: spacelab
    toc: true
    toc_depth: 3
    toc_float: true
---
```

Again, `knit` then update the files on GitHub.

```
git add index.*
git commit -m "Add a floating table of contents"
git push
```

![](images/06_website/05_R_website_Page_12.png)

[JaneEverydayDoe's files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/3caa9cc00e9ea167360b1299763ad3b01b6e9de6).


### Adding an image

Now lets add an image to our website. To keep our files organized, lets make a `img` directory inside our repository using `mkdir` (make directory).

```
mkdir img
```

In that directory, we'll upload a picture file (any format). In this case, we are uploading a file called `Jane.png`. If you don't have an image, take a screenshot of your GitHub profile and rename it accordingly. You can verify your upload worked using `ls`.

```
$ ls img
Jane.png
```

Now that we have the image, lets add the following code to our `index.Rmd` file:

```
![](img/Jane.png){width=100px}
```

This code introduces the image and specifies the width of the image in pixels. We want a small image, so we are setting it to 100 pixels (`100px`).

After knitting and uploading to GitHub, we now have a website with an image!

```
git add img/Jane.png
git add index.*
git commit -m "Add Jane's image"
git push
```

![](images/06_website/05_R_website_Page_13.png)

[JaneEverydayDoe's files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/505eaf2049930084526e79a005fc9e8a75f6b143).

### A similar website

If you need some inspiration, check this website by Amy Peterson: [amy-peterson.github.io](https://amy-peterson.github.io/). It was made using exactly the same tools. 

![](images/06_website/05_R_website_Page_14.png)

The raw files for her website are available [here](https://raw.githubusercontent.com/amy-peterson/amy-peterson.github.com/bf9637d0351e1494cbd0c34528b261e340539b06/index.Rmd).

### Beyond this lesson

In this lesson you learnt how to create websites from R and publishing them in GitHub. You also made your own personal website that you can put in your business cards, Twitter profile, share with friends and anywhere you want. Plus it was all free!

You might be interested in going beyond this quick website. For example, you might want to add a visitor's map using clustrmaps.com or track visitor using Google Analytics. You could also be interested in buying your own domain, setting up a multi-page website or even make a blog. All those things are possible but beyond the scope of this lesson. If you want to spend the time learning how to do some of those things, check:

* Recent changes to `JaneEverydayDoe` website at https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/commits/master
* https://pages.github.com/
* Emily Zabor's great tutorial http://www.emilyzabor.com/tutorials/rmarkdown_websites_tutorial.html
* https://bookdown.org/yihui/blogdown/ for making blogs

![](images/06_website/05_R_website_Page_15.png)


{quiz, id: quiz_06_website}

### Creating websites with R

? Which of the following statements is True?

a) We created a Jekyll website
b) We manually wrote our index.html file using HTML code
C) We created the index.html file from knitting an R Markdown file
d) We payed for a custom domain like JaneEverydayDoe.com

{/quiz}








