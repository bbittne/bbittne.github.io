Programming Background
================
Bryan Bittner
2022-06-04

``` r
rmarkdown::render("_Rmd/2022-06-04-blog-post-Module5.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)
```

## Blog Post 3

Everyone in this course had some programming experience coming in (due
to the prerequisites). What are your thoughts on R vs whatever other
software you’ve used? What functionality do you like about R? What parts
do you miss about your other language? Do you consider R a difficult
language to learn? (If you knew R prior to the course, describe your
experience when first learning it.)

Most of my programming experience would revolve around the .net series
of languages as well as the SQL database programming language. I have
also taken the Python programming course here at NC State. Overall I
like R, but if I had to choose between R and Python, I would choose
Python. As a software engineer, Python seems more intuitive and easier
to work with. I also like the fact that there is a single package to do
most things vs R it seems like everyone has their own packages that
solve the same problem.

I haven’t hand any other formal training in R besides this course, so
the explanations have definitely helped a lot. The use of the tidyverse
packages make R easier to work with.

## R Markdown output

``` r
plot(iris)
```

![](../images/unnamed-chunk-2-1.png)<!-- -->
