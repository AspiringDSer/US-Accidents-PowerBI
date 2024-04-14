# US Accidents - PowerBI Report 

# Table of Content <a id="top"></a>

1. [Project Overview](#Project-Overview)
2. [Data Sources](#Data-Sources)
3. [Data Model](#Data-Model)
4. [Report Structure](#Report-Structure)
5. [Challenges and Solutions](#Challenges-and-Solutions)
6. [Visual Samples](#Visual-Samples)
7. [Future Developments](#Future-Developments)

<a name='Project-Overview'></a>
# Project Overview
[Go to TOC](#top)

| Skills Demonstrated |                             |        |
| ------------------- | --------------------------- | ------ |
| PowerBI             | Data Modeling (Star Schema) | Python |
| DAX                 | Power Query                 |        |

I have developed a comprehensive Power BI dashboard for the US Accidents Dataset (2016-2023), offering a meaningful and interactive exploration of the data. Users can leverage the dashboard to gain valuable insights, make informed decisions, and construct compelling data-driven narratives.

Please feel free to reach out to me at jzqmah@gmail.com or message me on LinkedIn if you would like to access the Power BI (.pbix) file or request a live walkthrough. Please note that GitHub has a file size limit of 100 MB.

**Key Features:**

- **Interactive Analysis:** Users can slice and dice the data to uncover trends, patterns, and correlations, enhancing their understanding of accident dynamics.
- **Dynamic DAX Measures:** Leveraging DAX, I have created a set of dynamic measures that adapt to the context of the data, providing users with powerful analytical capabilities.
- **Real-world Applications:** The dashboard can be used for various applications, such as identifying car accident hotspot locations and studying the impact of precipitation or other environmental factors on accident occurrence.

![US Accidents - Pic 1](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/5be5febe-bf37-4134-a417-5acba9c5250e)
![US Accidents - Pic 2](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/3c154c3f-4335-4a27-9ead-a5eb868f8330)
![US Accidents - Pic 3](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/0c963226-f775-48f4-9a5e-11f0730c0666)

<a name='Data-Sources'></a>
# Data Sources
[Go to TOC](#top)

The project's visualizations and analyses are based on [US Accidents (2016-2023) Kaggle Dataset](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents). 
This is a countrywide car accident dataset that covers **49 states of the USA**. The accident data were collected from **February 2016 to March 2023**, using multiple APIs that provide streaming traffic incident (or event) data. These APIs broadcast traffic data captured by various entities, including the US and state departments of transportation, law enforcement agencies, traffic cameras, and traffic sensors within the road networks. The dataset currently contains approximately **7.7 million** accident records. For more information about this dataset, please visit [here](https://smoosavi.org/datasets/us_accidents).

**Data Processing:**

- **Source Data:** The dataset originates from Kaggle dataset in CSV format. 
- **Preprocessing:** I utilized Python (Pandas and Numpy Libraries) and Jupyter Notebook to preprocess the data, creating dimensional and fact tables using a star schema approach.
- **Integration with Power BI:** The processed tables were seamlessly integrated into Power BI, enabling the creation of insightful visualizations and analyses.

<a name='Data-Model'></a>
# Data Model
[Go to TOC](#top)

![datamodel](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/a65b3f39-85cc-45f4-b78e-060be331de10)

The project utilized **Dimensional Data Modeling** to structure the US Accidents dataset, employing the **star schema** to construct both Fact and Dimension Tables. This approach allows for efficient data storage and retrieval, enabling users to analyze the data from different perspectives easily.

I opted to demonstrate my data modeling skills using Python, deviating from the typical approach of using Power BI's Power Query. This decision was made to showcase my proficiency in Python and to highlight the flexibility and versatility of Python for data modeling tasks. Additionally,, its best practice to perform data transformation upstream, before integrating the data into Power BI.

In future developments, I plan to enhance the project by creating a cloud-based data warehouse solution and deploying the dataset into the solution using Dimensional Data Modeling principles. This will further optimize data storage and management, as well as facilitate scalability and accessibility.

For a detailed exploration of the data modeling process, please refer to `Data Modeling for US Accident Dataset.ipynb`.

| CSV File          | Table Description                                                                                                                                                                         |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FactAccidents.csv | This table contains facts and events related to dataset, such as accident details and severity.                                                                                           |
| DimLocation.csv   | This table contains dimensional attributes related to accident locations, such as geographical information (e.g., latitude, longitude), city, state, and other location-specific details. |
| DimWeather.csv    | This table contains dimensional attributes related to weather conditions, such as temperature, precipitation, visibility, and other weather-related metrics.                              |
| DimBinaryFlag.csv | This table contains dimensional attributes that are binary flags or indicators, such as whether certain conditions were present or absent during accidents.                               |
| DimTimeofDay.csv  | This table contains dimensional attributes related to the time of day when accidents occurred, such as morning, afternoon, evening, or night.                                             |
| DimDate.csv       | This table  contains dimensional attributes related to dates, such as day of the week, month, year, and other date-related details.                                                       |

| Dimension Table | Surrogate Key (PK) | Fact Table - Foreign Key (FK) |
| --------------- | ------------------ | ----------------------------- |
| DimLocation     | location_id        | location_id                   |
| DimWeather      | weather_id         | weather_id                    |
| DimBinaryFlag   | binary_id          | binary_id                     |
| DimTimeofDay    | time_of_day_id     | time_of_day_id                |
| DimDate         | Date (PK)          | Date                          |

<a name='Report-Structure'></a>
# Report Structure
[Go to TOC](#top)

The Power BI report is structured to provide users with interactive and insightful analysis of the US Accidents dataset. It allows navigation between three main reports, each focusing on different aspects of the data:

1. **Location Analysis:** This report provides insights into accident patterns based on location. Users can analyze accident frequencies, severity, and trends across different cities and states.

2. **Time Analysis:** This report focuses on analyzing various temporal aspects of road accidents. Users can explore how accident rates vary by time of day, duration of accident, and day of the week.

3. **Road & Weather Analysis:** This report examines the impact of road and weather conditions on accident occurrence. Users can analyze how factors such as precipitation, visibility, and road surface conditions correlate with accidents.

**Key Features:**

- **Slicers:** Each report includes three main slicers for filtering the data: Year, City, and State. These slicers allow users to focus on specific time periods, locations, and regions of interest.

**Interactive Visualizations:** The reports include a variety of interactive visualizations such as:

- **Maps:** Visualize accident locations and density.
- **Charts:** Display accident trends, severity, and other key metrics.
- **Tables:** Provide detailed accident data for further analysis.

**Cross-Report Drillthrough:** Users can drill through from one report to another to explore related data and gain deeper insights into the dataset.

**Future Enhancements:** In future developments, I plan to enhance the report with additional visualizations, such as trend analysis charts, and further improve the user experience with more interactive elements and storytelling features.

<a name='Challenges-and-Solutions'></a>
# Challenges and Solutions

[Go to TOC](#top)

![US Accidents - Pic 4](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/0d348879-c902-450d-9457-9590b492d8a6)

One of the most challenging tasks in the project was visualizing the percentage of total accidents on a chart. The solution involved creating a complex DAX measure with nested loops to ensure the measure adapted correctly to changes in slicer selection.

The main considerations were:

1. Ensuring the correct formula to calculate the percentage of total accidents, which was relatively straightforward.
2. Ensuring the DAX measure adapted accordingly to changes in slicer selection, which proved to be the more difficult part.

To address this, I implemented a nested loop inside the DAX measure to account for different slicer selections, such as Year, City, and State. This allowed the measure to dynamically calculate the percentage of total accidents based on the selected slicers.

The implementation of the nested loop required careful planning and testing to ensure it handled all possible slicer combinations accurately. By breaking down the problem into smaller, manageable parts and leveraging the flexibility of DAX, I was able to create a solution that provided the desired functionality and adaptability.

The following is the DAX measure used for calculating the percentage of total accidents:

![US Accidents - Pic 5](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/d5b5515e-de2d-4bff-96be-e5dd2ff1e68e)

<a name='Visual-Samples'></a>
# Visual Samples
[Go to TOC](#top)

**Power BI Features**
The following screenshots showcase some of the unique features found in Power BI report.

![US Accidents - Pic 6](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/214d353f-15bd-4479-af8d-ca3ec653f29e)

This card visual is designed to show the percentage change in a selected year compared to the previous year. When a specific year is chosen, the card displays both the percentage change and whether it is a positive or negative difference compared to the previous year. This feature provides users with a clear and concise way to understand the year-over-year changes in the data, facilitating quick insights into trends and patterns.

![US Accidents - Pic 7](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/9705273a-1eaa-4b32-ae24-075279890e9f)

This chart contains a feature that highlights the bar with the highest value in green and the lowest value in pink. This color differentiation helps viewers quickly identify these significant data points, adding clarity to the presentation. Each bar also represents the percentage of total accident cases, providing additional context for the data.

![US Accidents - Pic 8](https://github.com/AspiringDSer/US-Accidents-PowerBI/assets/79289892/42157183-085e-46db-a7a5-bc4d5d5344a0)

This interactive chart features dynamic parameters that allow users to customize the Y-axis variable, providing flexibility in exploring the data.

<a name='Future-Developments'></a>
# Future Developments
[Go to TOC](#top)

In future developments, I plan to enhance the reports with additional visualizations and analytical features to provide more comprehensive insights into the US Accidents dataset. Specifically, I aim to:

1. **ETL/ELT Pipeline:** Implement an ETL/ELT pipeline to store the dataset in AWS S3 and load it into a cloud-based data warehouse solution. This will improve data management and accessibility, enabling more efficient data processing and analysis.
    
2. **Data Modeling:** Construct a more robust data model in the cloud-based data warehouse solution, following Dimensional Data Modeling principles. This will optimize data storage and querying, facilitating more complex and insightful analyses.
    
3. **Additional Dimension Table:** Add an additional dimension table to provide insights regarding Time of Day. This will allow for more granular analysis of accident patterns based on the time of day, enabling users to identify trends and correlations.
    
4. **Advanced Map Analysis:** Implement a more advanced map analysis using Python Plotly. This will enhance the geographical visualization of accident data, providing more detailed and interactive maps for users to explore.
    
5. **Severity Prediction:** Utilize machine learning techniques, such as Random Forest, Decision Trees, Logistic Regression, K-Nearest Neighbors, etc., to predict accident severity. This predictive analysis will enable stakeholders to proactively identify high-risk areas and implement targeted safety measures.
    
6. **User Experience Improvements:** Further improve the user experience with more interactive elements and storytelling features. This will enhance the usability of the reports, making it easier for users to explore and understand the data.

By implementing these enhancements, I aim to provide a more comprehensive and valuable analytical tool for studying road accidents, enabling stakeholders to make informed decisions and improve road safety measures.
