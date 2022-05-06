---
title: "Elaborare PDF"
---

# [tabulizer](https://www.r-bloggers.com/2019/09/pdf-scraping-in-r-with-tabulizer/)

fornisce collegamenti R alla libreria Java Tabula , che può essere utilizzata per estrarre computazionalmente tabelle da documenti PDF. La funzione principale extract_tables()imita il comportamento della riga di comando della Tabula, estraendo tutte le tabelle da un file PDF e, per impostazione predefinita, restituisce quelle tabelle come un elenco di matrici di caratteri in R. 


    
    library("tabulizer")
    endangered_species_scrape <- extract_tables(
        file   = "D:/DIR/lavoro/QEF_590_20.pdf", 
        method = "decide", 
        output = "data.frame")

![](./immagini/cbimage.png)
    
    
[Scraping PDF files in R ‘manually’ with tabulizer package](https://rpubs.com/behzod/tabulizer){target="_blank"}

[Extracting Tables from PDFs in R using the Tabulizer Package](https://datascienceplus.com/extracting-tables-from-pdfs-in-r-using-the-tabulizer-package/){target="_blank"}

[PDF Scraping in R with tabulizer](https://www.r-bloggers.com/2019/09/pdf-scraping-in-r-with-tabulizer/){target="_blank"}

[Importare tabelle da PDF](https://www.agnesevardanega.eu/wiki/r/gestione_dei_dati/importare_tabelle_da_pdf){target="_blank"}

Per importare dati da un file pdf, usiamo il pacchetto tabulizer1), che usa la libreria open source tabula :

install.packages("tabulizer")
library(tabulizer)

<br>

## Estrarre i dati

<br>


### Estrarre direttamente la tabella

mydata <- extract_tables(file.choose()) 

Si aprirà la finestra di dialogo, che consentirà di scegliere il file PDF. Naturalmente, è possibile indicare semplicemente il nome del file:

mydata <- extract_tables("myfile.pdf") 

Possono essere estratte tabelle da più pagine. Il risultato sarà una lista di tabelle (formato carattere).

<br>


### Scegliere la pagina

Per indicare la pagina del file in cui è presente la tabella, usare l'argomento pages:

mydata <- extract_tables(file.choose(), pages = 3) 

In questo caso, verrà estratta la tabella a pagina 3.

<br>


### Selezionare interattivamente la tabella

Se nella pagina sono incluse diverse tabelle o aree di testo e tabelle, possiamo usare la funzione extract_areas():

mydata <- extract_areas(file.choose()) 

Si aprirà una interfaccia html (Shiny) che permetterà di selezionare la tabella o area di testo da importare.

<br>


### Trasformare i dati in dataframe o altro oggetto

Infine, trasformeremo i dati importati nel tipo di oggetto adatto, ad esempio un dataframe:

mydf <- as.data.frame(mydata)

1) Thomas J. Leeper (2018). tabulizer: Bindings for Tabula PDF Table Extractor Library.

<br>

---



    ```
    library("tabulizer")
    endangered_species_scrape <- extract_tables(
      file   = "C:/Users/paolo/Downloads/20211101_78.pdf", 
      method = "decide", 
      output = "data.frame")
    
    library(tidyr)
    library(dplyr)
    library(purrr)
    # Pluck the first table in the list
    endangered_species_raw_tbl <- endangered_species_scrape %>% pluck(1) %>% as_tibble()
    
    endangered_species_raw_tbl %>% knitr::kable()
    
    
    endangered_species_raw_tbl %>% head() %>% knitr::kable() # Show first 6 rows
    endangered_species_raw_tbl
    ```

############
    ```
    options(java.parameters = "-Xmx12000m")
    
    library(beepr) #for fun sounds when task is completed :)
    library(tidyverse)
    library(tabulizer)
    library(shiny)
    
    
    area <- locate_areas("D:/DIR/lavoro/QEF_590_20.pdf", pages = 12)
    
    area
    View(area)
    ```
-----------------------------------------------------------------------------------------------------------------------
# siti interessanti
* https://www.business-science.io/finance/2020/02/21/tidy-discounted-cash-flow.html
* 

#############

# [Tesseract]()
    ```
    library(tesseract) #https://github.com/tesseract-ocr/tessdoc
    tesseract_download("ita")
    ita <- tesseract("ita")
    
    tesseract_info()
    
    text <- tesseract::ocr("https://edicoladigitale.milanofinanza.it/class/books/mf/2021/20210930mf/images/pages/Page-61.jpg)", engine = ita)
    cat(text)
    ```

https://cran.r-project.org/web/packages/tesseract/vignettes/intro.html  
https://cran.r-project.org/web/packages/tesseract/vignettes/intro.html#read_from_pdf_files


#####
    ```
    # Requires devel version of magick
    # devtools::install_github("ropensci/magick")
    # Test it
    library(magick)
    library(magrittr)
    text <- image_read("https://edicoladigitale.milanofinanza.it/class/books/mf/2021/20210930mf/images/pages/Page-60.jpg") %>%
      image_resize("1000") %>%
      image_convert(colorspace = 'gray') %>%
      image_trim() %>%
      image_ocr()
    cat(text)
    ```


############

    # Rendering should be supported on all platforms now
    # convert few pages to png
        file.copy(file.path(Sys.getenv("R_DOC_DIR"), "NEWS.pdf"), "news.pdf")
        pdf_convert("news.pdf", pages = 1:3)
    
    # render into raw bitmap
        bitmap <- pdf_render_page("news.pdf")
    
    # save to bitmap formats
        png::writePNG(bitmap, "page.png")
        jpeg::writeJPEG(bitmap, "page.jpeg")
        webp::write_webp(bitmap, "page.webp")
    
    # Higher quality
        bitmap <- pdf_render_page("news.pdf", page = 1, dpi = 300)
        png::writePNG(bitmap, "page.png")
    
    # slightly more efficient
        bitmap_raw <- pdf_render_page("news.pdf", numeric = FALSE)
        webp::write_webp(bitmap_raw, "page.webp")
    
    # Cleanup
        unlink(c('news.pdf', 'news_1.png', 'news_2.png', 'news_3.png',
                 'page.jpeg', 'page.png', 'page.webp'))


#######

# [pdftools]()

library(pdftools)
 https://ropensci.org/blog/2016/03/01/pdftools-and-jeroen/
  
 renders pdf to bitmap array
bitmap <- pdf_render_page("D:/DIR/lavoro/QEF_590_20.pdf", page = 1)

 save bitmap image
png::writePNG(bitmap, "page.png")

jpeg::writeJPEG(bitmap, "page.jpeg")
webp::write_webp(bitmap, "page.webp")

########

# Split and Join PDF files
the pdf_subset() function creates a new pdf file with a selection of the pages from the input file

https://rpubs.com/kbodwin/pdftools

## Load pdftools
library(pdftools)

## extract some pages
pdf_subset('https://cran.r-project.org/doc/manuals/r-release/R-intro.pdf',
           pages = 1:3, output = "subset.pdf")

## Should say 3
pdf_length("subset.pdf")

# Generate another pdf
pdf("test.pdf")
plot(mtcars)
dev.off()

## Similarly pdf_combine() is used to join several pdf files into one.
## Combine them with the other one
pdf_combine(c("test.pdf", "subset.pdf"), output = "joined.pdf")

## Should say 4
pdf_length("joined.pdf")


########

<br>

******************************************************************

# Da PNG a R

library(pdftools)
sapply(list, function(x)
  pdf_convert(x, format = "png", pages = NULL, filenames = NULL, dpi = 300, opw = "", upw = "", verbose = TRUE))


library(pdftools)
directory<-"pdf/data"
file.list <- paste(directory, "/",list.files(directory, pattern = "*.pdf"), sep = "")
lapply(file.list, FUN = function(files) {pdf_convert(files, format = "png",dpi = 300,pages =NULL,filenames =)})



##########


setwd("C:/Users/paolo/Downloads")
library("pdftools")
pdf.text <- pdftools::pdf_text("metenorme09_40classificazione_attivita_economiche_2007.pdf")
cat(pdf.text[[546]]) 



txt <- pdf_text("metenorme09_40classificazione_attivita_economiche_2007.pdf")
text2 <- strsplit(txt, "\n")


<br>


## Export a list into a CSV or TXT file in R
sink("output.txt")
print(text2)
sink()

<br>


## oppure

cat(capture.output(print(text2), file="test.txt"))

write(text2, file="text2.txt")



library("tabulizer")
endangered_species_scrape <- extract_tables(
  file   = "metenorme09_40classificazione_attivita_economiche_2007.pdf", 
  method = "decide", 
  output = "data.frame")
  
---


# PDF
https://ropensci.org/blog/2016/03/01/pdftools-and-jeroen/

	library(pdftools  
	download.file("http://arxiv.org/pdf/1403.2805.pdf", "1403.2805.pdf", mode = "wb")  
	txt <- pdf_text("1403.2805.pdf")  
	cat(txt[1]) # first page text  
	cat(txt[2]) # second page text  

In addition, the package has some utilities to extract other data from the PDF file. The pdf_toc function shows the table of contents, i.e. the section headers which pdf readers usually display in a menu on the left. It looks pretty in JSON:


	toc <- pdf_toc("1403.2805.pdf") # Table of contents  
	jsonlite::toJSON(toc, auto_unbox = TRUE, pretty = TRUE)  # Show as JSON

Other functions provide information about fonts, attachments and metadata such as the author, creation date or tags.

	info <- pdf_info("1403.2805.pdf") # Author, version, etc  
	fonts <- pdf_fonts("1403.2805.pdf") # Table with fonts  

<br>

# rendering pdf

A bonus feature on most platforms is rendering of PDF files to bitmap arrays. The poppler library provides all functionality to implement a complete PDF reader, including graphical display of the content. In R we can use pdf_render_page to render a page of the PDF into a bitmap, which can be stored as e.g. png or jpeg.

		bitmap <- pdf_render_page("1403.2805.pdf", page = 1) # renders pdf to bitmap array  

		png::writePNG(bitmap, "page.png")  # save bitmap image
		jpeg::writeJPEG(bitmap, "page.jpeg")
		webp::write_webp(bitmap, "page.webp")  



The pdf format is pretty dumb and does not have notion of a table (unlike for example HTML). Tabular data in a pdf file is nothing more than strategically positioned lines and text, which makes it difficult to extract the raw data.

	txt <- pdf_text("http://arxiv.org/pdf/1406.4806.pdf")  
	cat(txt[18]) # some tables  
	cat(txt[19])

Pdftools usually does a decent job in retaining the positioning of table elements when converting from pdf to text. But the output is still very dependent on the formatting of the original pdf table, which makes it very difficult to write a generic table extractor. But with a little creativity you might be able to parse the table data from the text output of a given paper.
