# Tutorial: Extracting Geo-coordinates

This part will show you how to deal with geographic locations in the Vistorian. The demo network (see below) is a social network based on letter correspondences. The following walks through:

* how to extract geo-coordinates
* how to fix wrong coordinates
* how to save and load existing geo locations.

See here for how to [load data into the Vistorian](#2.-Loading-Data
).


### Extracting geolocations
This tutorial assumes that geolocations are encoded as additional columns in a [link table](../formattingdata.md). In this table, every line corresponds to a link with two locations: one for each node. The table uses column names Place1 and Place2, but you can name columns in your data as you like:
![image](../assets/Images/ExtractGeoCord_1.png)

First, we tell the Vistorian which columns in our table are locations, and to which node they belong: select **Location_source** and **Location_target** from the respective dropdown menus.
![image](../assets/Images/ExtractGeoCord_2.png)

Next, scroll down the bottom of the Data View page and you realize that the Vistorian has created a new table, containing an entry of each location entry it could find in your link table. 
![image](../assets/Images/ExtractGeoCord_3.png)

This table contains the following field:

* **Id**: a unique internal identifier. You must not edit it.
* **User name**: this the location name you have specified in your link table. This field, too, must not be touched.
* **Geoname**: this is the official location name that will be send to the geo service to obtain the coordinates. At the beginning Vistorian will populate this column with the user names. However, as some location names in your may not correspond to currently existing locations known by the geoservice, you can change geonames (see below).
* **Longitude / Latidude**: geocoordinates.

### Obtaining geo-coordinates
Once you have your location table, click the ‘Update location coordinates‘ button in the gray area just above the table.
![image](../assets/Images/ExtractGeoCord_4.png)

This will send your geonames to a [geoservice called Nominatim](https://nominatim.openstreetmap.org/ui/search.html) and populate the location table with coordinates where it could find the corresponding entries. Note that this time, one location has not been found: 
![image](../assets/Images/ExtractGeoCord_5.png)

The problem here is that Ile St Domingue is the french name, while the geoservice needs english names. If you click into the geoname-field that says Ile St Domingue, change it to Santo Domingo and click again Update location coordinates. This will find the right coordinates.

### Solving ambiguous geonames
The demo data set contains some ambiguous location names such as Orléans (France, Canada) and Brest (France, Belarus). To solve ambiguity you can specify more information in the geoname column (don’t ever change the user name column as this will break your data set).

For example, for Orléans, write Orléans France, then click Update location coordinates. You will see that the coordinates have changed and that Orléans is now in France.

![image](../assets/Images/ExtractGeoCord_6.png)

Of course, you can use the [map visualization](https://vistorian.github.io/visualizations.html/#map) to verify all your locations, then return to the data view, fix the coordinates, and reload the map visualization.

### Saving and using existing location tables
As creating clean and correct location tables can be tedious, you can export your table with the Export as CSV button at the right in the gray area.

 <img src="../assets/Images/ExtractGeoCord_7.png" width="30%" height="30%" class="center"> 

To import an existing location table, chose Upload from the Vistorian menu, next to Data Tables (figure right). Select your csv and it will show under the Data Tables headline in the menu (e.g., userLocationTable.csv).

Next, specify the location fields in your link table (see above).

Last, chose that table in the Location Table drop down menu as shown below.

If you specify the location fields after selecting a location table, the Vistorian will create a new one. In this case, just re-select your original location table from the dropdown menu.

![image](../assets/Images/ExtractGeoCord_8.png)
