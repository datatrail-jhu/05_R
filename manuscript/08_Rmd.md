# R Markdown

We've spent a lot of time getting R and RStudio working, learning about projects and version control - you are practically an expert at this! There is one last major functionality of R/RStudio that we would be remiss to not include in your introduction to R - [R Markdown!](http://rmarkdown.rstudio.com/)

### What is R Markdown? 

R Markdown is a type of document that allows you to generate fully reproducible reports. In these documents, text , code, and the results of the code can be easily combined. In fact, these lessons are written using what you've already learned about Markdown and all the R code you've recently mastered! 

To refresh your memory, this is how we use plain text in Markdown formatting:

![Markdown review](images/08_Rmd/08_R_Rmd-1.png)

Throughout this lesson we'll remind you of what you learned in the previous lesson on Markdown and discuss all the new things you'll be able to do with R Markdown documents!

R Markdown documents generally take one of two file extensions: .Rmd, .rmd. If a file ends with either of these two file extensions (ie Project_Analysis.Rmd), then you know it's an R Markdown document. While this type of file is a plain text file,  it can be rendered ("Knit") into HTML pages,  PDFs, Word documents, or slides! We'll get into exactly what that means in just a second!

![.Rmd to PDF](images/08_Rmd/08_R_Rmd-2.png)

### Why use R Markdown?

One of the main benefits is the reproducibility of using R Markdown. Since you can easily combine text and code chunks in one document, what this means for a data science project is that you can easily integrate an introduction about what your project question is and where your data came from and the code that you are running, the results of that code, some pretty plots and figures, and your conclusions all in one document. 

Sharing what you did, why you did it and how it turned out becomes so simple - and that person you share it with can re-run your code and *get the exact same answers you got.* That's what we mean about **reproducibility**. 

In addition to being reproducible, there will be times that you're working working on a project that takes many weeks or months to complete. In these cases, you want to be able to see what you did a long time ago (and perhaps be reminded exactly *why* you were doing this). By using an R Markdown document, you'll be able to see exactly what you did previously, what code you used AND the results of that code!

Another major benefit to R Markdown is that since it is plain text, it works very well with version control systems, such as git and GitHub. It is easy to track what character changes occur between commits; unlike other formats that aren't plain text. For example, in one version of this lesson, I may have forgotten to bold **this** word. When I catch my mistake, I can make the plain text changes to signal I would like that word bolded, and in the commit, you can see the exact character changes that occurred to now make the word bold. 

Check out [this video](https://vimeo.com/178485416) that the RStudio developers released about R Markdown and what it is!  

### Getting started with R Markdown

The best way to follow along for the rest of this lesson is to open up [RStudio Cloud](rstudio.cloud), and follow along on your own step-by-step. In the process, you'll get to generate your first R Markdown document! Generating and working with RMarkdown documents is incredibly easy when working within RStudio (or RStudio Cloud). To get started in [RStudio Cloud](rstudio.cloud), go to File > New File > R Markdown.. . 

![R Markdown...](images/08_Rmd/08_R_Rmd-4.png)

If a window pops up specifying that you need to install and update a few packages before using R Markdown, click "Yes" to install those updates. 

At this point, you will be presented with the following window: 

![R Markdown](images/08_Rmd/08_R_Rmd-5.png)

You'll want to add a Title to this document and put your name in the Author box.  

![Title and Author information filled out](images/08_Rmd/08_R_Rmd-7.png)

When you are done entering this information, click OK, and a new .Rmd document will open with a little explanation on R Markdown files. 

![R Markdown document](images/08_Rmd/08_R_Rmd-8.png)

There are three main sections of an R Markdown document. The first is the **YAML** at the top, bounded by the three dashes. This is where you can specify details like the title, your name, the date, and what kind of document you want output. If you filled in the blanks in the window earlier, these will be filled out for you. The spacing of this section matters, so if you edit anything here and then get an error when you try to Knit your document, it may be worth returning to this section to make sure spacing is as it should be.

Also on this page, you can see **text sections**. In this section, text should be written in Markdown. This means that the "## R Markdown" will appear as an H2 header when the document is rendered. and **Knit** will  be bold, as discussed in a previous lesson.

And finally, you will see **code chunks**. These are bounded by the triple backticks. These are pieces of R code, and are referred to as "code chunks". These code in these chunks can run right from within your document - and the output of this code will be included in the document when you Knit it. 

The easiest way to see how each of these sections behave is to produce the HTML! To do so, you'll learn how to knit the document below. 

### "Knitting" documents

When you want to preview an R Markdown document and when you are finished with an R Markdown document, you'll want to **"knit"** the plain text and code from your .Rmd into your final document. 

To do so with the R Markdown that opened with your R Markdown file, click on the "Knit" button along the top of the source panel. 

![Knit](images/08_Rmd/08_R_Rmd-9.png)

When you do so, it will prompt you to save the document. For now, we'll type "test_document" into the box. (However, when you're generating these documents for projects, you'll want to be sure that this document is saved in the appropriate directory, which is likely the `raw_code` directory. Click "Save." 

![Save .Rmd](images/08_Rmd/08_R_Rmd-10.png)

Upon saving the document, you should see a document like this appear in a new window: 

![Knit HTML](images/08_Rmd/08_R_Rmd-11.png)

So here you can see that the content of the header was rendered into a title, followed by your name and the date. The text chunks produced a section header called "R Markdown" which is followed by two paragraphs of text. Following this, you can see the R code `summary(cars)`, importantly, followed by the output of running that code. And further down you will see code that ran to produce a plot, and then that plot. This is one of the huge benefits of R Markdown - rendering the results to code inline.

Go back to the R Markdown file that produced this HTML and see if you can see how you signify you want text bolded. (Hint: Look at the word "Knit" and see what it is surrounded by). Additionally, feel free to change the text in this document or add additional code. Then, click on "Knit" again and see how the changes alter the HTML that is produced.

Upon Knitting to HTML, an additional file will now be saved in the same directory where you saved your .Rmd file. However, as expected, this file will have the extension .html. If you make changes and re-knit your file, this HTML file will be re-generated and all changes will be saved in this file.

![Saved HTML file](images/08_Rmd/08_R_Rmd-12.png)

One final note on knitting. In this example, we have Knit to HTML (a format that can be easily viewed in any web browser), but you can also knit to a PDF or Word document (among other options). To Knit to a different output format, click on the arrow to right of the Knit icon to expose a drop-down menu. Select the output document you'd like from this list. The new file type will be generated and saved in the same directory where the .Rmd file is, but with the appropriate extension (i.e. .pdf if you selected "Knit to PDF"). Feel free to play around with how these different file output options look when you Knit!

![Other file output options when Knitting](images/08_Rmd/08_R_Rmd-13.png)


### Summary

In this lesson we introduced you to R Markdown documents, discussing what they are and why you should use them. We briefly reviewed Markdown formatting, but if you are unclear on what Markdown is, feel free to go back to your previous Markdown lesson. In addition to introducing the what and why, we got you started with actually using R Markdown. Hopefully, you were able to generate and knit your first R Markdown document! Finally, this just touched on the basics of R Markdown. There are a number of options you can specify to display your code chunks in varied ways, different changes that can be made to your YAML to customize your output documents, and ways to create tables and use citations that we did not discuss. As you use R Markdown more and more, you'll get more acquainted with these capabilities. For now, it's great to know the basics and that there are more advanced features!

### Additional Resources

* [R Markdown Documentation](https://rmarkdown.rstudio.com/index.html), from RStudio
* [R Markdown video](https://vimeo.com/178485416), from RStudio
* [Basic R Markdown cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)
* ["R Markdown cheatsheet"](http://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)

### Slides and Video

![R Markdown](https://www.youtube.com/watch?v=_VIiUElGuE0)

*[Slides](https://docs.google.com/presentation/d/1COQq29mnEWgt1NO0qC8tmurswmaDRJpBzmKhKKmJgiw/edit?usp=sharing)  


{quiz, id: quiz_08_Rmd}
  
### R Markdown quiz

{choose-answers: 4}
? When should you use R Markdown documents? 

C) Whenever you're working through a data science project, because R Markdown documents generate fully reproducible reports.
m) Whenever you're just working with code but not text, because R Markdown can easily display code chunks. 
m) Whenever you're working with plain text but not code because R Markdown handles Markdown formatting.
o) Using R Markdown documents should generally be avoided and Markdown should be used instead. 
o) Whenever you're not working with code or plain text.


? How would you strike through some text?  

A) `~~strikethrough~~`   
b) `--strikethrough--`  
c) `\strikethrough\`  
d) None of the above 

{choose-answers: 4}
? How do you produce your final document?  

C) Knit  
o) Crochet   
o) Sew  
o) Macrame  
o) Glue
o) Paste
o) Combine

{choose-answers: 4}
? Click on this link to open the ["R Markdown Cheatsheet"](http://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf), take a look at the "Dynamic Documents" section. Which type of file is NOT a possible output from an R Markdown document?

C) txt
o) html
o) pdf,
o) MS Word
o) ODT
o) RTF
o) markdown document
o) a html or pdf based slide show

{choose-answers: 4}
? Click on this link to open the ["R Markdown Cheatsheet"](http://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf), take a look at the "Embed code with knitr syntax" section. What option would you use to display code in the output document?

C) echo
o) message
o) display
o) highlight
o) error
o) eval
o) warning

{/quiz}

