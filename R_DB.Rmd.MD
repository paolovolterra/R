---
R e DB
---

# [Access a database](https://rstudio.github.io/bigdataclass/access-a-database.html#connect-to-a-database)

![](https://rstudio.github.io/bigdataclass/images/connections-tab.PNG)

	
	con <- dbConnect(odbc::odbc(), "aida", timeout = 10)
	dbListTables(con)
	df <- odbc::dbGetQuery(con, "SELECT * FROM aida.cdg_mix")
	library('tidyverse')
	library(ggplot2)
	library(dbplot)
	df %>%
	  dbplot_histogram(lordo) #, binwidth = 100

	df %>%
	  dbplot_raster(proposto,lordo)

	library(readr)
	library(DataExplorer)
	DataExplorer::create_report(df)

	head(df, 10)
	dim(df)
	View(df)
	summary(df)