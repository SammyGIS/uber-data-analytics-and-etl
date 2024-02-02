# Uber Data Analytics | Data Engineering on GCP & Mage.AI Project

## Project Overview
This project aims to conduct comprehensive data analytics on Uber data using a robust stack of tools and technologies, including Google Cloud Platform (GCP), Python, Compute Instance, Mage Data Pipeline Tool, BigQuery, and Looker Studio.

## Architecture 
The architecture is designed to seamlessly integrate components for efficient data processing. It involves data ingestion from TLC Trip Record Data into Google Storage, processing with Compute Instances and Mage Data Pipeline Tool, and final storage in BigQuery for further analytics. Looker Studio is then employed for interactive visualization.

## Architecture 
<img src="architecture.jpg">

## Tools Utilized
1. **Google Cloud Platform**
   - **Google Storage:** Efficiently stores and manages large datasets.
   - **Compute Instance:** Processes and transforms data for analysis.
   - **BigQuery:** A powerful data warehouse for storing and querying massive datasets.
   - **Looker Studio:** Enables interactive exploration and collaboration.

2. **Modern Data Pipeline Tool - Mage.AI**
   - Facilitates seamless data flow and transformation throughout the pipeline.

## Dataset
The TLC Trip Record Data, encompassing yellow and green taxi trip records, serves as the primary dataset. It includes vital information such as pick-up/drop-off details, locations, distances, fares, rate types, payment methods, and passenger counts.

- [NYC TLC Trip Record Data Website](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- [Data Dictionary](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf)

## Data Model
<img src="data_model.jpeg">


## Star Schema for Data Warehouse

In our data warehouse, we have designed a star schema to efficiently organize and query our raw datasets. The schema comprises a central fact table surrounded by dimension tables that provide contextual information.

### Dimension Tables:
* datetime_dim
This dimension table dissects pickup and drop-off times into finer components, making it easier for querying. It includes attributes such as day, hour, year, and more, enhancing the granularity of time-related analyses.

* passenger_count_dim
Capturing the total number of passengers per trip along with a unique identifier, this dimension table facilitates comprehensive analysis of passenger-related metrics.

* trip_distance_dim
Storing the distance covered in each trip along with the corresponding trip ID, this dimension table aids in understanding and analyzing trip distances within the dataset.

* rate_code_dim
This dimension table converts numerical rate codes into meaningful rates as per the data dictionary, providing a more interpretable representation for rate-related analyses.

* pickup_location_dim
Containing the latitude and longitude of the pickup locations along with unique IDs, this dimension table assists in spatial analysis and geographical insights related to the pickup points.

* dropoff_location_dim
Similar to the pickup location dimension, this table stores the latitude and longitude of drop-off locations, enhancing our ability to analyze and visualize drop-off patterns.

* payment_type_dim : This dimension table translates payment type codes into their corresponding meanings, as per the data dictionary, making payment-related analyses more interpretable.

#### Fact Table
In the process of augmenting our analytical capabilities, the integration of dimension tables with the central fact table has been orchestrated through a series of left join operations. The pivotal entity in this schema, the fact_table, encapsulates vital metrics such as amounts and listed prices corresponding to each recorded trip.

## References
The project is inspired by insights from external sources. Check out the [Video Link](https://youtu.be/WpQECq5Hx9g) for more details.

