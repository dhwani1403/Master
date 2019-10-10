# Linda Loring Nature Foundation Phenology dataset
                                         
**Phenology Dataset has been given by Dr. Sarah T Bois. This data has been recorded as per month basis and then later divided as per Sites.
This dataset contains some important parameters for phenology like Date & Time, Temerature, Intensity and many more. I am using data of _Site H (Site_H.csv)_ for months from _June 2016 to Oct 2016_.**

### Below I have attached some Rplots which has been created with Date & Time, Temerature, Intensity variables.

#### 1a) Two scatter plots of two different variables

**_Scatter plot for Temperature and Intensity_**

From this scatter plot we can make some comments like Intensity is increasing as the temperature increases. There are some data missing in the excel file for Intensity and Temperature for some dates.

![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot_1a.jpeg)
```
> library(tidyverse)
> library(ggplot2)
> LLNF <- read.csv("Site_H.csv", header = TRUE)
> colnames(LLNF)
> names(LLNF)[names(LLNF) == "Date.Time..GMT.04.00"] <- "DateTime"
> names(LLNF)[names(LLNF) == "Temp..Â.C..LGR.S.N..10638853..SEN.S.N..10638853."] <- "Temperature"
> names(LLNF)[names(LLNF) == "Intensity..Lux..LGR.S.N..10638853..SEN.S.N..10638853."] <- "Intensity"
> ggplot(LLNF,aes(x=Temperature,y=Intensity))+
+ geom_point(color="Dark blue")
```
---
#### 1b)

**_Scatter Plot for Intensity and DateTime**

From the Rplot we can say that Intensity is consistent for few months (June 2016-Oct 2016). There are some outliers, may be they are bad readings.


![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot_1b_1.jpeg)
```
> LLNF$DateTime <- as.Date(LLNF$DateTime,format("%m/%d/%y"))
> ggplot(LLNF,aes(x=DateTime,y=Intensity))+
+ geom_point(color="Dark blue")
```
---
#### 2) One scatter plot with three variables

**_Scatter plot of three variables Intensity ,Temperature & DateTime_**

From the below Scatter plot we can suggest that through the DateTime , Intensity is consistent and Intensity has large value when temperature was above 20°C

![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot_2_1.jpeg)
```
> ggplot(LLNF,aes(x=DateTime,y=Intensity,color=Temperature))+
+ geom_point()
```
---
#### 3) One scatter plot of two variables, properly labeled, with a trend line added in

**_Scatter plot for Intensity & Temperature with Trend Line_**

Trend line in below scatter plot is showing that intensity is proportional to Temperature. Trend line is going upwards as Intensity increases with Temperature.

**_Note_**: This plot can have negative values for Temperature but as excel sheet does not contain any negative values for Temperature so thus plot.

![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot_3.jpeg)
```
> ggplot(LLNF,aes(x=Temperature,y=Intensity))+
+ geom_point()+
+ geom_smooth(method="lm")
```
---
#### 4) One faceted plot of two variables

**_Facet Plot with three variables Intensity, Temperature, DateTime_**

From the below plot we can observe two different varibales in two different windows, it is easy to compare Intensity and Temperature variable as per the DateTime which is on X axis.


![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot_4_1.jpeg)
```
> LLNF1<-gather(LLNF,key="measure",value="value",c(Intensity,Temperature))
> ggplot(LLNF1,aes(x=DateTime,y=value))+
+ geom_point()+
+ facet_wrap(~measure)+
+ theme_bw()
```
---
#### 5) One bar chart

**_Bar chart with two variables DateTime and Temperature_**

Temperature is consistent through the months (June 2016-Oct 2016), I am not sure about the values of Y axis as they are coming like 200, 400..

![](https://github.com/dhwani1403/Master/blob/master/LLNF_Data/Rplot.jpeg)
```
> ggplot(LLNF,aes(x=DateTime,y=Temperature,fill="grp"))+
+ geom_bar(stat="identity",color="blue",width=0.5)
```
---

