---
YAML
---
Esempi interessanti che ho utilizzato per realizzare pagine HTM autonome come:

* appunti-di-lavoro---imprese.html

* linguaggio-R---appunti.html

	output:
	  rmdformats::downcute:
		self_contained: true
		thumbnails: true
		lightbox: true
		gallery: false
		highlight: tango
	
	
		5 7 8 9 10 screen swiss
	output: rmdformats::readthedown
	output: rmdformats::downcute

		
		
	output:
	  html_document: 
		theme: readable
		highlight: haddock
		toc: true
		toc_float: true
		number_section: true
		code_folding: hide
		df_print: paged
		css: D:\DIR\R\css\adv.css
		
	---
	title: "LINGUAGGIO R - APPUNTI"
	author: "Paolo Volterra"
	date: "`r format(Sys.time(), '%d %B %Y')`"
	output:
	  html_document: 
		theme: readable
		highlight: haddock
		toc: true
		toc_float: true
		number_section: true
		code_folding: hide
		df_print: paged
	---	

# Documenti HTML
[approfondimenti](https://garrettgman.github.io/rmarkdown/html_document_format)


La posizione del sommario è fissata nel modello HTML predefinito di R Markdown. Se vuoi cambiare la sua posizione nel documento, dovrai modificare il modello:

    Crea una copia del modello HTML R Markdown da utilizzare come punto di partenza. Puoi trovarlo eseguendo questo comando R: system.file("rmd/h/default.html", package="rmarkdown")
    Muovi il $tocsezione in cui si desidera visualizzare il sommario.
    Salva il modello modificato nella stessa cartella del documento che stai visualizzando, ad es lowertitle.html
    Aggiungere template: lowertitle.htmlal html_documentimpostazioni.