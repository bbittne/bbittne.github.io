Project 2
================
Bryan Bittner
2022-07-08

``` r
rmarkdown::render("_Rmd/2022-07-08-blog-post-Project2.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)
```

## Project 2 Blog Post

This project is centered around a real life news data set. The end goal
of the project is to try to analyze and model the data set, as well as
try to predict the number of shares. This required knowledge of all
aspects that we have been taught so far in this course, as well as a few
new things that we had to learn along the way.

One of the most interesting aspects of this project was the ‘automation’
portion. This required additional code that would allow us to pass in a
particular news channel as a parameter. The report would then
automatically subset the news data to that specific channel and run the
analysis and modeling on that single channel. As the parameter channels
change, the report will change along with it.

If more time was allowed in the project, I would have spent additional
time and effort on some of the summaries and models. I think there are
additional insights that could have been drawn out from the vast data
set that were left untouched. We worked on the data as a subset, I think
it would have also been interesting to do some modelling using the whole
data set to see if that would have changed any predictions.

The most difficult part for me was the automation portion. There is a
lot going on in that small code block so not only is it a lesser known
feature, it is not very intuitive. Having said that, it is definitely a
cool feature and it works great!!

Overall I think this was a good project. Working with a team always has
its advantages and disadvantages. With this project I had some personal
family matters doing on which limited my participation. This meant that
Li did more than her fair sure of work. I greatly appreciated that but
also feel bad about putting her in that position. Parameter driven
reports/projects are widely used across industry so it is good to work
on a real lifelike example of what we will encounter outside of the
classroom.

[Here is a link to the github pages
site:](https://bbittne.github.io/ST558-Project2/)

[Here is a link to the project
repo:](https://github.com/bbittne/ST558-Project2)
