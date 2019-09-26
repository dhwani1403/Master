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


### Below tables can give the idea that what type of data a resercher should collect and how to organize that Data for Planktons species so that it will be easy to make any decision from the data. 


#### Solutions to above mentioned problems

* Specify Date formate for easy understanding.
* Add Time column so that we can identify the day and night parameters.
* Specify the measurment unit for DEpth, Density, Colony Size, Temperature.
* Merge two tables of Zoop to decrease the redundancy.
* Avoid negative values except Temperature readings or we can add contraints that no negative values will be accepted for Depth, Density & Colony size.
* Add Location column to mention that sample has been taken from Pond or Zoop (Station B is in a shallower southern arm of the lake).
* Chla value can be **N.A.** for Pond location.

#### Table #1 for **All locations**

| Date (MM/DD/YYYY) |Location| Time (AM/PM) | Depth (Meters) | Density (#/L) | ColonySize (Meters) | Species Name | Chla |Temperature (Fahrehneit) |
|------|--------------|---|-----------------|--------------|---------------------|--------------|--------------------------|---|
|      |              |---|                 |              |                     |              |                          |    |
|      |              |---|                 |              |                     |              |                          |  |
|      |              |---|                 |              |                     |              |                          |  |


