# Us-accident-analytics-dashboard
**ABSTRACT**

Road safety is a priority for everyone who owns a vehicle. With this project, we are going to analyse the US road accidents from February 2016 to March 2023 to understand the car accident hotspot locations, road accidents involved in different population densities and much more. Here we have a dataset which was retrieved in real-time using multiple traffic APIs. A dashboard was created on Looker Studio to visualize the same (https://lookerstudio.google.com/reporting/11838b21-1d09-4c69-85ac-c5c485606c23/page/F6kgD).


**DATA COLLECTION**

The dataset was extracted in the CSV format from Kaggle (US Accidents (2016 - 2023) (kaggle.com)). This is a nationwide geospatial dataset of vehicle accidents that covers data from 49 US states. Multiple APIs that provide streaming traffic incident (or event) data were used to collect accident data between February 2016 and March 2023. The data for this traffic information transmitting APIs has been collected by different organizations, such as state and federal transportation bureaus, law enforcement, traffic cameras, and traffic sensors installed on road networks. Approximately 7.7 million accident records are now present in the dataset. Additional datasets were retrieved from US open data sources for further analysis (https://hub.arcgis.com/search?collection=Dataset). All the datasets were transferred into GCS bucket.
![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/8d674ed8-328b-4e31-8841-40937ff4a00c)

 

The data from GCS bucket was fed to Big Query to perform data cleaning and data analysis. Different tables were created for different datasets and multiple views were created for data visualization.
 
![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/88daca68-6eaa-478b-a4eb-bdcb9752213c)



**DATA VISUALIZATION**

To visualize the geospatial data, Looker Studio was used. A dashboard was created to view the insights from the data. Design Intent and Data Insight for each page are as follows: - 

 ![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/8c7c5407-1146-4040-927d-391bbc4238a3)


Design Intent: Two maps were considered to visualize different datasets. On the left side, accident hotspot locations were plotted and, on the right, population densities for different regions were mapped. Bubble plot was used to represent the count of accidents on an individual location. Heatmap was utilized to view different population densities across USA. A state control was added to filter the data.

Data Insights: Although, Washington has a high population density, the number of accidents occurring is less as compared to other parts of USA.  


 ![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/fb292d79-2d64-4033-99c9-6b054a8f689a)


Design Intent: Two maps and a bar chart were considered to visualize different objectives. On the left side, accident hotspot locations were plotted and, on the right, number of beds in each hospital are mapped. Bubble plots were used to represent the count of accidents on an individual location and the number of beds in each hospital. A column chart was used to represent the average distance of the nearest hospital from the accident hotspot locations within a state (Initially, Euclidean distance was calculated between an accident location and the location of all the hospitals within a state. Minimum value from this list gave the nearest hospital location for that specific accident location. Similarly, nearest hospital locations were found for all the accident locations. Later, all the distances between nearest hospital from the accidents within a state were averaged to find the average distance of the nearest hospital from the accident hotspot location within a state). A state control was added to filter the data.

Data Insights: There’s a uniform distribution of medical facilities across the United States. The average distance of nearest hospital in Wyoming is way higher than the other states. More medical facilities are required for the states having average distance more than 10 kms.


 ![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/185bfe76-928d-44b9-bae0-0044bf700713)


Design Intent: Two maps and a bar chart were considered to visualize different objectives. On the left side, accident hotspot locations were plotted and, on the right, locations of fire station are mapped. Bubble plot was used to represent the count of accidents on an individual location. Heatmap was utilized to plot the location of fire stations across USA. A column chart was used to represent the average distance of the nearest fire station from the accident hotspot locations within a state (Initially, Euclidean distance was calculated between an accident location and the location of all the fire stations within a state. Minimum value from this list gave the nearest fire station location for that specific accident location. Similarly, nearest fire station locations were found for all the accident locations. Later, all the distances between nearest fire station from the accidents within a state were averaged to find the average distance of the nearest fire station from the accident hotspot location within a state). A state control was added to filter the data.

Data Insights: There’s a uniform distribution of law enforcement stations across the United States. The average distance of nearest fire department in Wyoming is way higher than the other states. More fire department infrastructure is required for the states having average distance more than 5 kms.

![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/f599c0e1-b1ac-4bad-8bfd-f6474c129796)

 

Design Intent: Two maps and a bar chart were considered to visualize different objectives. On the left side, accident hotspot locations were plotted and, on the right, locations of law enforcement station are mapped. Bubble plot was used to represent the count of accidents on an individual location. Heatmap was utilized to plot the location of law enforcement stations across USA. A column chart was used to represent the average distance of the nearest law enforcement station from the accident hotspot locations within a state (Initially, Euclidean distance was calculated between an accident location and the location of all the law enforcement stations within a state. Minimum value from this list gave the nearest law enforcement station location for that specific accident location. Similarly, nearest law enforcement station locations were found for all the accident locations. Later, all the distances between nearest law enforcement station from the accidents within a state were averaged to find the average distance of the nearest law enforcement station from the accident hotspot location within a state). A state control was added to filter the data.

Data Insights: There’s a uniform distribution of law enforcement stations across the United States. The average distance of nearest law enforcement station location in Wyoming is way higher than the other states. More law enforcement infrastructure is required for the states having average distance more than 10 kms.


![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/535e3d2a-46ac-418a-9f9f-1426c7b15c62)

 

Design Intent: A tree map, bar chart and a geo map were considered to visualize different objectives. Geo bubble map was leveraged to plot the average severity and the count of accidents for each of the accident hotspot locations. The size of the bubble inside the geo map represents the count of accidents for each accident location and the colour of the bubble portrays the average severity for each accidental location. Tree map was utilized to plot the count of accidents across different severities. A bar chart was used to represent the number of accidents within a state. State and date range controls were added to filter the data.

Data Insights: Although, the severity of accidents occurring in California are not high, there’s huge a spike in number of accidents. Poor infrastructure or negligence of traffic laws could be one reason for such a spike. Locations highlighted in red should be focused more as they represent locations with severe accidents. Fatal accidents can be reduced by increasing safety measures on these high severity accidental locations.

![image](https://github.com/diljyotsingh019/Us-accident-analytics-dashboard/assets/34520429/c39b5513-c00b-4fdc-a732-5b1301a1d4ad)

 

Design Intent: Two-line graphs and a column chart were considered to visualize different objectives. First line graph represents the count of accidents in an hour during the day. The second line graph portrays number of accidents during that month. Column chart was leveraged to plot the count of accidents for the day of the week. State and date range controls were added to filter the data.

Data Insights: There’s a huge spike in the count of accidents at 7am and 5pm. These two timings represent the rush hour of the day, which states that as the rush hour arrives the number of accidents increases as well. As seen from the column chart, the count of accidents is almost doubled during the weekdays. One possible explanation for the same could be the accidents occurring during rush hour. Also, the number of accidents occurring during the winter season is 1.5 times that of the number of accidents occurring in the summer season.


**REFERENCES FOR THE DATASET**

•	Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, and Rajiv Ramnath. “A Countrywide Traffic Accident Dataset.”, 2019. 

•	Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, Radu Teodorescu, and Rajiv Ramnath. "Accident Risk Prediction based on Heterogeneous Sparse Data: New Dataset and Insights." In proceedings of the 27th ACM SIGSPATIAL International Conference on Advances in Geographic Information Systems, ACM, 2019. 


