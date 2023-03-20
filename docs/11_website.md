---
output: html_document
date: '2022-04-11'
---



# Creating Websites with R

In previous lectures you have learned how to:

* Create a GitHub repository
* Use R Markdown for combining R code and text

Now we are going to use these two skills to create a website from within R. At the end of this lecture you will have your own personal website made with R!


### Create your website repository

GitHub has the nice property that it can automatically host websites for you from a repository. While this can de done for any repository, there is a special case: the `yourUsername.github.com` repository that makes setting up your own website a little bit simpler. We will start here because it's the most straightforward case.

{format: png}
![Create Repository](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_1)

We'll work through an example for someone whose GitHub username is `JaneEverydayDoe`, but you should follow along and complete each step using your own GitHub account. To get started, first log in to [github.com](http://github.com) and create a new repository (that nice green button). While normally for projects you'll be able to name your repository whatever you want, *this* new repository for your website **must have a specific name**. The repository *must* be named either `username.github.io` *or* `username.github.com`, where *your* GitHub username would replace `username`. So, in our case, the repo would be named: `JaneEverydayDoe.github.io`.

**Remember, this repository must be named: `username.github.io` or `usernmae.github.com`, with *your* GitHub username in the place of `username`.**

Yay, we now have our repository to get started!

### Sync files with GitHub


Now we are going to start putting your website together. We need to keep our files in sync with GitHub, and to do so we will clone the repository RStudio Cloud. That is, we will clone the `username/username.github.com` repository. For `JaneEverydayDoe` that would be `JaneEverydayDoe/JaneEverydayDoe.github.com`. We will do this via the _terminal_ from RStudio Cloud. Once you are in the terminal run the following (but change the username 'JaneEverydayDoe' to your GitHub username:

```
git clone https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com.git
```

{format: png}
![git clone](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g3c1a412a3a_0_0)

We now have completed the necessary GitHub setup!

### One last setup step

It's time to start working on our website! In the terminal access the `username.github.com` repository using the `cd` (change directory) command. For `JaneEverydayDoe` that would be:

```
cd janeeverydaydoe.github.com/
```

{format: png}
![cd into directory](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g3c1a412a3a_0_6)


The directory is empty currently. At this point, we can almost start our website. There is one more thing we need to do that is rather obscure. Something we haven't talked about is that GitHub was initially set up for hosting _Jekyll_ static websites and this is still the default. But, we are not using Jekyll and we need to tell GitHub that. To do so we need to create the hidden file `.nojekyll` and version control it. You can create the file using the `touch` command in the terminal or from RStudio Cloud using the following command:

```
touch .nojekyll
```
We haven't discussed the command `touch` or hidden files yet, so now is a great time to explain briefly that touch simply creates an empty file and hidden files are files that start with a period in the file name.

However, despite being hidden, we *can* check to make sure this file was created by using the command `ls -a` (`ls`, as discussed previously, stands for _list_ and the `-a` option states that we also want to display hidden files). When we run this command, we see the ".nojekyll" file has been created.

```
ls -a
```

{format: png}
![touch and ls](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g3c1a412a3a_0_12)

Cool, we now have the required `.nojekyll` file! But, it's not on GitHub yet. So, we need to version control it. You can do so in the RStudio Cloud terminal window using the following commands:

```
git add .nojekyll
git commit -m "This is not a Jekyll website"
git push
```

*Note*: If prompted to set your global configuration on GitHub, provide your email address or GitHub username and password, do so.

{format: png}
![touch and ls](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g3c1a412a3a_0_20)

Using the `JaneEverydayDoe` example, you can [see here](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/a5f889e3c9749720ee0435e95f77d0b4eaeea8d9) how the repository should look at this point in the process.

{format: png}
![Repo at this point in the process](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_9)

### Make the website

Ok, now we can make the website!

First, web pages display HTML code. With that knowledge, we are going to take advantage of another nice property of the web. If a directory (say that directory is named `hello`) contains an `index.html` file, then that file is displayed on the web browser when someone accesses the website's home page`. In other words, `index.html` is the default HTML file that is displayed. This means that we need to create an `index.html` file. How can we do that from R?

Well, let's create a `index.Rmd` file inside the `username.github.com/` directory. Here, lets take advantage of the nice RStudio menus. Go to `File` -> `New File` -> `R Markdown`. (*Note*: If prompted to install packages, click yes to install them)

{format: png}
![New Rmd document](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_13)

Then ensure `Document` is selected along the left and `HTML` is selected for the output format. Click OK.

{format: png}
![New R Markdown](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_17)

Now let's save it as `index.Rmd`. go to `File` -> `Save As` then type `index.Rmd` in the file name box, **making sure that it's saved inside the `username.github.com` directory**. In `JaneEverydayDoe`'s case, the relative file path would be `janeeverydaydoe.github.com/index.Rmd`.

{format: png}
![How to Knit](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_21)

Now click on the `knit` button and R to create the `index.html` file!

### Publish the website

Just so we can see the website in action, let's publish it. What does that mean? Well, we have the `index.html` file in our computer but it's not on GitHub's computers. So, we need to version control the `index.html` file (let's also version control the `index.Rmd` source file) and upload (`git push`) to GitHub.

In the terminal window of RStudio Cloud, run the following commands:

```
## Tell git to version control the index.* files
git add index.*

## Provide a good commit message
git commit -m "First version of the website"

## Upload the files to GitHub
git push
```

And after a few seconds or a minute or so, you can view your website at https://username.github.io. For `JaneEverydayDoe` that is https://janeeverydaydoe.github.io/ and it looks like this:

{format: png}
![First website!](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_25)

You can check `JaneEverydayDoe` [files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/6ef6468c9fb0dc93ed436b056ddd602e13658377) and compare it against yours.

### Customize the website

Ok, so now we have a website that is publicly available and that we made with R. Isn't that awesome!? Next lets work on customizing our website. This part is super flexible and it really depends on what you want to show. In this example, `JaneEverydayDoe` is going to describe a little about her, her interests, projects, internet work-related profiles, her contact information (her email) and a nice little image that shows her GitHub activity. Take the template below and edit your `index.Rmd` file. Note that everything here is written using Markdown formatting.

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

{format: png}
![Updated website](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_37)

Check `JaneEverydayDoe`'s files at [this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/c0b15cf33e3fe88322d46e9f35def6c485eb0fee).


### Change the theme

R Markdown has several _themes_ that are available to you. These themes include preset fonts and colors for HTML pages that you can use. You can find them all listed at [rmarkdown.rstudio.com/html_document_format.html#appearance_and_style](https://rmarkdown.rstudio.com/html_document_format.html#appearance_and_style). Let's try the `spacelab` theme by editing the YAML front matter (the top section) of the `index.Rmd` file from:


```
---
title: "JaneEverydayDoe's website"
output: html_document
---
```

to

```
---
title: "JaneEverydayDoe's website"
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

![Website with spacelab theme](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_41)

[JaneEverydayDoe's files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/33db3fac9619ef32bdb032b56e0ca5836b5e28c5).

### Adding a table of contents

A similar process could be used to add a table of contents. Update your YAML using the code you see here.
```
---
title: "JaneEverydayDoe's website"
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
Your website should now reflect these changes!

{format: png}
![Website at this point in the process](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_45)

[JaneEverydayDoe's files at this point in time](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/3caa9cc00e9ea167360b1299763ad3b01b6e9de6).


### Adding an image

Now let's add an image to our website. To keep our files organized, lets make a `img` directory inside our repository using `mkdir` (make directory).

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

{format: png}
![Website with image added](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g38bb68a320_0_49)

{format: png}
[JaneEverydayDoe's files at this point in the process](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/tree/505eaf2049930084526e79a005fc9e8a75f6b143).

### A similar website

If you need some inspiration, check out Amy Peterson's website: [amy-peterson.github.io](https://amy-peterson.github.io/). It was made using exactly the same tools.

![Amy's website](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/export/png?id=18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU&pageid=g3c1a412a3a_0_49)

The raw files for her website are available [here](https://raw.githubusercontent.com/amy-peterson/amy-peterson.github.com/bf9637d0351e1494cbd0c34528b261e340539b06/index.Rmd).

### Beyond this lesson

In this lesson you learned how to create websites from R and publishing them in GitHub. You also made your own personal website that you can put in your business cards, Twitter profile, share with friends and anywhere you want. Plus it was all free!

You might be interested in going beyond this quick website. For example, you might want to add a visitor's map using clustrmaps.com or track visitor using Google Analytics. You could also be interested in buying your own domain, setting up a multi-page website or even make a blog. All those things are possible but beyond the scope of this lesson. If you want to spend the time learning how to do some of those things, check:

* Recent changes to `JaneEverydayDoe` website at [https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/commits/master](https://github.com/JaneEverydayDoe/janeeverydaydoe.github.com/commits/master)
* [https://pages.github.com/](https://pages.github.com/)
* Emily Zabor's great tutorial [http://www.emilyzabor.com/tutorials/rmarkdown_websites_tutorial.html](http://www.emilyzabor.com/tutorials/rmarkdown_websites_tutorial.html)
* [https://bookdown.org/yihui/blogdown/](https://bookdown.org/yihui/blogdown/) for making blogs


### Slides and Video

[Automated Videos](https://youtu.be/phEJ5oI37bs)

* [Slides](https://docs.google.com/presentation/d/18cfusRGwEtQCD4MKew4S3s7HdK8AuSr_RRPQS6S3KKU/edit?usp=sharing)
