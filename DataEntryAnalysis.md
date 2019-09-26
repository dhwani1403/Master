## Introduction of Assignment
Three data files are given which contains the data for Plankton Organism and its two species. We need to organize the data in more efficient way and create the Data table. This table can be used as a reference for future studies by researchers.

## List of the some problems in the given file

_**Pond 2010**_

* Date Formate is unclear, is it MM:DD:YYYY or DD:MM:YYYY
* What parameter is **Z** in File # 1, we can interpret the column significance.
* If we consider Z as Depth then Measurement unit for **Depth** and **Temperature** Column is not specified.
* Some data is missing for depth Z, Temp, density, colony Diameter column.
* At what time of the day sample has been taken, is not mention since it is important to mention the time as species density changes from day to night.



**_Zoop-temp-main_**

* Some Temperature data is missing.
* Time of sample taking is not mentioned.
* What is Chla, Column name should be easy to interpret.


**_Zoop-temp_**

* Data can not be negative , it must be either positive or 0 (row 20 & 35)
* Time of sapmle taking is not mentioned.
* In place of two or three tables we can create ! table which can contain Location Column so handling data will be easy




## Solutions to above mentioned problems

* Specify Date formate for easy understanding.
* Add Time column so that we can identify the day and night parameters.
* Specify the measurment unit for DEpth, Density, Colony Size, Temperature.
* Avoid negative values except Temperature readings or we can add contraints that no negative values will be accepted for Depth, Density & Colony size.
* Add Location column to mention that sample has been taken from Pond or Zoop (Station B is in a shallower southern arm of the lake).
* Chla value can be **N.A.** for Pond location.
* Merge three tables in to one to avoid redundancy and it will be easy to handle 1 table instead of 3 tables. Or in future if researchers want to study any othe species also so they do not have to change the table structure, they just have to add the data in the rows.


## Below table can give the idea that what type of data a resercher should collect and how to organize that Data for Planktons species so that it will be easy to make any decision from the data. 

#### Table for **All locations**

| Date (MM/DD/YYYY) |Location| Time (AM/PM) | Depth (Meters) | Density (#/L) | ColonySize (Meters) | Species Name | Chla |Temperature (Fahrehneit) |
|------|--------------|---|-----------------|--------------|---------------------|--------------|--------------------------|---|
|  6/18/2018    | Pond | 1:00 PM  |    0.5      |    40          |    3.22      |    Cuni          |    N.A.  |  15.5  |
|  6/18/2018    | Pond | 2:00 AM  |    5      |    80         |    2.00      |    Cuni          |    N.A.  |  14  |
| 6/18/2018     | Station B  | 1:00 PM  |    0.5   |         87     |    2.44   |     Chippo         |       3.2  | 18.8 |
| 6/18/2018     | Station B  | 2:00 AM  |    5   |        67    |    2.2   |     Chippo         |       2.8  |16  |



