# Tracing scientific mobility with folium map

Following script creates a geographic map of scientific mobility. It shows scientists going from host institute to guest institute for a given year.

# Preprocessing

IMPORTANT: The information about the various institutes of the scientists should be available. You should know geolocations (latitude and longitude) of the host and guest institutes. If not, use 'geopy-googlemaps-batchgeocoder' from github to generate geoinfo (latitude and longitude) (You need to purchase necessary Google API key). As described in the 'geopy-googlemaps-batchgeocoder' folder, you will need to create a csv input file with the names of the host and guest institutes, adressline and city. You will have to run batchcoder's python code twice, i.e. once for host institutes and once for guest institutes. When processing csv output file, first open the excel program and then import the data in the excel file with the import button. Convert the geodata to text before clicking the finish button. This is to get geodata in a proper format.

# Further processing

The data from csv output files of host and guest institute are bundled with information such as applicant, title, year, name of institution. An example excel file is provided with this repository, to match with the column names used in the script below. Alternatively you can change column names in the scripts to match with your excel. The output of the python code is a map in an html format.

# Script
Importing various modules required for analysis

  pandas
  
  folium
  
  os
  
  tkinter

Importing the scientific mobility example 'folium import file' with Tkinter module. You need to close the window after importing the file provided in the github repository.

Converting the datatypes to allow it to proces in folium

# Creation of folium map

import folium.plugins for Markercluster

generating a map

adding layers to map, default 'off' for cluster host universities

adding marker clusters to respective layers

adding markers to marker cluster for each source university

adding markers to marker cluster for each destination university

adding lines going from host institute to guest institutes

adding title to the map

saving the map in the folder where your current jupyter notebook is.

## User manual html file
You can view the number of scientists per region and per zoom level. The markers are colored based on quantity: more than 10 is color red yellow, 2 to 10 is color green. If you hover over the color red yellow markers, you can see the range. There are two layers of information: Host and guest institute info with the guest institute info default on. Zooming in further shows the numbers of scientists per region. Zooming in even further gives number of scientists per university. The last zoom lists each scientist by address with number 1 in the circle. If you hover over a circle, you get information about the scientist. You can see the specific research information when you click on it. The guest addresses are in red color and the host addresses are in blue color.
