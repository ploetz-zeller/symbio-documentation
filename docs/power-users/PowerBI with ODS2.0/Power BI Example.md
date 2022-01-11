
#Report Example within Power BI

##Load Data
At first load data to a blank file.
1. Open Power BI Desktop. (The web application is not able to import data from a SQL Server.)
2. Select *Import data from SQL Server* to add data to your report.

![Data Source](media\Picture1.png)

Enter the Server name and the name of the Database. You can find this information in the email with your access data. At next select *DirectQuery* and click *OK*.
> **Connection Mode**
> *DirectQuery*: Creates a direct connection to the data base. The data is always up to date because it comes directly from the source and is not a copy. If the data in the original source is changing also the used data is changing.
> *Import*: Stores the data from the source to the Power BI file. The used data gets old because it's only a copy of the original data. This mode can be faster in performance, but is not recommended to be used for a report, also caused by the huge file size.

![Connect to SQL Server database](media\Picture2.png)

3. In the Navigator select all the tables you need to create your report and click on *Load*.
Only select the needed tables to keep your file clear.
If you put the name of the schema (for example *processes.*) into the search bar, only the tables of the regarding models are suggested. (Your access data send in the email contains the name of the SQL Schema.) There is the option to just check the main table (here: *DWH__Demo_released_processes.fact_Processes*) of a model and auto-select all related tables of this model by using the *Select Related Tables*-Button.

![Search for SQL Schema in Navigator](media\Picture3.png)

If the connection is created, you find all loaded tables in the section ```Fields``` on the right:

![Tables in Field Section](media\Picture4.png)








##Navigation in Power BI
On the right there are three areas with different kinds of tools to work with. These areas, which also can be hidden, are called sections in the following (```Filter```, ```Visualizations``` and ```Fields```): 

![Navigation: Sections](media\Picture5.png)

Beside that you will find two or three different panes in the ```Visualizations```-Section, on the left there is the ```Fields```-Pane, in the middle the ```Format```-Pane and on the right is the ```Analytics```-Pane, which is only displayed if any visualization is selected.

![Navigation: Panes](media\Picture6.png)






##Add Visualization
Now let's add a visualization to the report.
1. In the section ```Visualizations``` on the right you can choose between different kinds. If you hover over the icons, you can see the name of the diagrams in the tooltip.
To understand how Power BI works, let's start with a simple visualization, for example select *Table*.

![Add Visualization](media\Picture7.png)

Now a blank table is part of your report. At next populate it with data.

2. Select the new created table in the page on the left. And, on the right, change in the ```Visualizations```-Section to the ```Fields```-Pane. Whether you select the data from the ```Fields```-Section on the right or you drag the data fields and drop it to the *Values*.

![Add Data to Visualization](media\Picture8.png)

By drag and drop you can change the order of the fields. Depending on the chosen visualization there can be additional information where you need to add fields, for example for the legend.

3. Do it the same way for other visualizations.








##Filter Data
To show only particular and not all contained data, you can filter the data in the ```Filter```-Section. In the following example there are two versions of each process, one in English and one in German; the different languages are filtered based on the column CultureId.

> **Filter Area**
> You can apply the filter only on the current visualization, on the whole page or on all pages. If you filter by language it makes sense to filter on the whole page and not only for one visualization.

Drag the column you want to filter into the ```Filter```-Section and choose *Basic filtering* as *Filter type*.

![Filter Example](media\Picture21.png)

> **Filter types**
> *Basic filtering*: Select from available values.
> *Advanced filtering*: Filter with operators and individual values.








##Calculated Values
To display not only the values your tables provide you, but also calculated values, let’s create a measure with DAX.

>*Data Analysis Expressions (DAX) is a programming language that is used throughout Microsoft Power BI for creating calculated columns, measures, and custom tables. It is a collection of functions, operators, and constants that can be used in a formula, or expression, to calculate and return one or more values. You can use DAX to solve a number of calculations and data analysis problems, which can help you create new information from data that is already in your model.* [Detailed Tutorial](media\https://docs.microsoft.com/en-us/learn/modules/create-measures-dax-power-bi/)

1. At first select the data-table (in the ```Fields```-Section) the measure relates to.

![Selection of a Data Table](media\Picture13.png)

2. Click on *New Measure* in the ```Table Tools```-Tab on the top:

![Navigation: New Measure](media\Picture14.png)

3. An input appears on the top. Here you can name the measure and put in your DAX.
Select an expressive name, so you know what the measure is there for.

![Measure Creation](media\Picture15.png)

This example shows an easy calculation, that counts the number of processes by counting the rows of the process-table:

![Measure Example](media\Picture16.png)

After creating the measure it is visible in the ```Fields```-Section on the right:

![Find Measure in Fields-Section](media\Picture17.png)

4.  The measure field can be used the same way as the imported data fields. In this example we only want to display the calculated number of processes without a chart. Therefor choose the table-visualization and add the created measure in the ```Fields```-Pane as value:

![Usage of Measure](media\Picture18.png)

After formatting the column header, the table looks like this:

![Result of Measure Usage](media\Picture19.png)








##Format Visualization
Next let's format the visualizations to give the report an expressive look. There are nearly endless options to customize the look of visualizations. For an individual design you can change parameters as color, font or size. But some units as the title can also be hidden. In the following you'll find an overview of the most important formatting options.

1. In order to change the format of a visualization select it in the page on the left and change to the ```Format```-Pane in the ```Visualizations```-Section on the right.

![Navigation: Format Pane](media\Picture9.png)

> **Visualization Designs**
> General: You can change the position and add a description.
> Title: You can edit the style of the title, for example font color or alignment.
> Background: You can choose the background color and transparency.
> Border: You can add a border and edit its color and radius.
> Data Color: For charts you can select the color of the of the displayed data.
> Legend: For charts you can show or hide the legend and edit its style.
> Column Headers: You can design the column headers of a table, for example the colors of font and background.
> Grid: You can edit the grid of a table, for example you can change colors, text size or line weight.
> X/Y Axis: You can change for example the scale type, color, text size or category width of an axis.

2. In the first example let's add a title to the table and change its font color:  Expend the ```Title```-Card and change the slider from *off* to *on*. Here you can add a title and change its color or size:

![Example for Title Formatting](media\Picture10.png)

3. But there are also more interesting kinds of visualizations: If you’ve added a bar chart, you can edit for example the format of the legend or the axis in the ```Format```-Pane:

![Example for Axis Formatting](media\Picture11.png)

Which data is shown in the legend, you determine in the ```Fields```-Pane, for example there is shown the state of a process in this pie chart:

![Example for Legend Formatting](media\Picture12.png)








##Page Formatting
To complete the look of the report at last let’s change the formatting of the whole page.

1. If no visualization is selected, go to the ```Format```-Pane, and expand ```Page Background```. Here you can edit the color of the background. There is also the option to select a background picture.

![Formatting of Page Background](media\Picture20.png)

2. Go to the ```Insert```-Tab on the top in order to add elements as text boxes or pictures.

![Navigation: Insert-Tab](media\Picture22.png)

For example you can add a text box with a title or a logo of a company to the report:

![Example for Report with Title and Logo](media\Picture23.png)