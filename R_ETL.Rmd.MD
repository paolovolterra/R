---
title: "ETL"
---

" [DataEditR ](https://github.com/DillonHammill/DataEditR)

![](https://raw.githubusercontent.com/DillonHammill/DataEditR/master/man/figures/DataEditR/DataEditR-README.gif)

# [DataEditR](https://rpubs.com/timness/759633)
Pacchetto R basato su shiny e rhandsontable che rende facile visualizzare, inserire, filtrare e modificare i dati in modo interattivo.

![](https://raw.githubusercontent.com/DillonHammill/DataEditR/master/vignettes/DataEditR/DataEditR-15.gif)

	library(DataEditR)
	df <- read.csv("cglobal_202107.csv", sep='\t')
	data_edit(df)
	data_edit(df, viewer = "viewer")
	data_edit(df, viewer = "browser")
  
