---
title: "Tabelle in R"
---


https://themockup.blog/posts/2020-09-04-10-table-rules-in-r/  

Add images to table	https://bjnnowak.netlify.app/2021/10/04/r-beautiful-tables-with-gt-and-gtextras/

Stargazer: A solution to produce amazing academic tables  
https://ignacioriveros1.github.io/r/2021/03/25/stargazer-for-amazing-academic-tables.html  

Las 5 librerías de R para hacer tablas  
![](https://elartedeldato.com/wp-content/uploads/2021/09/Screenshot-2021-09-22-at-18.35.24.png)  
![](https://elartedeldato.com/wp-content/uploads/2021/09/Screenshot-2021-09-22-at-18.08.30-1024x265.png)  





<br>



![](./immagini/tabelle1.png)

<br>


# Xtable 

<br>


# Booktabs

<br>


##[Figure e tabelle ](https://kbroman.org/knitr_knutshell/pages/figs_tables.html){:target="_blank"}

<br>


# [kable](https://cran.r-project.org/web/packages/kableExtra/vignettes/awesome_table_in_html.html){:target="_blank"}
Create Awesome LaTeX Table with knitr::kable and kableExtra

The goal of kableExtra is to help you build common complex tables and manipulate table styles. 

It imports the pipe %>% symbol from magrittr and verbalize all the functions, so basically you can add “layers” to a kable output in a way that is similar with ggplot2 and plotly.

![](./immagini/kableExtra0.png)
![](./immagini/kableExtra.png)

![](./immagini/kableExtra2.png)

<br>





## altre

[How to convert an Excel or csv table into a LaTeX table in three different ways:](https://www.youtube.com/watch?v=F4s1Rnla1r4){:target="_blank"}

* [Tables Generator](https://www.tablesgenerator.com/latex_tables){:target="_blank"}

* [Excel2LATEX](https://ctan.org/pkg/excel2latex?lang=en){:target="_blank"}

* [Pandas to_latex](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_latex.html){:target="_blank"}



<br>



# Tabelle

knitr::kable()è il modo migliore per includere le tabelle in un rapporto Markdown R, come spiegato in dettaglio qui . Ancora una volta, questa funzione è intelligente nella selezione automatica della formattazione corretta per l'output selezionato.

```{r table}
knitr::kable(mtcars[1:5,, 1:5], caption = "A table caption")
```

Se vuoi creare le tue semplici tabelle in R Markdown e stai usando R Studio, puoi dare un'occhiata al insert_table pacchetto . Fornisce un'interfaccia grafica ordinata per creare tabelle.

Il raggiungimento dello stile personalizzato della larghezza della colonna della tabella va oltre lo scopo di knitr, ma il kableExtrapacchetto è stato scritto per aiutare a raggiungere questo obiettivo: https://cran.r-project.org/web/packages/kableExtra/index.html



<br>


# Generare tabelle

https://www.tablesgenerator.com/markdown_tables <img src="./immagini/13.PNG" width="300px" />

    Table Header  | Second Header
    ------------- | -------------
    Cell 1        | Cell 2
    Cell 3        | Cell 4
    
    
    