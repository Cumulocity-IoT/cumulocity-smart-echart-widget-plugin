# Cumulocity Smart Echart Widget Plugin [<img width="35" src="https://user-images.githubusercontent.com/32765455/211497905-561e9197-18b9-43d5-a023-071d3635f4eb.png"/>](https://github.com/SoftwareAG/cumulocity-smart-echart-widget-plugin/releases/download/1.0.0/sag-ps-pkg-smart-echart-1.0.0.zip)

The Smart Echart Widget Plugin is the Cumulocity module federation plugin created using c8ycli. This plugin can be used in Application Builder or Cockpit.
The Smart Echart Widget Plugin helps you to display API and datahub response on a chart with color configurations.

### Please choose Smart Echart Widget release based on Cumulocity/Application builder version:

|APPLICATION BUILDER | CUMULOCITY | SMART ECHART WIDGET PLUGIN  |
|--------------------|------------|-----------------------------|
| 2.0.x              | >= 1016.x.x| 1.x.x                       |

![Picture1](https://user-images.githubusercontent.com/85675121/154234664-5840f68e-33b8-4e49-89fa-b9b854773c75.png)

## Features
  
*  **Charts Supported:** Line , Bar , Polar, Radar, Pie, along with Horizontal Orientation

*  **Supports Datahub:** Datahub can be chosen as a source and results from datahub can be configured with LIMIT option.

*  **Configurable Color:** Select custom color for your chart.

*  **Configurable Zoom:**  Select the zoom which is best fit for your chart.

## Prerequisite
   Cumulocity c8ycli >=1016.x.x
   
## Installation

### Runtime Widget Deployment?

* This widget support runtime deployment. Download [Runtime Binary](https://github.com/SoftwareAG/cumulocity-smart-echart-widget-plugin/releases/download/1.0.0/sag-ps-pkg-smart-echart-1.0.0.zip) and install via Administrations --> Ecosystems --> Applications --> Packages 

## QuickStart
  

This guide will teach you how to add widget in your existing or new dashboard.

  

1. Open you application from App Switcher

2. Add new dashboard or navigate to existing dashboard

3. Click `Add Widget`
  
4. Search for `Smart Echart`

5. Select `Target API or Datahub`

6. Fill Options required

7. Click `Save`

Congratulations! Smart Echart is configured.

## User Guide

-   **Target API:** User can select an API or Datahub or Microservice. 
- If API is selected, user needs to give API URL and the listname that would hold the response.Example response of API should be in format:
`
{
	"<listName>":[
	{
		<fieldname>:<value>,
		<fieldname>:<value>,
		<fieldname>:<value>,
	},
	{
		<fieldname>:<value>,
		<fieldname>:<value>,
		<fieldname>:<value>,
	}
	]
}`
- In UI, the API datasource config would look like 
![Datasource_API](https://user-images.githubusercontent.com/85675121/178733831-8cf0e257-1255-49e6-aaa6-a58969838cb0.PNG)

- If Datahub is selected, user needs to provide a relative URL and the SQL query to get data from Datahub. 
![Datasource_DataHub](https://user-images.githubusercontent.com/85675121/178725170-40fbcd1f-4279-4bea-8ac7-b6fd0a11de74.PNG)
- If Microservice is selected, user needs to provide a relative URL
![Datasource_Microservice](https://user-images.githubusercontent.com/85675121/178725293-958d3899-bb1f-4766-a2f9-96e7dc88ec53.PNG)


-   **Types Of Chart:** User can select a Chart Type and its Layout.Below is the detail of chart types available alongwith the options
  
Options Available in Chart Config :


**1. Chart Title** : This will be the title of chart on top-left.

**2. List Name** : Name of the response field which holds JSON object. For example: API response comes as output:{…..JSON…}.Then List Name = output.

**3. Data Source(API / Datahub)** :  Either API or Datahub.

    3.1. API : Provide the API url and listname.
    3.2. Datahub : Provide the Datahub Url and SQL query to access the data.If required add the limit to restrict the no. of records fetched.
    NOTE: Datahub should be on the same tenant and user must have permission to access datahub.
    3.3. Microservice : Provide the relative URL.



**4. Chart Type** : At present, we have Bar, Line, Radar, Polar, Pie and Scatter chart.

**5. Chart Layout** : This has diff values based on the Chart type selected by User.
            ```
NOTE : In Simple charts, X-Axis can be category or value type and Y-Axis can be value only whereas in Horizontal charts, Y-Axis can be category or value type and X-Axis can be value only.
            ```

    5.1 Line Chart : For Simple Line, Only single value in Y-Axis Dimension.For Stacked Line, Comma separated values in Y-Axis Dimension.
    5.2 Bar Chart : For Simple Bar, Only single value in Y-Axis Dimension.
    For Stacked Bar, Comma separated values in Y-Axis Dimension.For Simple Horizontal Bar, Only single value in X-Axis Dimension.For Stacked Horizontal Bar, Comma separated values in X-Axis Dimension.
    5.3 Pie Chart : It can be a simple pie chart or a rose pie chart.Some value of pie chart are:
		  PieSliceValue : The numerical axis
		  PieSliceName : Can be same as PieSliceValue or can be a category axis.
		  Pie Radius : Mandatory.Should be in <num> or <num>% or <num><num> or <num>%<num>% format.
		  Border radius : optional. Specifies the radius of pie slice.
		  Border width : optional. Specifies the width of pie slice.
    5.4 Scatter Chart : It can be simple scatter chart or horizontal scatter chart with category on Y-Axis.
		  Bubble Size : Mandatory.Specifies the size of scatter bubble.
	5.5 Polar Chart : It can be a Line polar or Bar Polar chart or Angle Axis or Radius Axis Polar chart.
		  Angle Axis and Radius axis is usually used when x axis is of category type like date,days etc.
		  PolarChartRadius : Mandatory. Should be in <num> or <num>% or <num><num> or <num>%<num>% format.
		NOTE: X axis dimension type can be either category or value.
	5.6 Radar Chart : Here the 
		  X Axis dimension : can be numerical or category.Example: Sales or Name.This basically plots the box of radar.
		  Radar Dimensions : are the numerical fields which are plotted inside the radar box.
		  Radar Chart Radius : Mandatory. Should be in <num> or <num>% or <num><num> or <num>%<num>% format.
	NOTE : Radius can be a double numbers or single.In double number first number specifies the inside circle and second specifies the ourside radius.
	If you specify radius in percentage then it will be with respect to viewport size of chart container.

**6. X-Axis Type** : This has three options :

    6.1 Value : For numerical axis. Example fields like productSales : 2000,3000,1290 etc. 
    6.2 Category : For categorized data. Example fields like: Date: ‘Mar-2021’,’Feb-2020’ etc.
    6.3 Time : For time axis where you want to show continuous time data.
    
   **7. X-Axis Dimension** : This should be the fieldname of value you want to show on chart. It should be exactly same as it is in response of API.
   
   **8. Y-Axis Type** : This has three options :

    8.1 Value : For numerical axis. Example fields like productSales : 2000,3000,1290 etc. 
    8.2 Category : For categorized data. Example fields like: Date: ‘Mar-2021’,’Feb-2020’ etc.
    8.3 Time : For time axis where you want to show continuous time data.
    
  **9. Y-Axis Dimension** : This should be the fieldname of value you want to show on chart. It should be exactly same as it is in response of API.
  
  **10. X-Axis Rotate Labels** : In case the labels for x axis are lengthy , you can specify an input from -90 to 90.
  
  **11. Y-Axis Rotate Labels** : In case the labels for y axis are lengthy , you can specify an input from -90 to 90.
  
  **12. Legend** : User can select the shape of legend from here.
  
  **13. Slider Zoom** : This is like pinch zoom we have in phones. User can zoom in to see large datasets in detail.
  
  **14. Box Zoom** : This is available in top-right corner if selected. User has to select the zoom button and it would be highlighted in blue color and then user can make the selection on chart and that area will be zoomed in. To go back to previous stage user needs to click on ‘Zoom Reset’ Button(available in top-right corner).
  
  **15. Chart Color** : You can specify color in input box or you can use color picker.

------------------------------

## **Aggregation Utility**

Widget also provides aggregation functions as below:

**Dimension**: Specify the numerical dimension name.

**Method** : Select one of the method from dropdown.

**Group By** : Specify the category dimension.
 ```
Example: If you are creating a simple line chart with x-axis dimesion as ‘Date’ and y-axis dimension as ‘score’.To see the average score , In Aggregate you would Specify dimension as ‘score’ with method as ‘average’ and group by as ‘Date’.

In case of multiple numerical axis, you need to give all the axis in aggregate to be able to map those on chart.
``` 



------------------------------

This widget is provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
_____________________
For more information you can Ask a Question in the [TECH Community Forums](https://tech.forums.softwareag.com/tag/Cumulocity-IoT).
