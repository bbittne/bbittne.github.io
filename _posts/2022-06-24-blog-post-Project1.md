Project 1
================
Bryan Bittner
2022-06-24

``` r
rmarkdown::render("_Rmd/2022-06-24-blog-post-Project1.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)
```

## Project 1 Blog Post

In my current position, one of my job duties is to forecast revenue for
the state of North Dakota. With the list of API’s to choose from, I
naturally gravitated to the Financial Data api.In the beginning, I did
not have a plan for the data. As soon as I started querying the data and
running my EDA, a storyline quickly developed.

In order to forecast revenue, I need to be aware of how things outside
of the state might influence the ND’s revenue income. Typically this
would center around oil and agricultural prices, but I also need to be
aware of changes at the federal level. On June 14th the Federal Reserve
raised interest rates by 0.75 percentage points. This will in turn raise
rates on everyone as well as any company that needs a loan. Naturally
this rate change will require all individuals and businesses to spend
more money. When a business has to spend more money, their stock price
typically will go down as well. Going into this project, I was aware
that the stocks took a bit of a hit when the rate change was made. I was
not aware of the anticipation and trendline that accompanies the said
decision.

Overall I think this was a very neat project and I’m glad I had the
chance to work on it. One of the most difficult things I had was the
fact that the free version of this API had a count limit. This limit
wasn’t an issue when I was manually running the code chunks, but it
caused me some time when I went to render the code. In the end I found
the problem and just payed to get those counts increased. A small price
to pay to have an efficient and well laid out project!

If I had to do a similar project again, I probably would have spent a
bit more time in the analysis phase instead of jumping into the code. In
the end it would have saved some time if I laid out a plan before
writing code. Overall though I think things went pretty smooth.

[Here is a link to my github pages repo:](https://bbittne.github.io/)

[Here is a link to my regular
repo:](https://github.com/bbittne/Project1)
