<link rel="stylesheet" type="text/css" href="assets/styles/style.css">

# Getting Started

## Demo datasets to download:
* [Marie Boucher CSV File](https://drive.google.com/file/d/1Os_1D7xQEQHN_hujn8lf1qRVTwHTl8yV/view?usp=sharing)
* [les miserables CSV File](https://drive.google.com/file/d/11cSkZ9TYX7B1mq8gSIuKwEjahlEEmRH8/view?usp=sharing)

## Preparing data

The Vistorian can import three data formats:
- table format (CSV files)
- GEDCOM
- PAJEK
- GraphML (XML)

If you are unsure how to structure your data tables if you are using tables, please read this [guide](formattingdata). 

## Importing data

Data in the Vistorian is stored in your local storage. That means that at no time, the Vistorian is transmitting any of your data to our servers. You can delete your data through the Vistorian. 

To create a new network visualization, click the 'Create New Network' button when launching the Vistorian.
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/a878953b-0830-497b-9fe0-627cac263d74)

A form will come up asking you to 
1) chose an existing data set that you have uplaoded before, or
2) upload a new network.

### Name 
Enter a name for your network: 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/deb05120-b0d6-4821-a62d-aec606f86935)


### Format 

Chose the format your data is in. For this example, we chose `table' format since this requires most configuration. 

![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/15bed1a7-8d18-4d08-afc0-c8146eaf88b6)

### Link Table

We chose a file from our machine and upload it through the uplaod interface:
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/9f757ea4-70e0-4256-9811-9669c0fa1492)

Upon successful upload, the form shows the first few rows from your table. Tick the 'Has Header Row' tickbox to avoid the Vistorian interpreting the first row as data. 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/8df026c0-f201-40b0-a886-61fc9010aec9)

For each of the required fields, select a column from the drop-down menu. 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/af264cdb-4691-46ff-b5be-956a00afc3bd)

If you have temporal data, chose a column from your table and chose a time format. You can learn about time formats by clicking the `edit' button. 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/7d555624-757d-4dc5-9556-187cf4fb13a1)

The Vistorian asks you if you have an extra file recoring node types. The process for entering node data is the same as for links. You can add more fields for multiple node types. 

![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/1e58474a-f5be-46ed-be9e-79ded58ec68b)

## Summary

Vistorian will show you the network as a node and link table. The data in these tables is only the data you have entred through the form. It is the data the Vistorian visualizes. If you have not uploaded a node table, a node table is created with a row for each node. The overview let's you check how the Vistorian `sees' your data. 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/c6686c2c-df2e-4183-81c3-abc223f77d1c)

## Visualization

Clicking the `Next' button brings you to a screen where you can chose among a set of visualizations. Click any of these visualizations to show it. 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/c0889979-03dc-4908-a67c-3c9f47f0d378)

![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/ba05a9e6-1199-4cc1-b906-ca62abf66b4f)

## My Visualizations

You will see any visualization you have created for any data set in the `My Visualizations' menu: 
![image](https://github.com/vistorian/vistorian.github.io/assets/1230497/2c15da4c-e1ea-4e0b-9886-864f0df03d79)

Use this page to open any previous visualization. Clicking the 'Create Visualization' button brings you to the start of the upload for [above](#Importing_data).

