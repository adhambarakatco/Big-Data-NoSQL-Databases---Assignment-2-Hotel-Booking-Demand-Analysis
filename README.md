# Big Data & NoSQL Databases - Assignment 2: Hotel Booking Demand Analysis

## Overview

This project analyzes the *Hotel Booking Demand* dataset using Apache Spark to answer business questions and generate valuable insights. The dataset includes booking details for City Hotel and Resort Hotel, including information such as booking dates, length of stay, number of guests, pricing, and cancellation status. The aim is to preprocess the data, clean it, and perform various analytical tasks to answer specific business questions.

## Table of Contents
- [Project Description](#project-description)
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Preprocessing and Analysis](#preprocessing-and-analysis)
- [Business Queries and Results](#business-queries-and-results)
- [Bonus Tasks](#bonus-tasks)
- [How to Run](#how-to-run)
- [Evaluation Criteria](#evaluation-criteria)
- [Contact Information](#contact-information)

## Project Description

This project aims to perform comprehensive analysis on a hotel booking dataset using **Apache Spark**. The tasks include preprocessing, cleaning the data, deriving new columns, and answering business questions using both **SparkSQL** and **Spark DataFrame API**. The queries cover key business areas like cancellation rates, seasonal trends, room mismatches, and customer preferences.

### Business Questions:
1. Which countries have the highest cancellation rates?
2. What season has the highest cancellation rate for bookings with lead time > 100 days?
3. Which room types experience the highest mismatch with the assigned room type?
4. What distribution channel has the lowest cancellation rate and the highest average revenue per booking?
5. Which meal types are most common among bookings with more than 3 total guests?

### Bonus:
- Show the relationship between lead time and cancellation status using a visual chart (scatter or boxplot).

## Technologies Used

- **Apache Spark**: For data processing and querying.
- **SparkSQL**: For querying the data with SQL-like syntax.
- **Spark DataFrame API**: For handling data in DataFrame format.
- **Python**: For writing the Spark queries and data processing steps.
- **Jupyter Notebook**: For interactive development and testing of the solution.

## Dataset

The dataset used for this project is named `egphotelbookings.csv`, which contains detailed booking information from a City Hotel and a Resort Hotel. 

### Key Columns:
- `hotel`: The name of the hotel (either Renaissance Hotel or JW Marriott Hotel).
- `is_canceled`: Indicates if the booking was canceled (1 for canceled, 0 for not canceled).
- `lead_time`: The number of days from booking to arrival.
- `arrival_date_year`, `arrival_date_month`: The year and month of arrival.
- `stays_in_weekend_nights`, `stays_in_week_nights`: The number of weekend and weekday nights the guest stayed.
- `adults`, `babies`: The number of adults and babies in the booking.
- `meal`: Type of meal package.
- `country`: Country of origin of the guest.
- `distribution_channel`: The booking distribution channel (e.g., Travel Agents, Tour Operators).
- `reserved_room_type`, `assigned_room_type`: The room types reserved and assigned.

## Preprocessing and Analysis

### 1. Data Cleaning and Preprocessing:
- Loaded the dataset into a Spark DataFrame.
- Explored and cleaned the data by handling missing values and duplicates.
- Created new derived columns, such as:
  - **Total stay duration**: Sum of weekend and weekday nights.
  - **Season**: Based on the `arrival_date_month`.
  - **Total guests**: Sum of adults, children, and babies.

### 2. Queries and Analysis:
The following queries were implemented using both **SparkSQL** and **Spark DataFrame API**:

1. **Cancellation Rate by Country**:
   - Calculated the cancellation rate per country and identified the top five countries with the highest cancellation rates.

2. **Cancellation Rate by Season**:
   - Analyzed the cancellation rates by season (Winter, Spring, Summer, Fall) for bookings with a lead time > 100 days.

3. **Room Type Mismatch**:
   - Identified the room types where the reserved and assigned room types differed, indicating mismatches.

4. **Distribution Channel and Revenue**:
   - Computed the distribution channel with the lowest cancellation rate and its average revenue per booking.

5. **Meal Type and Total Guests**:
   - Identified the most common meal types for bookings with more than 3 total guests.

## Business Queries and Results

The project implements both SparkSQL and Spark DataFrame API to achieve the following results:

### 1. Cancellation Rates by Country:
Top countries with the highest cancellation rates are identified based on a comparison of the total bookings and cancellations.

### 2. Seasonal Cancellation Rates:
The season with the highest cancellation rate for bookings with a lead time of more than 100 days is determined.

### 3. Room Type Mismatch:
Analysis of the room type mismatch, where the reserved and assigned room types differ, is conducted.

### 4. Distribution Channel and Average Revenue:
The distribution channel with the lowest cancellation rate is identified, along with its average revenue per booking.

### 5. Meal Types for Larger Groups:
The most common meal types for bookings with more than 3 guests are found.

## Bonus Tasks

A chart (scatter or boxplot) is generated to show the relationship between the lead time and cancellation status. The trend is described in a sentence, highlighting key insights without using correlation functions.

## How to Run

To run the solution, follow these steps:

1. Ensure you have Apache Spark and Jupyter Notebook installed.
2. Clone this repository.
3. Upload the dataset `egphotelbookings.csv` into your working directory.
4. Open the provided Jupyter Notebook (`BigData_Ass_2_Solution.ipynb`).
5. Run each cell to process and analyze the data.
6. Review the results and visualizations in the notebook.
