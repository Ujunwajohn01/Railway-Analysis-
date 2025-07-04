# Railway-Analysis-
A Power BI Data Analytics Project by Obianujunwa John that analyzes real-world railway ticket sales.

### Table of Contents
- Project Overview
- Project Scope
- Business Objectives
- Expected Outcome
- Use Case
- Skills Demoonstrated
- Data Source
- Data Dictionary
- Data Connection
- Data Profiling 
- Data Cleaning and Preparation
- Key KPIs
- Key Analysis & Insights
- Recommendations
- Conclusion
- Contact

### Project Overview
This Power BI project analyzes railway ticket sales, passenger journey statuses, station performance, and time-based travel patterns using transactional data. The objective is to uncover performance trends across key train stations in the UK, optimize peak time planning, and understand how ticket types and station routes contribute to revenue.

### Project Scope
The project covers train tickets sales from December 8, 2023 to April 30, 2024 using a dataset containing:

- Train ticket sales and prices
- Journey time and status
- Ticket type distribution
- Route popularity
- Station-specific revenue performance

### Business Objectives
- Identify top revenue-generating routes and stations
- Evaluate revenue contributions by ticket types and classes
- Analyze journey punctuality and customer refund behavior
- Discover monthly and hourly travel patterns
- Provide strategic recommendations for operations and marketing

### Expected Outcomes

The analysis delivers a data-driven snapshot of the railway system's financial and operational performance. It enables route optimization, improves ticketing strategies, and enhances customer service through interactive dashboards and clear KPIs.

### Use Case
Stakeholders who can benefit from this analysis include:

**1. Operations Managers:** Optimize station efficiency and staffing based on travel peaks and refund patterns.

**2. Revenue Analysts:** Identify which ticket types and stations contribute most to revenue.

**3. Customer Service Teams:** Understand where journey delays and cancellations are happening to better serve customers.

**4. Marketing Teams:** Design targeted promotions for low-revenue periods or underused routes.

### Skills Demonstrated
- Data Analysis
- Data Cleaning and Transformation in Power Query
- Power BI Data Modeling
- Data Cleaning and Transformation
- DAX Calculations
- Data Visualization
- KPI Reporting

### Data Source
**Source:** [Maven Analytics](https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=uk%20tra) dataset consisting of Mock train ticket data for National Rail in the UK, including details on the type of ticket, the date & time for each journey, the departure & arrival stations, the ticket price, and more.
**File:** railway.csv
**Type:** Flat file (CSV)
**Tools Used:** Power BI
**Rows:** 31,653
**Columns:** Transatcion ID, Date of Purchase, Time of Purchase, Purchase Type, Purchase Method, Railcard, Ticket Type, Ticket Class, Price, Departure Station, Arrival Station, Date of Journey, Departure Time, Arrival Time, Journey Status, Reason for Delay, Refund Request
**Created Column:** Month Name, Month No, Route, Departure Hour(12), Departure Hour(24)

### Data Dictionary
- **Transaction ID:** Unique identifier for an individual train ticket purchase.
- **Date of Purchase:** Date the ticket was purchased.
- **Time of Purchase:** Time the ticket was purchased.
- **Purchase Type:** Whether the ticket was purchased online or directly at a train station.
- **Payment Method:** Payment method used to purchase the ticket (Contactles Credit Card or Debit Card)
- **Railcard:** Whether the passenger is a National Railcard holder (Adult Senior or Disabled) or not (None). Railcard holders get 1/3 off their ticket purchases.
- **Ticket Class:** Seat class for the ticket (Standard or First).
- **Ticket Type:** When you bought or can use the ticket. Advance tickets are 1/2 off and must be purchased at least a day prior to departure. Off-Peak tickets are 1/4 off and must be used outside of peak hours (weekdays between 6-8am and 4-6pm). Anytime tickets are full price and can be bought and used at any time during the day.
- **Price:** Final cost of the ticket
- **Departure Station:** Station to board the train.

### Data Connection
The steps taken in data connection in Power BI include:
**1. Open Power BI Desktop**
- Launch Power BI Desktop on computer.

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Power%20Bi%20Desktop.png)

**2. Get Data**
- Click on the "Blank report" tab in the Power BI Desktop.
- Click on the "Home" tab in the Power BI Desktop.
- Select "Get Data" to initiate the data import process

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Get%20Data%20(Power%20BI).png)

**3. Choose Text/CSV and Specify the File Location**
- In the "Get Data" window, select "Text/CSV" as the data source.
- Navigate to the location where the CSV file is stored.
- Select the CSV file you would like to import and click "Open."

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/File%20Location.png)

**4. Preview and Transform**
- Select the tables to be inserted
- Power BI displays a preview of the data from the CSV file.
- Review the data to ensure it is displayed correctly.
- Click on transform data.

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Power%20Query.png)

### Data Profiling
Data profiling is the process of examining your dataset to understand its structure, quality, and integrity before performing analysis. It's an essential first step in any data project. Here’s the data profiling summary for my Railway Station Analysis based on the railway.csv file and the dashboard visuals:

**Basic Information**
- **Total Rows:** 31,653  
- **Total Columns:** 18

### Column Profiling Table:

| Column Name           | Data Type | Unique Values | Missing Values | Missing (%) | Sample Values                         |
|-----------------------|-----------|----------------|----------------|-------------|----------------------------------------|
| Transaction ID        | Int64     | 31,653         | 0              | 0.00%       | da8a6ba8-b3dc, b0cdd1b0-f214, ...       |
| Date of Purchase      | Date      | 128            | 0              | 0.00%       | 2023-12-08, 2023-12-16, ...             |
| Time of Purchase      | Time      | 24,351         | 0              | 0.00%       | 12:41:11, 11:23:01, ...                 |
| Purchase Type         | Text      | 2              | 0              | 0.00%       | Online, Station                         |
| Payment Method        | Text      | 3              | 0              | 0.00%       | Contactless, Credit Card, Debit Card   |
| Railcard              | Text      | 4              | 0              | 0.00%       | Adult, None, Disabled, Senior          |
| Ticket Class          | Text      | 2              | 0              | 0.00%       | Standard, First Class                   |
| Ticket Type           | object    | 3              | 0              | 0.00%       | Advance, Off-Peak, Anytime              |
| Price                 | Int64     | 125            | 0              | 0.00%       | 43, 23, 3, 13, 76                       |
| Departure Station     | Text      | 12             | 0              | 0.00%       | London Paddington, Kings Cross, ...    |
| Arrival Destination   | Text      | 32             | 0              | 0.00%       | Liverpool Lime Street, York, ...       |
| Date of Journey       | Date      | 121            | 0              | 0.00%       | 2024-01-01, 2024-01-02, ...             |
| Departure Time        | Time      | 96             | 0              | 0.00%       | 11:00:00, 09:45:00, ...                 |
| Arrival Time          | Time      | 203            | 0              | 0.00%       | 13:30:00, 11:35:00, ...                 |
| Actual Arrival Time   | Time      | 623            | 1,880          | 5.94%       | 13:30:00, 11:40:00, ...                 |
| Journey Status        | Text      | 3              | 0              | 0.00%       | On Time, Delayed, Cancelled            |
| Reason for Delay      | Text      | 8              | 27,481         | 86.82%      | Signal Failure, Technical Issue, ...   |
| Refund Request        | Boolean    | 2              | 0              | 0.00%       | No, Yes                                 |

### Data Cleaning & Preparation
Using Power Query Editor, the following data cleaning and preparation procedures were performed:
**1. Created New Columns:** Some of the new columns that were added to the dataset include:
- **Month Name:** This column was extracted from the "Date of Purchase" Column.

   DAX Code: `Month Name = FORMAT(railway[Date of Purchase].[Date],"MMM")`
- **Month No:** This column was extracted from the "Date of Purchase" Column.

  DAX Code: `Month No = MONTH(railway[Date of Purchase])`
- **Route:** This column was created by combining the "Departure Station" and "Arrival Destination" column together.

   DAX Code: `Route = railway[Departure Station] & " - " & railway[Arrival Destination]`
- **Departure Hour12:** This column was extracted from the "Departure Time" Column.

   DAX Code: `DepartureHour12 = 
IF(
    HOUR([Departure Time]) = 0 || HOUR([Departure Time]) = 12,
    12.00,
    MOD(HOUR([Departure Time]), 12) + 0.00
)`
- **Departure Hour24:** This column was extracted from the "Departure Time" Column.

  DAX Code: `DepartureHour24 = FORMAT(HOUR([Departure Time]), "00.00")`

**2. Created New Measues**
The following DAX Measures were created:
- **Total Revenue:** Thus calculates the total revenue generated from ticket purchases by summing the Price column.

  DAX Code: `Total Revenue = SUM(railway[Price])`
- **Average Ticket Price:** This computes the average price of all tickets sold, providing insight into typical ticket costs.

  DAX Code: `AVG Ticket Price = AVERAGE(railway[Price])`
- **Total Tickets Purchased:** This counts the number of unique ticket transactions, indicating total tickets purchased.

  DAX Code: `Total No of Tickets Purchased = DISTINCTCOUNT(railway[Transaction ID])`
- **Delayed Journey Count:** This returns the number of journeys that were marked as delayed in the dataset.

  DAX Code: `Delayed Journey = COUNTROWS(FILTER('railway',railway[Journey Status]="Delayed"))`
- **Refund Request Count:** This counts how many passengers requested a refund, helping assess service issues.

  DAX Code: `Refund Requests = COUNTROWS(FILTER(railway, railway[Refund Request]= "Yes"))`
- **Total No of Stations:** This measures the number of unique departure stations, giving insight into network reach and station usage.

  DAX Code: `Total Stations = DISTINCTCOUNT(railway[Departure Station])`

### Key KPIs
- **Total Revenue:** $741,921
- **Total Tickets Purchased:** 31,653
- **Average Ticket Price:** $23.44
- **Total Stations:** 12
- **Total Delayed Journeys:** 2,292
- **Total Refund Requests:** 1,118

### Key Analytics & Insights
**1.	 Ticket Revenue by Station**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Ticket%20Revenue%20by%20Station.png)

**Insight:** London Kings Cross generated the highest revenue (~$200K), followed by Liverpool Lime Street ($135K) and London Euston ($112K).

**Problem:** Heavy revenue concentration in a few stations might indicate dependence on limited routes.

**Recommendation:** Diversify promotional efforts to boost underperforming stations. Consider additional services or offers from mid-tier stations to expand revenue base.



**2. Most Popular Route Taken**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Most%20Popular%20Route%20Taken.png)

**Insight:** The most frequented route is Manchester Piccadilly → Liverpool Lime Street (4.6K journeys), followed by London Euston → Birmingham New Street (4.2K).

**Problem:** High demand routes may face congestion, reduced service quality, or maintenance strain.

**Recommendation:** Prioritize infrastructure, train capacity, and service frequency on top routes. Introduce loyalty or dynamic pricing strategies to manage load.

**3. Total Revenue by Ticket Types**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Total%20Revenue%20by%20Ticket%20Type.png)

**Insight:**
•	Advance tickets generated the highest revenue.
•	Off-Peak tickets sold in high volume, but at lower average prices.
•	Anytime tickets provided a balanced contribution.

**Problem:** While Advance tickets are profitable, dependence on pre-booking might limit spontaneous travelers.

**Recommendation:** Enhance pricing strategies by balancing promotions across all ticket types. Consider limited-time discounts for Off-Peak and Anytime options to drive volume.

**4. Monthly Ticket Purchase Trends**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Monthly%20Ticket%20Purchase.png)

**Insight:** January led in ticket sales (205K), followed by March (195K) and April (187K). A sharp drop in December (1K) could be due to holiday season, data cutoff, or reduced services.

**Problem:** Seasonality affects revenue forecasting and staffing.

**Recommendation:** Prepare flexible staffing and marketing for peak months. Investigate December’s dip—if due to reduced services, ensure communication to minimize customer dissatisfaction.

**5. Journey Status Breakdown**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Passenger's%20Journey%20Status.png)

**Insight:** 86.82% of journeys were on time, while 7.24% were cancelled and 5.94% were delayed.

**Problem:** Nearly 13% of journeys experienced disruption—this affects trust and can trigger refund claims or negative feedback.

**Recommendation:** Investigate delay and cancellation causes. Implement predictive maintenance, improve scheduling, and boost transparency via real-time updates.

**6. Peak Travel Hours**

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Peak%20Travel%20Times.png)

**Insight:**

- Highest ridership occurs at 06:00, 07:00, 17:00, and 18:00, with 3K+ passengers each.
- Lowest traffic appears between 11:00–15:00.

**Problem:** Uneven distribution of passengers causes overcrowding and resource underutilization.

**Recommendation:** Promote off-peak travel with discounted fares or flexible ticketing. Increase train frequency or seating during peak hours to maintain comfort and punctuality.

### Data Visualization

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Railway%20KPIs.png)

![](https://github.com/Ujunwajohn01/Railway-Analysis-/blob/main/Full%20Dashboard.png)

### Recommendations
**1. Focus on High-Performing Stations:**
Prioritize services and staffing at London Kings Cross, Liverpool Lime Street, and London Euston.

**2. Maximize Advance Ticket Sales:**
Encourage more customers to book early by expanding discounts or loyalty rewards for advance purchases.

**3. Improve Journey Reliability:**
Reduce delays and cancellations through better scheduling, real-time updates, and backup planning.

**4. Leverage Off-Peak Hours:**
Run promotions during late-morning/afternoon hours to increase usage during quieter periods.

**5. Analyze Route Preferences:**
Offer targeted deals or premium services on popular routes like Manchester–Liverpool and Euston–Birmingham.

**6. Reduce Refund Requests:**
Analyze root causes of cancellations or complaints that lead to refunds. Improve customer experience around journey disruptions.

### Conclusion
This railway station analysis provides a comprehensive look at station revenue, travel patterns, ticket type behavior, and passenger experience. The findings empower stakeholders to make strategic decisions that enhance profitability, reduce delays, and align services with rider behavior. By leveraging these insights, railway companies can improve operational efficiency, customer satisfaction, and revenue performance.

### Contact

Obianujunwa Vivian John

ujunwajohn01@gmail.com

Lagos, Nigeria

Role Target: Data Analyst (Transport, Logistics, or Tech-focused organizations)

### THANK YOU!









