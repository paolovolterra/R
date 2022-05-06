# R
in questo repository metto le prove e gli appunti presi su R
Se meritevoli, approfondisco gli argomenti in appositi files

![Immagine](https://technosoups.com/wp-content/uploads/2021/03/R-programming-language.jpg)


library(tidyquant)
library(DT)
library(FinCal) 


https://www.codingfinance.com/post/2018-03-23-car-payment/

https://www.business-science.io/finance/2020/02/26/r-for-excel-users.html#


----------------------------------------------------------------------------------------------------------------------------

# EXCEL

## [tidyxl](https://nacnudus.github.io/tidyxl/)
tidyxl imports non-tabular data from Excel files into R. It exposes cell content, position, formatting and comments in a tidy structure for further manipulation, especially by the unpivotr package. It supports the xml-based file formats ‘.xlsx’ and ‘.xlsm’ via the embedded RapidXML C++ library. It does not support the binary file formats ‘.xlsb’ or ‘.xls’.

It also provides a function xlex() for tokenizing formulas. See the vignette for details. It is useful for detecting ‘spreadsheet smells’ (poor practice such as embedding constants in formulas, or using deep levels of nesting), and for understanding the dependency structures within spreadsheets

### [xlsx complessi](https://github.com/nacnudus/ukfarm)

### [Spreadsheet Munging Strategies](https://nacnudus.github.io/spreadsheet-munging-strategies/)

----------------------------------------------------------------------------------------------------------------------------

# Fuzzy

## [fuzzyjoin: Join data frames on inexact matching](https://github.com/dgrtwo/fuzzyjoin)  
The fuzzyjoin package is a variation on dplyr's join operations that allows matching not just on values that match between columns, but on inexact matching. This allows matching on:

# environment

* [esempio 1](https://www.business-science.io/finance/2020/02/21/tidy-discounted-cash-flow.html)


----------------------------------------------------------------------------------------------------------------------------

# Scraping

## [rvest](https://rvest.tidyverse.org/)
![](https://rvest.tidyverse.org/logo.png)
rvest helps you scrape (or harvest) data from web pages. It is designed to work with magrittr to make it easy to express common web scraping tasks, inspired by libraries like beautiful soup and RoboBrowser.

If you’re scraping multiple pages, I highly recommend using rvest in concert with polite. The polite package ensures that you’re respecting the robots.txt and not hammering the site with too many requests.
