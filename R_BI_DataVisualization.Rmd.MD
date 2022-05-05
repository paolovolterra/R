---
title: Data visualisation
---

10 Tips to Customize Text Color, Font, Size in ggplot2 with element_text()
https://cmdlinetips.com/2021/05/tips-to-customize-text-color-font-size-in-ggplot2-with-element_text/  

![](https://i2.wp.com/cmdlinetips.com/wp-content/uploads/2021/05/customize_plot_tag_with_element_text_theme_ggplot2.png?w=630&ssl=1)

# Data Visualization with R
https://rkabacoff.github.io/datavis/  
![](https://rkabacoff.github.io/datavis/img/cover.png)

# [Heat Map](https://r-charts.com/correlation/heat-map-ggplot2/)

![](https://r-charts.com/en/correlation/heat-map-ggplot2_files/figure-html/heat-map-gradientn-ggplot2.png)

# [waffle chart ](https://r-charts.com/part-whole/waffle-chart-ggplot2/)  
![](https://r-charts.com/en/part-whole/waffle-chart-ggplot2_files/figure-html/waffle-chart-iron-keep-ggplot2.png)


# Dumbbell

Il Dumbbell Plot è una visualizzazione che mostra il cambiamento tra due punti nei nostri dati. Prende il nome a causa della del forma manubrio.  
È un ottimo modo per mostrare i dati che cambiano tra due punti (dall'inizio e alla fine)
![](https://i1.wp.com/www.business-science.io/assets/2021-08-12-ggalt-dumbbell-plots/03_plot_output.jpg?w=578&ssl=1)


# Circular barplot with R and ggplot2

https://www.r-graph-gallery.com/web-circular-barplot-with-R-and-ggplot2.html  

![](https://www.r-graph-gallery.com/img/fromTheWeb/dataviz_hiking.png)

# Boxplot

https://waterdata.usgs.gov/blog/boxplots/

![](https://sdcastillo.github.io/PA-R-Study-Manual/Exam-PA-Study-Manual_files/figure-html/unnamed-chunk-50-1.png)

![](https://cdn-images-1.medium.com/max/1600/1*NRlqiZGQdsIyAu0KzP7LaQ.png)
![](https://waterdata.usgs.gov/blog/static/boxplots/picsWithDL-1.png)



# [Colourpicker](https://cran.r-project.org/web/packages/colourpicker/vignettes/colourpicker.html)

# [Esquisse](https://github.com/dreamRs/esquisse)

![](https://raw.githubusercontent.com/dreamRs/esquisse/master/man/figures/esquisse.gif)

# ggridges: Ridgeline plots in ggplot2


![](https://wilkelab.org/ggridges/articles/gallery_files/figure-html/unnamed-chunk-4-1.png)

# Patchwork 

https://github.com/thomasp85/patchwork


# Scatterplot

https://github.com/jtlandis/ggside  
![](https://github.com/jtlandis/ggside/raw/main/man/figures/README-example-mix-scales-1.png)

https://github.com/olihawkins/pilot  
![](https://github.com/olihawkins/pilot/raw/master/gallery/examples/scatter-chart-basic/scatter-chart-basic-1.png)

Small multiple scatterplot  
https://github.com/olihawkins/pilot  
![](https://github.com/olihawkins/pilot/raw/master/gallery/examples/scatter-chart-facets/scatter-chart-facets.png)
---

# [HEXMAPS](https://github.com/ONSgeo/HexMapping)

![](https://github.com/ONSgeo/HexMapping/raw/master/MD_images/Indonesia_kabupaten_bdys_population_hexmap.png)

https://pbs.twimg.com/media/FDZPmKZWQAMCDyh?format=jpg&name=small

![](https://github.com/BlakeRMills/30DayMapChallenge/blob/main/Day%204%20(Hexagons)/Day%204%20(Hex).R)

---
# vistime - Pretty Timelines in R 

https://github.com/shosaco/vistime  
![](https://github.com/shosaco/vistime/raw/master/man/figures/basic_highchart.png)  


# Sankey

https://r-charts.com/flow/sankey-diagram-ggplot2/  

![](https://r-charts.com/en/flow/sankey-diagram-ggplot2_files/figure-html/sankey-diagram-ggplot2-remove-legend.png)

# Chord Diagram

![](https://r-charts.com/en/flow/chord-diagram_files/figure-html/chord-diagram-colors.png)


# [ggvis](https://ggvis.rstudio.com/#:~:text=ggvis%20is%20a%20data%20visualization,Rstudio%20or%20in%20your%20browser.)

[ggforce](https://rviews.rstudio.com/2019/09/19/intro-to-ggforce/#:~:text=The%20ggforce%20package%20is%20an,facets%20%2C%20and%20other%20ggplot%20functions.)

![](https://rviews.rstudio.com/post/2019-09-16-intro-to-ggforce_files/figure-html/unnamed-chunk-6-1.png)
---
#Hystogram

---

# [Lattice](https://www.rdocumentation.org/packages/lattice/versions/0.20-41)
---

# [Plotly](https://plotly.com/r/)
---

# [Patchwork](https://patchwork.data-imaginist.com/)

	library(ggplot2)
	library(patchwork)

	p1 <- ggplot(mtcars) + geom_point(aes(mpg, disp))
	p2 <- ggplot(mtcars) + geom_boxplot(aes(gear, disp, group = gear))

	p1 + p2

![](https://patchwork.data-imaginist.com/reference/figures/README-example-1.png)

	p3 <- ggplot(mtcars) + geom_smooth(aes(disp, qsec))
	p4 <- ggplot(mtcars) + geom_bar(aes(carb))

	(p1 | p2 | p3) /
		  p4

![](https://patchwork.data-imaginist.com/reference/figures/README-unnamed-chunk-2-1.png)

	p1 + gridExtra::tableGrob(mtcars[1:10, c('mpg', 'disp')])

![](https://patchwork.data-imaginist.com/articles/guides/assembly_files/figure-html/unnamed-chunk-6-1.png)


##Altre immagini

![](https://patchwork.data-imaginist.com/articles/guides/assembly_files/figure-html/unnamed-chunk-14-1.png)

![](https://patchwork.data-imaginist.com/articles/guides/assembly_files/figure-html/unnamed-chunk-15-1.png)

![](https://patchwork.data-imaginist.com/articles/guides/assembly_files/figure-html/unnamed-chunk-17-1.png)

![](https://patchwork.data-imaginist.com/articles/guides/assembly_files/figure-html/unnamed-chunk-23-1.png)

![](https://patchwork.data-imaginist.com/articles/guides/layout_files/figure-html/unnamed-chunk-22-1.png)

---


# [quantmod](https://www.rdocumentation.org/packages/quantmod/versions/0.4.17)
---

# [raincloud](https://shilaan.rbind.io/post/visualizing-data-with-raincloud-plots/)

![](https://shilaan.rbind.io/post/visualizing-data-with-raincloud-plots/featured_hu417f03dcf8ed10f9d81113a42e3ecf31_311987_720x0_resize_q75_lanczos.jpg)

https://wellcomeopenresearch.org/articles/4-63/v2

---

# [RGL](https://cran.r-project.org/web/packages/rgl/vignettes/rgl.html#introduction)

---

# [TidyTuesday](https://github.com/mikeShout/TidyTuesday)

https://github.com/mikeShout/TidyTuesday/tree/master/2021_44_UltraRunning

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2021_44_UltraRunning/Ultramarathons.png)

https://github.com/mikeShout/TidyTuesday/tree/master/2020_45_IKEA

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_45_IKEA/IKEA_PricevSize.png)

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_21_VolleyBall/volleyball_xgboost_files/figure-markdown_github/explorePlots-1.png)

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_49_TorontoShelters/readme_files/figure-markdown_github/3rdBox-1.png)

## Network Diagram

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_51_NinjaWarrior/ninjaWarrior_files/figure-markdown_github/arc-2.png)

## Theme Economist

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_52_BigMacIndex/BigMacIndex_files/figure-markdown_github/explore-2.png)

![](https://raw.githubusercontent.com/mikeShout/TidyTuesday/master/2020_52_BigMacIndex/BigMacIndex_files/figure-markdown_github/calc-4.png)

---
# Da sistemare

![](https://wellcomeopenresearch.s3.amazonaws.com/manuscripts/18219/d324e0ad-4ca0-4d1e-8d9b-9627067f51fa_Figure%20M7.gif)

https://wellcomeopenresearch.org/articles/4-63/v2



# [Esplorazione dei dati categoriali con Inspectdf](https://www.r-bloggers.com/2019/06/exploring-categorical-data-with-inspectdf/)

![](https://i1.wp.com/alastairrushworth.github.io/assets/images/inspect_cat_plot_1-1.png?w=578&ssl=1)

# [da approfondire](https://ggobi.github.io/ggally/reference/ggpairs.html)

![](https://ggobi.github.io/ggally/reference/ggpairs-2.png)
![](https://ggobi.github.io/ggally/reference/ggpairs-7.png)
![](https://ggobi.github.io/ggally/reference/ggpairs-8.png)

<br>


# [Chapter 5 Exploratory Data Analysis](http://www.john-ros.com/Rcourse/eda.html)

![](http://www.john-ros.com/Rcourse/Rcourse_files/figure-html/unnamed-chunk-144-1.png)

# [Introduction to Data Science]()
Ron Sarafian

[Chapter 5 Exploratory Data Analysis](https://bookdown.org/ronsarafian/IntrotoDS/eda.html)
![](http://www.john-ros.com/Rcourse/Rcourse_files/figure-html/unnamed-chunk-140-1.png)
![](https://cdn-images-1.medium.com/max/1600/1*NRlqiZGQdsIyAu0KzP7LaQ.png9

