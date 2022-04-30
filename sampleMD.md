---

Author: "Sr. Yididiel"

Date: "Saturday, 23 April 2022"

---

# Mastering Markdown - Detailed Crash Course

[Mastering Markdown - Detailed Crash Course](https://youtu.be/CqUJ7nLSLzs)

# Heading one

## Heading two

### Heading three

#### Heading four

##### Heading five

###### Heading six

## Styling Text

_**This text is italic**_

_**This is also italic**_

_**This text is bold**_

_**This is also bold**_

_My country_Israel_ is great!_

## Strike Through Text

~~strikethrough~~

## Lists

* Item 1
* Item 2
* Item 3
  * Sub Item 4
  * Sub Item 5

## Ordered Lists

1. Num 1
2. Num 2
3. Num 3

## Inserting Images

![White Deer](img/whitedeer.jpg)

## Linking a webpage or pages

**This is a link:** [This is my awesome Ansible repository!]("https://github.com/yididiel7/ansible_tutorial.git")

## Block quotes

_As_Sr. Yididiel_said:_

> "The more you learn the **better** you get!"
> Welcome back to **TELL US™** on Github.

## Code Highlights

This is javascript code

```javascript
function greetUser(){
    console.log('Shalom user');
}
```

This is python code

```python
def Move():
  print('Started moving.')
```

This is PHP code

```php
$query = "SELECT * FROM users";
```

## Task Lists

* [ ] This task is incomplete
* [x] This task is complete

## Creating Tables

Name     | Age
---------|-----
Yididiel | 55
Tyrone   | 57
Yeshiyah | 78
Asiel    | 72

## Mentions

@yididiel7 is also a **contributor & developer**

```{r get_data, message = FALSE, warning = FALSE}

Message and warning options

It is great that we have live code in our document, but results seems to be populated with additional text. Those are “messages” from the package loading and some could be additional warning about casting values to different type. It depends, but generally suppressing message really helps with document appearance. I also tend to suppress warnings, but this can cause issue in downstream analysis, be sure you understand your warnings before suppressing them.

Let’s add a couple of options to our code chunk and press Knit

```

## Getting and wrangling the data

```{r get_data}
make_url <- function(package) {
  paste0('<a href="https://cran.r-project.org/web/packages/', package, '">', package, '</a>')
}

library(magrittr)
library(dplyr)

avail_packages <- available.packages(contriburl = contrib.url("https://mirror.aarnet.edu.au/pub/CRAN/")) %>% 
                    as.data.frame() %>% 
                    as_tibble() %>% 
                    rowwise() %>% 
                    mutate(Depend = length(unlist(strsplit(Imports, split = ",")))) %>% 
                    ungroup() %>% 
                    select(Package, Version, Depend, Imports, License) %>% 
                    mutate(Package = make_url(Package),
                           Depend = ifelse(is.na(Imports), -1, Depend))

```

## Displaying table

```{r make_table, message=FALSE, warning=FALSE}
library(DT)
avail_packages %>% datatable(escape = FALSE)
```

## Plot the data

```{r plot}
library(ggplot2)
avail_packages %>% ggplot(aes(Depend)) + geom_bar()
```

**sessionInfo**
