---
title: Mappe coropletiche
---

# [con GGPLOT](https://www.agnesevardanega.eu/wiki/r/ggplot2/mappe) 
* servono i dati dei poligoni Istat: gli shapefiles possono essere importati con la funzione st_read() e indicando il nome della cartella e non dei files  
Per rappresentare nelle mappe i valori di altre variabili, basterà aggiungere i dati al dataframe dei dati spaziali.  
Ad esempio, avendo un dataframe di dati su base regionale, bisognerà prima di tutto accertarsi che esso preveda una variabile comune con il dataframe dei poligoni (COD_REG = codice regione)
* Unire i due dataframe con right_join (vedi dplyr_join)




![](https://www.agnesevardanega.eu/wiki/lib/exe/fetch.php?media=:r:ggplot2:map02-1.png)
![](https://www.agnesevardanega.eu/wiki/lib/exe/fetch.php?media=%20:r:ggplot2:906ed35b-5e6d-4c10-b359-08c2da5fea3e.png)



# [con mapIT](http://www.milanor.net/blog/building-a-choropleth-map-of-italy-using-mapit/)

	
	df <- data.frame(
	  Regione = c("Abruzzo", "Basilicata", "Calabria", "Campania", "Emilia-Romagna",
				  "Friuli-Venezia Giulia", "Lazio", "Liguria", "Lombardia", "Marche",
				  "Molise", "Piemonte", "Puglia", "Sardegna", "Sicilia", "Toscana",
				  "Trentino-Alto Adige", "Umbria", "Valle d\'Aosta", "Veneto"),
	  valore = c(12,5,12,14,30,13,14,13,40,17,7,6,27,17,14,22,32,6,3,23))

![](http://www.milanor.net/blog/wp-content/uploads/2014/11/mapIT-plot3.png)

# [con MAPS]()

	library(maps)
	map("state", interior = FALSE)
	map("state", boundary = FALSE, col="gray", add = TRUE)

![](https://revolution-computing.typepad.com/.a/6a010534b1db25970b0120a6630f09970c-500wi)


# [con SP](https://blog.revolutionanalytics.com/2009/10/geographic-maps-in-r.html)

GADM è un database spaziale della posizione dei confini amministrativi del mondo e, come ha scoperto Claudia Engel, le informazioni sulla mappa sono disponibili come oggetti R nativi che possono essere tracciati direttamente con la spplot funzione (dal pacchetto sp ). Ad esempio, ecco come caricare i dati per la Svizzera e quindi tracciare ogni cantone con un colore che denota la sua lingua principale: 