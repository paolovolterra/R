---
R-miscellanea
---

install.packages("readxl")
library("readxl")
# xls files
my_data <- read_excel("tabella.xlsx")
my_data
my_data[1:2] <- apply(my_data[1:2]*100, 2, function(x) paste0(x, "%"))
sprintf("%.1f %%", 100*my_data)
sprintf("%s costed $ %3.2f ", stuff, price)


---
title: "appunti su R"

description: |
  Una descrizione del mio testo, non tanto breve, al punto che
  la faccio apparire su più righe in questo modo
  
tags: [ "varie", "tag", "descrivono", "il mio testo" ]

date: "2017-08-21"

author:
  - Paolo Volterra
---

## link a MYSQL SERVER

library(RMariaDB)
#Connecting to MySQL DB
stuffDB <- dbConnect(MariaDB(), user = "pvolterr", password = "***", dbname = "aida", host = "127.0.0.1")


query <- "SELECT * from q_2020vs2019;"

results <- dbSendQuery(stuffDB, query)
bilanci<- dbFetch(results)
dbClearResult(results)

View(bilanci)
str(bilanci)

sum(complete.cases(bilanci))
sum(!complete.cases(bilanci))


mean(bilanci$`20ricavi`)
mean(bilanci$`20ricavi`, na.rm = TRUE)
bilanci$`20ricavi`[is.na(bilanci$`20ricavi`)] <- mean(bilanci$`20ricavi`, na.rm = TRUE)



## SCRAPING PAGINA WEB [link](https://stackoverflow.com/questions/3195522/is-there-a-simple-way-in-r-to-extract-only-the-text-elements-of-an-html-page)

library(htm2txt)

url <- 'https://en.wikipedia.org/wiki/Alan_Turing'

text <- gettxt(url)

print(text)


## Automate PowerPoint Production Using R
https://joenoonan.se/post/using-r-to-make-powerpoint-decks/  
![](https://joenoonan.se/post/using-r-to-make-powerpoint-decks/index_files/pptx_master.gif)


## VISUALIZZARE L'IMMAGINE LOCALE

x = read.csv("my_file.csv", stringsAsFactors=FALSE) ![image](file:///D:/DIR/APPUNTI/R/immagini/01.png){ width=60% height=60% }


## 04 LEGGERE UN CSV

while base data import functions (like read.csv and read.table) convert strings to factors by default, tidyverse functions (like read_csv from the readr package or read_excel from the readxl package) do not.

With base R functions, to avoid conversion of strings to factors you would do, for example:

x = read.csv("my_file.csv", stringsAsFactors=FALSE)

In readr you can just read the file, as there is no stringsAsFactors argument and no automatic conversion of strings to factors:

library(readr)
x = read_csv("my_file.csv")

However, if you wish you can also use the optional col_types argument to specify whether a particular column should be read in as a factor. See the col_types section of the help for read_csv for details.


## 04 SCRIVERE UN CSV

## 45 - DATABASE



## 47 STATISTICA DI BASE


## 48 EDA 
![image](D:/DIR/APPUNTI/R/immagini/03.PNG){ width=50% height=50% }

* _names() o colnames()_

* class()

* head() e tail()

* mean() median() quantile()


## [49 DATA QUALITY](https://www.udemy.com/course/introduzione-a-r/learn/lecture/19868268#content){ width=60% height=60% }

### MISSING VALUES

#### VEDERE SE CI SONO ![image](D:/DIR/APPUNTI/R/immagini/04.PNG){ width=60% height=60% }

dataset

	data <- data.frame(x1 = c(7, 2, 1, NA, 9), 
	x2 = c(1, 3, 1, 9, NA),
    x3 = c(NA, 8, 8, NA, 5))		   
				   
|comando                    |cosa fa                          |output|
|---------------------------|---------------------------------|-------|
|is.na(df)                  |vedere se ci sono valori mancanti|
|complete.cases(data)		|                                 | # [1] FALSE  TRUE  TRUE FALSE FALSE|
|table()complete.cases(df)) |quanti sono?                     | # [1] FALSE  TRUE  TRUE FALSE FALSE|
|sum(complete.cases(df))    |totale completi                  |
|sum(!complete.cases(df))   |totale incompleti                |


final[complete.cases(final), ]

na.omit is nicer for just removing all NA's. complete.cases allows partial selection by including only certain columns of the dataframe:

final[complete.cases(final[ , 5:6]),]

Your solution can't work. If you insist on using is.na, then you have to do something like:

final[rowSums(is.na(final[ , 5:6])) == 0, ]

but using complete.cases is quite a lot more clear, and faster.

![image image](file:///D:/DIR/APPUNTI/R/immagini/09.png "Image Description"){ width=50% height=50% }

![image image](file:///D:/DIR/APPUNTI/R/immagini/10.png "Image Description"){ width=50% height=50% }



con VIM si vedono graficamente (in rosso)

> library(VIM)

> matrixplot(df) 

![image image](file:///D:/DIR/APPUNTI/R/immagini/05.png "Image Description"){ width=50% height=50% }

#### TOGLIERE [listwise deletion](https://statisticsglobe.com/listwise-deletion-missing-data/)

> na.exclude(df) 

> na.omit(df)

> df[complete.cases(df),]

> library(tidyr)

> drop_na(df)



#### SOSTITUIRE 

1. con media  ° mean(df$var1)* o mediana della variabile dove mancano i valori 



> col valore medio calcolato ![image image](file:///D:/DIR/APPUNTI/R/immagini/06.png "Image Description"){ width=50% height=50% }

> col valore medio precalcolato  ![image image](file:///D:/DIR/APPUNTI/R/immagini/07.png "Image Description"){ width=50% height=50% }


2. data mining predittivo

3. hot deck (per variabili qualitative)



### OUTLIERS

#### vederli con boxplot

mtcars

boxplot(mtcars)$out

boxplot(mtcars$hp)$out

boxplot(mtcars$hp, plot = FALSE)$out

#### toglierli 

outliers <- boxplot(mtcars$hp, plot = FALSE)$out

mtcars[-wich(mtcars$hp 

 ![image image](file:///D:/DIR/APPUNTI/R/immagini/08.png "Image Description"){ width=50% height=50% }

#### sostituirli


### DATI DUPLICATI

duplicated(df)

wich(duplicated(df))

sum(duplicated(df))

### FORMATI ERRATI

### INCONSISTENZE

## 50 VISUALIZZARE I DATI


## [51 GRAFICA DI BASE](https://www.udemy.com/course/introduzione-a-r/learn/lecture/5688706#content)

Possiamo stampare tutti colori a disposizione come funziona kolors creare un oggetto con alcuni colori scelti da noi Apriamo un nuovo grafico dove al posto delle palette Dr mettiamo il nostro oggetto possiamo personalizzare il grafico mettendo un titolo utilizzando il parametro mail un sottotitolo utilizzando il parametro sub l'asse delle x 40 x Lab modificare ad esempio il grafico Crea un nuovo grafico dove invece delle frequenze assolute quindi il numero di persone per unicità mettiamo la percentuale che gli utilizziamo la funzione plot table se abbiamo tutto in un nuovo oggetto e poi riprendiamo il grafico tramite questo nuovo oggetto possiamo creare un grafico a torta semplicemente utilizzando la funzione fai è dentro la funzione mettendo l'oggetto in questo caso le percentuali in questo caso possiamo personalizzare maggiormente il grafico magari cambiando i colori utilizzando il parametro collo magari non titola nostro grafico anche questo vettore maniera casuale creare una seconda tabella con i generi

E mi vado a creare un unico da prima che includa sia il genere sia le città
Sentiamo adesso le due variabili della cassetta tramite era funzione Mosaic plot funziona mettendo una tilda e poi mettendo in relazione le due variabili che vogliamo. ridurre il grafico e poi come secondo parametro inserendo i dati ossia il Data Frame
Il risultato è un grafico che finisce per la punto dove è più presente il genere maschile piuttosto che il genere femminile nelle varie città in questo caso per rendere più carino il risultato è l'italiano Questo pacchetto Air colorbrewer
Contiene una serie di tavolozze di colori siamo trovarle facilmente cercando il nome del pacchetto su Google quindi te ne scegliamo una ad esempio spectral e andiamo a modificare il nostro bardotto ci prendiamo un oggetto con la tavolozza scelta entriamo il grafico tracolla mettendo la nostra tavolozza quindi possiamo mettere a grafico sia variabili singola sia a due variabili qualitative nello stesso momento se parliamo di grafici per variabili qualitative numeriche i tipi di grafici più comuni sono scatterplot e istogrammi possiamo utilizzare la funzione plot per creare un istogramma che prenda in considerazione tutte le variabili di un dataset variabile Float abbiamo diversi parametri il primo dei quali abbiamo visto ci permette di inserire l'asse delle x il secondo l'asse delle y
Ma anche il titolo del nostro grafico

Il sottotitolo
Il nome dell'asse delle x
Asse delle y
Il colore del grafico
Ecco il parametro pch il tipo di indicatore
Come vedete al 6 corrispondono questi triangolini rovesciati

Possiamo decidere il tipo di indicatore guardando questo specchietto che presenta le varie opzioni del parametro pch
Possiamo anche Mostrare i valori delle variabili con colori differenti In questo primo caso creiamo due grafici che si sovrappongono in buona sostanza Quindi mettiamo la variabile S pallandt in blu e la variabile sapa luitz in rosso
Oppure possiamo creare un vettore con i nomi dei colori associati alle 3 tipologie
E poi Creiamo un grafico che mettendo in relazione due variabili ci mostri i tre colori appunto delle tipologie di fiore
Altri tipi di grafico ad esempio quelli che seguono l'andamento nel tempo di un certo fenomeno Sono meglio rappresentati tramite delle linee in questo caso possiamo sempre utilizzare la funzione plot ma andremo a modificare un altro a parametro o sia il parametro Type
In questa data set her Passenger Sono inclusi dei dati sul numero di passeggeri di aerei che hanno volato tra il 1949 e il 1960 e come vedete la rappresentazione è meglio data da una linea che segue nel tempo appunto all'andamento dei Passeggeri
Qui possiamo andare a modificare Ad esempio la linea Secondo le nostre preferenze
Sempre type-l che sta per line e poi andiamo a modificare il colore ad esempio della linea per questo utilizzeremo il parametro lvd


# R Commander

install.packages("Rcmdr")

library(Rcmdr)

