# Data Formats

[Link Tables](#link-tables) | [Node Tables](#node-tables) | [Location Tables](#location-tables) | [Finding the right format](#finding-the-right-format) | [Formatting Time](#formatting-time) | [Issues with Data Files and Formating](#Troubleshooting-Issues-with-Data-Formatting-and-Dataset-Files)


The Vistorian imports data formatted in tables in `csv` format (**c**omma **s**eparated **v**alues, https://en.wikipedia.org/wiki/Comma-separated_values) files. Each csv contains one table. You can export `csv`-files from 
* MS Excel ([File > Save As > Select file type 'CSV'](https://support.office.com/en-ie/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba)) 
* Apple's Numbers (File -> Export to -> CSV),
* google spreadsheets (File -> Download as -> Comma-separated values), or
* you can create `CSV` by hand in any text editor.

If you have edited or compiled your data files manually, you can use the free online tool [CSVLint](https://csvlint.io) to check if your CSV file is properly formatted. 

This page explains what information you can put in your CSV files so The Vistorian can visualize it. There are some rules to follow where which information goes.

## Troubleshooting Issues with Data Formatting and Dataset Files
 For issues and errors related to data files formatting and upload please check our [troubleshooting page](https://vistorian.github.io/Troubleshooting.html##-Issues-related-to-Data-Formats-and-Dataset-Filename:).

## Terminology

This document and the [Visualization Manual](https://github.com/networkcube/vistorian/wiki/Visualization-Manual) follow the general network terminology, however there are many concepts, potentially meaning the same.

A **network** (or graph) is a set of **nodes** (or actors, or vertices, etc…) and **links** (or relations, or edges, or arcs, etc…). **Attributes** are values associated to nodes and links. Our network model currently supports the following information:

* multiple links between the same pair of nodes,
* geographic locations associated to nodes, changing over time,
* time, i.e. changing network topology, attributes, and locations

## Data Tables

The Vistorian knows three types of tables and depending on your network you need to provide between 1 and all 3 tables (explained later).

* a **link table** contains one row per link in the network while columns specify link attributes

    | SOURCE| TARGET| ATTR_1| 	…| 
    | ---   | ---   | ---   | ---| 
    | Bob   |Anton  | 	A   | 	…| 
    | Bob   |Charles| B	    |   …| 

* a **node table** contains one row per node in the network while columns specify types of relations to other nodes:

    | NODE| 	PARTNER	| FRIEND| 	…| 
    | ---| ---| ---| ---| 
    | Ana| 	Anton| 	A	| …| 
    | Bob	| Charles	| B| 	…| 

* a **location table** contains one row per geographic location and their coordinates

    | USERNAME | 	LONGITUDE| 	LANGITUDE| 
    | ---| ---| ---| 
    | Atlantis	| 13.4	| 45.2| 

Both, node and link tables can express the same network, but in many cases having your data in node or in link table format makes life easier. However, in some cases you have to provide a node table, or a link table or even both. The differences between node and link tables and which table(s) you need for your specific data are explained below.

## Link Tables

Link tables are the most common way to format network information. Each row represents a link in the network with the link's _attributes_ in columns. Using link tables you can specify a variety of link attributes such as 
* link weight
* link type
* link time (read [how to format links with time](https://github.com/networkcube/networkcube/wiki/Data-Preparation#links-in-dynamic-networks))
* geolocation of source node
* geolocation of target node
* direction (_coming soon_)

In link tables, you cannot specify attributes for nodes, such a node type.

The following explains examples of how to provide the above information in link tables.

### Simple Link Tables (no link attributes)

The simplest link table that creates a very simple network has only two columns (attributes), one that specifies the source node of a link and one that specifies the target node: 

| Sender  | Receiver |
|---------|----------|
| Bob     | Anton    | 
| Bob     | Charles  |
| Charles | Maria    | 

The corresponding CSV-file that can directly be imported into The Vistorian looks like this: 

    Sender, Receiver 
    Bob, Anton 
    Bob, Charles  
    Charles, Maria  
    Maria, Anton 

The two required fields in every link table are: 

* **Source Node** - name of the source or starting point of a link.
* **Target Node** - name of the target or end point of a link.


### Link Attributes

Additional information for each link can be added as additional columns to the link table. The following table models a social network in which links between persons that live in and move between cities, represent money transactions over several years, as well as the type of transaction.

| Sender | Sender Location | Receiver | Receiver Location | Amount | Year | Type         |
|--------|-----------------|----------|-------------------|--------|------|--------------|
| Bob    | Rome            | Charles  | Lisbon            | 10     | 1801 | Loan         | 
| Bob    | Paris           | Charles  | Lisbon            | 14     | 1803 | Gift         | 
| Bob    | Rome            | Charles  | Lisbon            | 3      | 1810 | Purchase     | 
| Bob    | Rome            | Anton    | London            | 2      | 1801 | Purchase     |  
| Anton  | London          | Bob      | London            | 5      | 1810 | Loan         |  
| ...    | ...             | ...      | ...               | ...    | ...  |...           | 

This table contains one row per transaction. Besides sender and receiver, each transaction has a time (`Year`), a weight (`Amount`), a type (`Type`) as well as the current locations of the persons involved in the transaction. Note that in row 2 (in 1803), Bob is sending the money from Paris, not from London.

The additional columns / attributes can express the following information about the network:

* **Weight** - a numeric value larger than 0
* **Link Type** - a categorical value (a string or number) representing the type of the link.
* **Time** - the time stamp of a link. Times can be anything from a specific millisecond to a year and can be formatted in many different ways as long as the **entire table uses the same time format**. Possible time formats are: 
    * `29/03/1804` 
    * `03/29/1804`
    * `1804`
    * `March 1st, 1804`
    * `13:39`
    * `1:39pm` 
    * ...
* **Source Node Location** - name of the geographic location of the source node, at the time of the link.
* **Target Node Location** - name of the geographic location of the target node, at the time of the link.

When specifying geographic locations, the application searches for their coordinates online. In order to retrieve the correct coordinates, the following guideline helps the visualization finding the right geocoordinates: 
     * **Uniqueness**: `Brest, France` instead of `Brest` (which exists in Belarus, too) 
     * **Existence**: `Charles' Drugstore, Alfama, Lisbon` instead of `Charles' Drugstore`, which may not have any geocoordinates associated to it
     * **Contemporaneity**: `St. Petersburgh` instead of the old name `Leningrad`.

There is a workaround to allow you specify antique or imprecise names, using location tables (see below).

In summary, the standard template for a link table is as follows, while the **order of columns does not matter**. Mandatory attributes are highlighted **bold**.

| ID | **Source Node** | **Target Node** | Weight | Time | Link Type | Source Location | Target Location |
|----|-----------------|-----------------|--------|------|-----------|-----------------|-----------------| 
| 0  | ...             | ...             | ...    | ...  | ...       | ...             | ...             |                   


### Links in Dynamic Networks

When time is associated with a link in a dynamic network (or temporal, or longitudinal network), there are two options what a link can mean:

* **Event**: An event represents an individual action or objets exchanged in the time attribute. For example, 
    * a letter or message send between two persons at a specific date,
    * a citation between two papers,
    * a transaction between two accounts. Link weight could represent the amount send.

* **Lasting relation**: Lasting relations are relationships that last over a longer period but, the link weight changes over time. For example
    * number of letters or messages send per week,
    * number of people migrating between countries per month,
    * number of citations per year,
    * value of money send regularly between accounts,
    * strength of signals between brain regions.

For visualization, the main difference is that each event is treated as a different link in the network, while a lasting relationship is treated as the same link with varying attributes. 

For example, when selecting a time-period, e.g. 1801-1806, event links will be shown as different links between nodes. The number of links between the same two nodes indicates the number of events, e.g. the number of letters send between the two nodes in the selected period. In contrast, if the links were lasting relationships, only one link will be shown between the nodes, showing the average weight during the selected time period.

To specify an event in your link table, you can stick to the above format. To specify a lasting relationship, you have to add **ID**s to your links. An ID (identifier) is a unique number identifying the same link. The following table shows an example with two lasting relationships (IDs 0 and 1) and the change of their respective weight (`Money ($k)`) over four years each.

| ID | Sender | Receiver | Money($k) | Year |  
|----|--------|----------|-----------|------|
| 0  | Anton  | Bob      | 100       | 1801 | 
| 0  | Anton  | Bob      | 100       | 1802 | 
| 0  | Anton  | Bob      | 30        | 1803 | 
| 0  | Anton  | Bob      | 10        | 1804 | 
| 1  | Anton  | Charles  | 10        | 1801 | 
| 1  | Anton  | Charles  | 20        | 1802 | 
| 1  | Anton  | Charles  | 30        | 1803 | 
| 1  | Anton  | Charles  | 100       | 1804 | 

The first four links are semantically the same relationship: money send between Anton and Bob (over several years). In the visualization, selecting the entire time period 1801-1804 will show 
* one link between `Anton` and `Bob` with the average `60` as link weight, and 
* one link between `Anton` and `Charles` with the average `40` as link weight.

Of course, you can create a network with multiple relationships by using one IDs per relationship. The following table shows two relationships between `Anton` and `Bob` and three relationships between `Anton` and `Charles`.

| ID | Sender | Receiver | Money($k) | Year |   
|----|--------|----------|-----------|------|
| 0  | Anton  | Bob      | 100       | 1801 | 
| 0  | Anton  | Bob      | 100       | 1802 | 
| 1  | Anton  | Bob      | 30        | 1803 | 
| 1  | Anton  | Bob      | 10        | 1804 | 
| 2  | Anton  | Charles  | 10        | 1801 | 
| 3  | Anton  | Charles  | 20        | 1802 | 
| 3  | Anton  | Charles  | 30        | 1803 | 
| 4  | Anton  | Charles  | 100       | 1804 | 


**Summary:** A single link table is sufficient to specify a network. Link tables contain one line per link, allowing to specify attributes on links as well as locations of the respective nodes at the time of the relationship. Some information in link tables are redundant, as in the example just above. While there are technically more sophisticated data and table formats, link tables are human readable and edible with common spread-sheet applications. 





## Node Tables

Node tables contain on line (row) per node in the network. Node tables can be used in two ways:

* **Specifying a network:** similar to link tables, a single node table can be used to create a network.
* **Complementing a link table:** while the link table contains links and their attributes, a node table can deliver nodes and their attributes to the same network.

### Node Tables for Network Creation

A common format used by historians are genealogies. The table below specifies a genealogy where each row contains the immediate family relationships of a person:

| CHILD|MOTHER|FATHER|GOD-FATHER|GOD-MOTHER|PLACE-OF-BIRTH|
| ---| ---| ---| ---| ---| ---| 
| Bob| 	Celine| 	Charles| 	Dave| 	Eve | 	Paris| 
| Ana| 	Fannie| 	Gerd	| Mike| 	Dianne| 	London| 
| Celine| Maria	| João| 	Pedro| 	Ana| 	Lisbon| 

This node table can be interpreted to contain **one column per link**. In other words, we want the network to contain one link between each node in the child column and each node in the associated columns: Mother, Father, God-father, God-mother. We could even create a node for each name in |the Place-of-birth field, if desired.

When using node tables as in the example above, the visualization interprets the column name (e.g, Mother) as link type and colors links differently.

In short, a node table used individually has the following template. Bold headers are required columns.

| NODE	| NODE TYPE	| RELATION_1	| RELATION_2	| RELATION_3	| …|
| --- | ---| ---  | --- | ---| ---|
| …	| …	| …	| …	| …	| …| 
| …	| …	| …	| …	| …	| …| 

* **Node:** the name of the node whose relations are specified in this row.
* **Node Type:** a node type if required.
* **Relation_1-Relation_n:** columns specifying the connections of the node in this column.


### Node Tables complementing Link Tables

Eventually, some networks may require both node and link tables:
* link tables to specify links and their attributes, and
* node tables to specify nodes and their attributes.

A node and a link tables are related through node names. I.e the node names in the node table **must match** the names of source and target nodes in the link table. The visualization looks up the names internally to create the network. The following two tables show a simple example of a social network where each node has a profession.

**Link table:**

| SENDER |	RECEIVER |
|---|---|
|Ana	| Charles|
|Charles |	Bob|
| …	| …|

**Node table:**

|NAME	| PROFESSION|
|---|---|
|Ana	| Lawyer|
|Bob	| Merchant|
|Charles	| Accountant|



## Location Tables

The Vistorian automatically creates location tables if you have specified any ‘source_locations’ or ‘target_locations’ in the link table. If these names are modern english names (e.g. ‘Kaliningrad’, ‘Rome’, etc.), our database will find the geo-coordinates. You need to be connected to the internet in order to retrieve coordinates.

If you are using places which are unlikely to be registered in any modern street atlas, you may want to provide Vistorian with the names and geo-coordinates you have. In this case, you can upload your own location table.

|USERNAME |	LONGITUDE |	LATITUDE|
|---|---|---|
|Atlantis |	13.4	| 45.2|

When you assign the location table in The Vistorian, you will see a fourth colum, called ‘geoname’. This is an internal value that you do not have to provide. It’s the modern name The Vistorian is looking for in the geoname database. It is separate from the ‘username’ so you can display your alternative name (e.g. ‘Koenigsberg’) instead of the modern and English name (‘Kaliningrad’).

If you find that any coordinates are wrong you can either:

* insert them by hand, directly in the Vistorian interface, or
* try a more specific ‘geoname’, e.g. ‘Brest, France’ instead of simply ‘Brest’ which might locate Brest in Belarus.

In both cases, if you find your location to be wrong (e.g. visualized on the map), you can either:
* try another or more specific ‘geoname’ (e.g. ‘Brest, France’), or
* insert the new coordinates in the table in the Vistorian interface.

## Finding the Right Format

Which tables you need and which information needs to go where depends on every specific case. There might also be may cases that are not currently supported by our visualizations, e.g. locations associated to links. In this case, please send us an email: benj.bach@gmail.com.

This section gives some brief guidelines to find the right tables and formatting.

* Your network is a genealogy: Use a single node table, with each column being a family relation
* Your network has no attributes to nodes and links: use a single link table
* Your network has only link attributes (link weight, link type, link time, source/target locations): use a single link table and specify each attribute in a column
* Your network has attributes on nodes (type): use both tables; a node table to specify node attributes and a link table to specify link attributes.

## Currently Work-In-Progress or Unsupported Scenarios

The following cases are currently under development. If you are interested in a particular case, please let us know and/or join the development team.

* Nodes with fixed locations (i.e. node location in node table)
* Link Directionality
* Multiple node types in node table

## Formatting Time

| INPUT | EXAMPLE | DESCRIPTION |
| ------| ------- | ------------- |
| YYYY | 2014 | 4 or 2 digit year|
|YY	|14	| 2 digit year|
|Y |	-25	 |Year with any number of digits and sign|
|Q |	1..4|	Quarter of year. Sets month to first month in quarter.|
|M MM	| 1..12	|Month number|
|MMM MMMM| 	Jan..December |	Month name in locale set by moment.locale()|
|D DD	|1..31	|Day of month|
|Do	| 1st..31st	|Day of month with ordinal|
|DDD DDDD |	1..365	|Day of year|
|X | 1410715640.579 | Unix timestamp|
|x | 1410715640579 | Unix ms timestamp|
