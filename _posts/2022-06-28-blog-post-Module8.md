Blog Post 3 - Favorite R Features
================
Bryan Bittner
2022-06-28

``` r
rmarkdown::render("_Rmd/2022-06-28-blog-post-Module8.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(html_preview= FALSE))
```

## Blog Post 3

This blog post is all about the coolest feature we have learned in the R
Programming world.

In my humble opinion, I still prefer Python over R as a general
programming language. Having said that, there are still some features in
R that I like better than Python. In general, I like the plots/graphs in
R more than Python. They seem a bit easier to use and seem to have an
endless variety of options. Google seems like it has more pages to help
the user along the way here. We have just scrapped the surface when it
comes to modeling, but I think R might hold the advantage here as well.

Getting more specific, I think the coolest and probably underutilized
feature in R would be the mutate() function in conjunction with the
if_else() vectorized comparison. In my opinion this is HUGE!! It is
crazy fast and efficient and can be useful for seemingly endless tasks.
Traditionally programming languages would require a loop and multiple
statements. R can handle this in a single line of code.

Below is a quick example of mutate() with if_else()/

First lets generate some random numbers between 0 and 1

``` r
testData<-runif(100,min=0,max=1)
testData<-as.tibble(testData)
names(testData)<-"Values"
testData
```

    ## # A tibble: 100 × 1
    ##    Values
    ##     <dbl>
    ##  1  0.665
    ##  2  0.841
    ##  3  0.437
    ##  4  0.840
    ##  5  0.280
    ##  6  0.222
    ##  7  0.761
    ##  8  0.705
    ##  9  0.904
    ## 10  0.849
    ## # … with 90 more rows

Now if we wanted to add a new binary variable that is 1 if the values is
greater than or equal to 0.50 and 0 if less than 0.50, we can easily do
this in one statement.

``` r
testData <- testData %>% mutate(ValuesGTEOneHalf = if_else(Values >= 0.5,1,0))
testData
```

    ## # A tibble: 100 × 2
    ##    Values ValuesGTEOneHalf
    ##     <dbl>            <dbl>
    ##  1  0.665                1
    ##  2  0.841                1
    ##  3  0.437                0
    ##  4  0.840                1
    ##  5  0.280                0
    ##  6  0.222                0
    ##  7  0.761                1
    ##  8  0.705                1
    ##  9  0.904                1
    ## 10  0.849                1
    ## # … with 90 more rows

This is an over simplistic example, but if you had a dataset with
thousands or even millions of records, this one statement can be a time
and life saver for sure!
