# Cumulocity Smart Echart Widget Plugin [<img width="35" src="https://user-images.githubusercontent.com/32765455/211497905-561e9197-18b9-43d5-a023-071d3635f4eb.png"/>](https://github.com/SoftwareAG/cumulocity-smart-echart-widget-plugin/releases/download/1.0.0-beta/smart-echart-runtime-widget-1.0.0-beta.zip)

The Cumulocity IoT Smart Echart Widget Plugin is the Cumulocity module federation plugin created using c8ycli. This plugin can be used in Application Builder or Cockpit.
The Cumulocity IoT Smart Echart Widget Plugin helps you to display API and datahub response on a chart with color configurations.

### Please note that this plugin is in currently under BETA mode.

### Please choose Smart Echart Widget release based on Cumulocity/Application builder version:

|APPLICATION BUILDER | CUMULOCITY | SMART ECHART WIDGET PLUGIN  |
|--------------------|------------|-----------------------------|
| 2.0.x(coming soon) | >= 1016.x.x| 1.x.x                       |

![Picture1](https://user-images.githubusercontent.com/85675121/154234664-5840f68e-33b8-4e49-89fa-b9b854773c75.png)

## Features
  
*  **Charts Supported:** Line , Bar , Polar, Radar, Pie, along with Horizontal Orientation

*  **Supports Datahub:** Datahub can be chosen as a source and results from datahub can be configured with LIMIT option.

*  **Configurable Color:** Select custom color for your chart.

*  **Configurable Zoom:**  Select the zoom which is best fit for your chart.


## Installation

## Prerequisites:
   Cumulocity c8ycli >=1016.x.x

### Runtime Deployment?

* This widget support runtime deployment. Download [Runtime Binary](https://github.com/SoftwareAG/cumulocity-smart-echart-widget-plugin/releases/download/1.0.0-beta/smart-echart-runtime-widget-1.0.0-beta.zip) and install via Administrations(Beta mode) --> Ecosystems --> Applications --> Packages 

### Local Development?

**Requirements:**
* Git
* NodeJS (release builds are currently built with `v14.18.0`)
* NPM (Included with NodeJS)

**Instructions**
1. Clone the repository: 
```
git clone https://github.com/SoftwareAG/cumulocity-smart-echart-widget-plugin.git
```
2. Change directory: 
```
cd cumulocity-smart-echart-widget-plugin
```
3. Install the dependencies: 
```
npm install
```
4. (Optional) Local development server: 
```
npm start -- --shell cockpit
```
5. Build the app: 
```
npm run build
```
6. Deploy the app: 
```
npm run deploy
```


------------------------------

These tools are provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.
_____________________
For more information you can Ask a Question in the [TECH Community Forums](https://tech.forums.softwareag.com/tag/Cumulocity-IoT).
