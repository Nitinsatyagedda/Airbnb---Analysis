# Airbnb-Analysis
This is an open-source project repo which deals with extracting data from Airbnb dataset available in MongoDB Atlas as a sample dataset, pre-processing and loading it into a CSV file for visualization. EDA is done using Streamlit along with Plotly charts and Folium Geospatial Visualization. Also, an interactive dashboard is built using Power BI.

## Introduction
Airbnb, is an American San Francisco-based company operating an online marketplace for short-term and long-term homestays and experiences.  
The company acts as a broker and charges a commission from each booking.  
This project aims at Extracting, Cleaning, Performing the EDA, Visualizing it using Streamlit and Creating an interactive Power BI Dashboard. The dataset is available in the MongoDB Atlas as a Sample Dataset.  

## Table of Contents
1. Pre-requisites
2. Technology Stacks 
3. Usage
4. Data Extraction
5. Data Cleaning and Transformation
6. Visualization and Exploration
7. Dashboard Creation
8. Further Improvements  

## Pre-requsites
Install the following packages to run the project. 
```
pip install streamlit
pip install pandas
pip install folium
pip install streamlit_folium
pip install numpy
pip install Pillow
pip install plotly

```

## Technology Stack
- Python scripting 
- NoSQL - MongoDB Atlas
- Streamlit App development
- Data Pre-processing
- GeoSpatial Visualization
- Plotly
- PowerBI  

## Usage
Clone the repo from the below mentioned link.  
[Airbnb-Analysis](https://github.com/Chindhu-Alagappan/Airbnb-Analysis.git)   
Install packages from "requirement.txt"  
Run the streamlit application using `streamlit run .\Airbnb.py`  
View the portal in your [localhost](http://localhost:8501/)    

## Data Extraction 
- Login to the MongoDb Atlas portal  
- Choose "Browse Collections"  
- From the list of collections, select **sample_airbnb.listingsAndReviews**  
- Explore the dataset available  
- To access it from Python, Click the Overview -> Data Toolkit -> App Driver -> Under option 3, you will find the link to access  
- Copy and paste it to Airbnb - Preprocessing.ipynb  
**Note** : Replace your password with <password> in the access link.  

## Data Cleaning and Transformation
- Split the dataset into separate table, so that we can get a clear understanding.
- Handling null values, duplicates and converting the categorical to numerical values (whereever necessary) are performed.
- The following are the important dataframes created.

**DataFrame : airbnb_table**
| Column | Non-Null Count | Dtype |
| :---------- | :-------- | :---------- |
| _id | 5555 non-null | object |
| listing_url | 5555 non-null | object |
| name | 5555 non-null | object |
| summary | 5555 non-null | object |
| space | 5555 non-null | object |
| description | 5555 non-null | object |
| neighborhood_overview | 5555 non-null | object |
| notes | 5555 non-null | object |
| transit | 5555 non-null | object |
| access | 5555 non-null | object |
| interaction | 5555 non-null | object |
| house_rules | 5555 non-null | object |
| property_type | 5555 non-null | object |
| room_type | 5555 non-null | object |
| bed_type | 5555 non-null | object |
| minimum_nights | 5555 non-null | int64 |
| maximum_nights | 5555 non-null | int64 |
| cancellation_policy | 5555 non-null | object |
| accommodates | 5555 non-null | int64 |
| bedrooms | 5555 non-null | float64 |
| beds | 5555 non-null | float64 |
| number_of_reviews | 5555 non-null | int64 |
| bathrooms | 5555 non-null | float64 |
| amenities | 5555 non-null | float64 |
| price | 5555 non-null | float64 |
| security_deposit | 5555 non-null | float64 |
| cleaning_fee | 5555 non-null | float64 |
| extra_people | 5555 non-null | float64 |
| guests_included | 5555 non-null | float64 |

**DataFrame : host_table**
| Column | Non-Null Count | Dtype |
| :---------- | :-------- | :---------- |
| _id | 5555 non-null | object |
| host_about | 5555 non-null | object |
| host_has_profile_pic | 5555 non-null | int32 |
| host_id | 5555 non-null | object |
| host_identity_verified | 5555 non-null | int32 |
| host_is_superhost | 5555 non-null | int32 |
| host_listings_count | 5555 non-null | int64 |
| host_location | 5555 non-null | object |
| host_name | 5555 non-null | object |
| host_neighbourhood | 5555 non-null | object |
| host_picture_url | 5555 non-null | object |
| host_response_rate | 5555 non-null | float64 |
| host_response_time | 5555 non-null | object |
| host_thumbnail_url | 5555 non-null | object |
| host_total_listings_count | 5555 non-null | int64 |  
| host_url | 5555 non-null | object |
| host_verifications | 5555 non-null | object |

**DataFrame : address_table**
| Column | Non-Null Count | Dtype |
| :---------- | :-------- | :---------- |
| _id | 5555 non-null | object |
| country | 5555 non-null | object |
| country_code | 5555 non-null | object |
| government_area | 5555 non-null | object |
| market | 5555 non-null | object |
| street | 5555 non-null | object |
| suburb | 5555 non-null | object |
| latitude | 5555 non-null | float64 |
| longitude | 5555 non-null | float64 |

**DataFrame : availability_table**
| Column | Non-Null Count | Dtype |
| :---------- | :-------- | :---------- |
| _id | 5555 non-null | object |
| availability_30 | 5555 non-null | int64 |
| availability_60 | 5555 non-null | int64 |
| availability_90 | 5555 non-null | int64 |
| availability_365 | 5555 non-null | int64 |

**DataFrame : reviews_score_table**
| Column | Non-Null Count | Dtype |
| :---------- | :-------- | :---------- |
| _id | 5555 non-null | object |
| review_scores_accuracy | 5555 non-null | float64 |
| review_scores_checkin | 5555 non-null | float64 |
| review_scores_cleanliness | 5555 non-null | float64 |
| review_scores_communication | 5555 non-null | float64 |
| review_scores_location | 5555 non-null | float64 |
| review_scores_rating | 5555 non-null | float64 |
| review_scores_value | 5555 non-null | float64 |
| overall_rating | 5555 non-null | float64 |

## Visualization and Exploration
The Exploratory Data Analysis (EDA) is done using Streamlit Application with the help of the below mentioned packages.  
- Folium - GeoSpatial visualization package.  
- Plotly Charts / Plots - Building interactive charts and plots.
  
Some snippets from the portal are displayed below. <br><br>
Location Details :  <br><br>
![Location Details](https://github.com/Chindhu-Alagappan/Airbnb-Analysis/blob/1c1ea2d971d708ac6fba237c9f981822df861a74/Output%20Snapshots/Image_2.png)
<br>
<br>
<br>
Price Details :  <br><br>
![Price Details](https://github.com/Chindhu-Alagappan/Airbnb-Analysis/blob/1c1ea2d971d708ac6fba237c9f981822df861a74/Output%20Snapshots/Image_6.png)
<br>
<br>
<br>
Availability Details :  <br><br>
![Availability Details](https://github.com/Chindhu-Alagappan/Airbnb-Analysis/blob/1c1ea2d971d708ac6fba237c9f981822df861a74/Output%20Snapshots/Image_7.png)  

## Dashboard Creation
An interactive dashboard with 7+ reports are generated and filtered through a *Country* slicer in Power BI.  
View the dashboard using the link mentioned below.  
[Airbnb-Dashboard](https://github.com/Chindhu-Alagappan/Airbnb-Analysis/blob/1c1ea2d971d708ac6fba237c9f981822df861a74/Airbnb%20-%20Dashboard.png)

## Further Improvements  
The project can further be enhanced by building models to predict the hosts preferences based on seasons and availabilities. This will help us to better understand and recommend to the hosts accordingly.  
If you encounter any issues or have suggestions for improvements, feel free to reach out.  
  
Email : *nitinsatyagedda@gmail.com*  
LinkedIn : *https://www.linkedin.com/in/nitin-satya-gedda-aa9933260/*
  
Thanks for showing interest in this repository ! 
