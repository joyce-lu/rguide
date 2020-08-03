# A Lazy Person's Guide to R

This is a guide to R, written by a lazy statistics student for lazy statistics students! My goal is to make this as helpful as possible for you, regardless of whether you are someone who (1) has never scripted or coded in your entire life or (2) knows R basics but just needs a refresher. If you're (3) a programmer coming from another language, read [this](http://arrgh.tim-smith.us/) instead. It will probably be very cathartic for you.

Before you continue, [install RStudio](https://rstudio.com/products/rstudio/download/) if you have not already.

A helpful tip to save time: the stuff hidden behind light bulb icons is good but not necessary to know for an R beginner (...or if your pset is due in two hours).

Another helpful tip to save time: sections with a red dot in the header are for beginner-beginners, as in this is your first time opening RStudio.

Coming soon:
1. R syntax cheatsheet
2. Helpful functions for data analysis that you can steal
3. Short practice exercises

## The Basics

>*If you've never touched code before and have no idea where to begin, start here!*

### RED DOT Using RStudio

Open RStudio and create a new R script (aka document) by clicking on the icon on the top-left. Now you should see 4 panes:

**Top left -** source pane. It's where opened scripts are displayed and edited, by you!

**Bottom left -** console. It's where code output is printed.

**Top right -** environment. It displays a list of all the data, variables, and functions that you've created in this session.

**Bottom right -** viewer. If you make a plot or look up a function's documentation, this is where it'll show up.

**^maybe I should just present that in a screenshot**

To run a command in the R console, just type it and press enter. To run a line of code in a script, just put your cursor anywhere on the line and press ctrl-enter. In a script, commands can be separated by new lines or semicolons.

In R, most of what you'll write in a script will 
look like this:

    variable_name <- do_something(arg1, arg2)
    do_something_else(variable_name)

The back arrow `<-` is the assignment operator; the example above stores the return value of the function `do_something` in an object called `variable_name`. You can also use `=`, which does the same thing.

### RED DOT Attaching Packages

A package is a bundle of functions that somebody else has written for you to use. In base R, you only have access to a limited number of commonly used functions; chances are you'll need more.

Before attaching a package, you need to install it. (This happens only once; a package will remain installed unless you actively uninstall it.) Say you want to install the package `ggplot2`; just run the command `install.packages("ggplot2")`. (Note the quotes--you need them!)

Now you can attach it via the command `library(ggplot2)`. (Quotes are optional this time.) You have to reattach a package after you clear your workspace, if you want to use it again. Sometimes, you'll see people attach packages with `require(ggplot2)`. [They would be wrong. :)](https://yihui.org/en/2014/07/library-vs-require/)

Now that you've attached the package, you can use any of its functions. To see the documentation (aka instructions) for a function--for instance, `read_excel`--simply run the command `?read_excel`.

LIGHT BULB: To use a function from an installed package without having to attach it, do `package::function(arg1, arg2)`. 

### Atomic Vectors, Data Frames, and Lists

(Pretty much) everything in R is a vector. The most basic data structure in R is an atomic vector, which is a fancy way to say a list of things that are all of the same "type"--for example, all integers or all characters. (Note: there's also an actual data structure called a list; to distinguish between the two, I'll refer to the generic list in a serif font.)

Despite the fancy name, there is nothing fancy about atomic vectors. You make one like this:

    my_vector <- c("1", "2", "3")
    your_vector <- as.character(1:3)
    our_vector <- c(my_vector, your_vector)

The output of each vector looks like this:

    > my_vector
    [1] "1" "2" "3"
    > your_vector
    [1] "1" "2" "3"
    our_vector
    [1] "1" "2" "3" "1" "2" "3"

As you might have surmised from `my_vector` and `our_vector`, putting objects inside `c()` **c**oncatenates the values into a vector. `your_vector` uses a special shortcut that is available when making vectors of whole numbers: `1:3` creates the vector `[1] 1 2 3`, and then `as.character()` converts it from type numeric to type character.

Which brings me to a discussion of type. There are 3 main vector types in R: logical (`TRUE` or `FALSE`), numeric (integers or doubles), and character (strings of symbols enclosed in quotes). There's some fuzziness between the types (for example, if you add a bunch of logicals together it's as if you're adding 1 for each `TRUE` and 0 for each `FALSE`), but it's not super important for now. You can check the type of an atomic vector with `typeof(my_vector)` or `class(my_vector)`. The vector's type will influence what you can and can't do with it. For example, you can't add or subtract non-numeric vectors.

    > my_vector - your_vector
    Error in my_vector - your_vector: non-numeric argument to binary operator



# data manipulation
# modeling functions
# code snippets; parameters; WRITE FUNCTIONS
# shiny

# ggplot2
