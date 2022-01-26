# Gauge Custom Visualization

![gauge-chart](./images/gauge-chart.jfif)

## Gauge chart for MicroStrategy Dossier
You can easily create gauge chart using metrics and format it as you want. 
This visualization is free to use. 
If you found an issue with the widget , please comment on this page. 

## Basic Usage
Just drag 1 metric to Value then it will show you gauge chart.

It also supports 4 metrics ,
Value will show gauge point and progress,
Target will show target point ,
Min and Max value for setting start and end point of gauge .

Please refer attached mstr file ( This sample dossier is built in 2021 update 2 environment. Please open it with latest Workstation )

![gauge-style-and-format](./images/gauge-style-and-format.jfif)

## Gauge Style and format 
It supports several options for various gauge style

## Predefined Styles
![gauge-predefined-style](./images/gauge-predefined-style.jfif)
![gauge-sample](./images/gauge-sample.jfif)

## Format options

### Minimum and Maximum
You can set default value of min and max in format tab.

![gauge-min-max](./images/gauge-min-max.jfif)

**Start Angle and End Angle** : Decide where to start and end drawing gauge. 
0 degree or 360 degree of gauge is right side and add degrees to anti-clockwise direction.

![gauge-angle](./images/gauge-angle.jfif)

For example, start angle :180 and end angle : 0 will show half gauge.

### Size and Margin
Margin will move gauge **center point** vertically or horizontally. Gauge size will shrink or magnify the gauge. This is  percentage value to widget size.

![gauge-margin](./images/gauge-margin.jfif)

This option is useful when your gauge has small portion of circle like below picture .
It just draws gauge from 90 degree to 0 degree and a lot of space is empty.

![gauge-set-margin](./images/gauge-set-margin.jfif)

You can move center by setting margin % 

![gauge-set-margin-2](./images/gauge-set-margin-2.jfif)

Above setting will move center 20% left and 75% from top and magnify gauge 120% from original size. 
Default gauge center is 50% left and 50% from top and radius is 100%.

You can move metric value and name by setting margin of the font in Gauge font and Position tab.  Same rule will be applied. 

![gauge-set-margin-3](./images/gauge-set-margin-3.jfif)

### Gauge Threshold
In Gauge detail tab, You can enable threshold color by percent of gauge min max. 
If you want to set color of bottom 20% is blue and top 20% is red, set threshold like below.

![gauge-threshold](./images/gauge-threshold.jfif)

There is known issue that if you type into value in the threshold field, threshold is sometimes missing depends on the value is overlapped other threshold. When this happen, reset other values will resolve the issue.

## Object requirements: 
- At least 1 Metrics 
- Minimum MicroStrategy version: 2020
- Current visualization version: 1.0

## Publisher: DongHyub Lee   ( Sales Engineer in  MicroStrategy Korea) 

## MicroStrategy Features
- Supports custom properties
- PDF Export 

## Installation instructions
- To install this visualization, download the .zip file below and deploy it in MicroStrategy Workstation or MicroStrategy Web.
- After you have installed the visualization, you can open a working demo of this visualization by uploading the .mstr file below and doing the following:
  - To open the demo visualization in MicroStrategy Desktop or Workstation, double click the .mstr file.
  - To open the demo visualization in MicroStrategy Web, choose Create -> Upload MicroStrategy File -> View Dashboard

## Visualization Disclaimer
By downloading or using this visualization, you accept and acknowledge these terms.
This visualization is both intended as sample code and provided as a convenience to MicroStrategy users. MicroStrategy cannot guarantee that the code provided will apply to any MicroStrategy releases and clients outside of the versions stated within this article. This sample is supported by MicroStrategy Technical Support up to and including the basic visualization functionality listed in this article. Defects will be triaged by the MicroStrategy team as they are raised. For users with active MicroStrategy Technical Support contracts, contact MicroStrategy Technical Support to raise these defects.

## Open Source
eCharts (https://echarts.apache.org/en/index.html) library is included in the widget code

Published: Aug 17, 2021
Last updated: Aug 17, 2021

## Download attachments
- [EChartGauge.zip](https://github.com/PrezSeah/galleryres/raw/main/Microstrategy/gauge-custom-visualization/attachments/EChartGauge.zip)
- [EChartGauge.mstr](https://github.com/PrezSeah/galleryres/raw/main/Microstrategy/gauge-custom-visualization/attachments/eChart-Gauge-Sample.mstr)
