# Chicago Gun Violence

## Methodology
This is a website with SQL database to analyse data related to gun crime in Chicago in 2015. The following paragraphs outline the methodology used in different steps of the research.

## Data Gathering
Two types of data are needed for this research: attribute data and vector data. To ensure reliability, data released by relevant official organizations has been collected. It must also be related to comparable years that influenced the gun crime incidents and be equivalent in scale to the boundary files.

The first attribute data is the records of all gun incidents in Chicago in 2015, collected and maintained by the Gun Violence Archive. The geographical coordinates of these incidents are provided for vector representation.

To explore what might influence these incidents, reports of the gun problem in Chicago and across the USA were reviewed. Demographic and socioeconomic data was obtained from the National Historical Geographic Information System (NHGIS) and mental health data collected in 2015 for the same geographies was obtained from the Centres for Disease Control & Prevention. All factors were taken from estimates for the Census Tracts for 2011-2015 through the American Community Survey.

The first type of vector data is polygon data in different scales, including Chicago city's boundary, communities' boundaries, and boundaries of census tracts. All these data are open and available at Chicago Data Portal.

## Data Cleaning and Database
MySQL software was used to create a database and import various tables into the available server (dev.spatialdatacapture.org). With MySQL scripts, tables were cleaned, amended, joined per Census Tracts, and grouped for the larger Community Areas. By cleaning the data, it is ready for the analysis process.

## Analysis
Two methods of analysis were conducted on the data related to gun shooting crime in Chicago: regression and cluster analysis.

Firstly, different factors were considered to find any relationship between the gun shooting incident rate in Chicago's communities and demographic and socioeconomic factors. Simple linear regression was used to find the said relationship. To confirm selection, variables with a high R value against the incident rate were chosen. The P-value was also considered to determine the likelihood of the slope between the two being zero.

Explanatory variables that were overly correlated with each other were removed from the analysis, leaving only 7 distinct variables.

To analyse if gun incidents were occurring at a higher rate in places of common characteristics, cluster analysis was used to further analyse the relationship between the variables and the incident rate. Incident rate was not used in the algorithm but analysed against the output. K-Means clustering algorithm was used to ensure all areas are assigned a cluster for comparison against gun incidents across the whole city.

## Server Side Components/API
Once the analysis is completed, a node.js program is set up to provide JSON files to return the desired data, through MySQL commands, for use on the website. Endpoints are created for boundary data as GeoJSONs, incident locations and characteristics, and explanatory variables for varying scales.

## Visualisation
The findings of this research have been presented by creating a website that presents information through different formats, namely maps, graphs, charts and text.

## Maps
Google Maps API is used to support our map tool, allowing customizability of functions through JavaScript and so compatibility with our JSON files. Our visualization presents all incidents as markers and colours areas according to observed values for visual inferences.

## Graphs and Charts
The graphs and charts related to data analysis and descriptive statistics have been utilised alongside the map. These charts and graphs are provided by Highcharts, which is a popular website providing interactive charts and graphs for websites.

Scatter plots with linear regression lines are used to show the relationship between gun crime incidents and other factors. Histogram charts are used
