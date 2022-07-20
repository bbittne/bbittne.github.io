Blog Post 4
================
Bryan Bittner
2022-07-16

``` r
rmarkdown::render("_Rmd/2022-07-16-blog-post-MachineLearning.Rmd", 
                  output_format = "github_document",
                  output_dir = "./_posts",
                  output_options = list(
                    html_preview= FALSE
                    )
)
```

## Blog Post - Machine Learning

We have learned a lot of different modeling types and machine learning
methods. All of which are very interesting and have their specific uses.
I would have to say that I think the coolest model that we learned about
would have to be the kNN nearest neighbor.

kNN is a supervised machine learning method meaning it relies on
manually inputted data in order to learn and produce accurate output.
kNN can be used on both classification problems as well as regression
problems.

The basics for kNN is that you use the “closest” k number of
observations to determine the prediction with the highest probability.
The kNN algorithm assumes that similar things are near each other. The
kNN algorithm will calculate the distance between points and determine
the likely outcome.

For an example, we can look at the traditional ‘iris’ dataset.

``` r
data(iris)
head(iris)
```

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

Before we do any modeling, lets split up the dataset into a training set
and a test set.

``` r
train <- sample(1:nrow(iris),size=nrow(iris)*.8)
test <- dplyr::setdiff(1:nrow(iris),train)

irisDataTrain <- iris[train,]
irisDataTest <- iris[test,]
head(irisDataTrain)
```

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 67           5.6         3.0          4.5         1.5 versicolor
    ## 16           5.7         4.4          1.5         0.4     setosa
    ## 92           6.1         3.0          4.6         1.4 versicolor
    ## 147          6.3         2.5          5.0         1.9  virginica
    ## 108          7.3         2.9          6.3         1.8  virginica
    ## 54           5.5         2.3          4.0         1.3 versicolor

In order to fit a kNN model, we need to load the class library. For the
model fit, we will pass in the training data and use the test data to
determine how accurate the model predictions are. Here we will use the
sepal.length and sepal.width as our predictors and the Species as the
response variable.

``` r
knnFit <- knn(train = select(irisDataTrain, Sepal.Length, Sepal.Width),
              test = select(irisDataTest, Sepal.Length, Sepal.Width),
              cl = irisDataTrain$Species,
              k = 3)
fitInfo <- as_tibble(data.frame(knnFit, select(irisDataTest, Species, Sepal.Length, Sepal.Width)))
fitInfo
```

    ## # A tibble: 30 × 4
    ##    knnFit     Species    Sepal.Length Sepal.Width
    ##    <fct>      <fct>             <dbl>       <dbl>
    ##  1 setosa     setosa              4.9         3.1
    ##  2 setosa     setosa              5.1         3.5
    ##  3 setosa     setosa              4.7         3.2
    ##  4 setosa     setosa              5.5         3.5
    ##  5 versicolor setosa              4.5         2.3
    ##  6 setosa     setosa              4.4         3.2
    ##  7 setosa     setosa              5.3         3.7
    ##  8 virginica  versicolor          7           3.2
    ##  9 virginica  versicolor          6.4         3.2
    ## 10 versicolor versicolor          5           2  
    ## # … with 20 more rows

Now that the model has been fit, we can use this table below to see how
accurate the predictions were. There are three different types of
species. The numbers on the diagonal column from left to right are the
predictions that were correct. All of the other values in the table are
predictions that were incorrect. As you can see, overall it looks like
the kNN model did a great job at predicting.

``` r
tbl1 <- table(fitInfo$knnFit,fitInfo$Species)
tbl1
```

    ##             
    ##              setosa versicolor virginica
    ##   setosa          6          0         0
    ##   versicolor      1          4         3
    ##   virginica       0          7         9

Here we can get an actual value to see how accurate the model is. The
value below is a ‘mis-classification rate’. Meaning this is how often
the kNN model predicted the incorrect Species type.

``` r
misClass <- 1 - sum(diag(tbl1))/sum(tbl1)
misClass
```

    ## [1] 0.3666667

Overall the kNN model did a pretty good job at predicting. One way to
improve the mis-class rate would be to utilize cross validation.
