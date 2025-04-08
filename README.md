# 🛺 Namma Yatri Trips Dashboard

A comprehensive Power BI dashboard visualizing real-time trip activity, driver earnings, user engagement, and geographic distribution for the Namma Yatri platform.

---

## 📊 Dashboard Overview

This dashboard provides insights into:
- Trip performance (searches, estimates, quotes, and completions)
- Driver earnings and engagement
- Temporal trends (based on trip duration)
- Geographic distribution of activity across assemblies
- Conversion funnel from trip searches to completed rides

![image](https://github.com/user-attachments/assets/35575fc3-e327-4cba-88d4-063bebd71574)


---

## 📁 Data Model & Schema

### 📌 Table 1: `Assembly`
| Column Name    | Description                         |
|----------------|-------------------------------------|
| Assembly_ID    | Unique identifier                   |
| Assembly       | Name of the specific assembly zone  |

---

### ⏱️ Table 2: `Duration`
| Column Name    | Description                         |
|----------------|-------------------------------------|
| duration_id    | Unique identifier for time periods  |
| duration       | Hourly trip window (e.g., "0-1")    |

---

### 💳 Table 3: `Payment`
| Column Name    | Description                         |
|----------------|-------------------------------------|
| id             | Unique identifier                   |
| method         | Payment method (Cash, UPI, etc.)    |

---

### 🚦 Table 4: `Trip Details`
| Column Name              | Description                                                              |
|--------------------------|--------------------------------------------------------------------------|
| tripid                   | Unique identifier of trips                                               |
| loc_from                 | Source location code                                                     |
| searches                 | Trip request count                                                       |
| searches_got_estimate    | Whether the user got a price estimate (1 = Yes, 0 = No)                  |
| searches_for_quotes      | Searched for drivers after estimate (1 = Yes, 0 = No)                    |
| searches_got_quotes      | Received driver quotes (1 = Yes, 0 = No)                                 |
| customer_not_cancelled   | Customer did not cancel (1 = True, 0 = Cancelled)                        |
| driver_not_cancelled     | Driver did not cancel (1 = True, 0 = Cancelled)                          |
| otp_entered              | OTP entered to start ride (1 = Yes, 0 = No)                              |
| end_ride                 | Whether the ride was completed (1 = Completed, 0 = Not completed)        |

---

### 🚗 Table 5: `Trips`
| Column Name    | Description                                                               |
|----------------|---------------------------------------------------------------------------|
| tripid         | Foreign key linking to Trip Details                                       |
| faremethod     | Payment method ID, links to `Payment` table                               |
| fare           | Fare amount (in INR)                                                      |
| loc_from       | Location ID of source                                                     |
| loc_to         | Destination location, links to `Assembly` table                           |
| driverid       | Driver ID                                                                 |
| custid         | Customer ID                                                               |
| distance       | Distance in kilometers                                                    |
| duration       | Time window identifier, links to `Duration` table                         |

---

## 🚀 Key Metrics Tracked
- **Completed Trips**
- **Driver Earnings**
- **Search ➝ Estimate ➝ Quote ➝ Ride Completion Funnel**
- **Payment Method Distribution**
- **Time of Day Impact**
- **Trip Distance and Fare Analysis**
- **Regional Activity by Assembly**

---

## 🌍 Geographic Focus
The dashboard highlights trip data primarily across **Karnataka, India**, especially focusing on specific **assemblies** such as:
- Ramanagaram
- Yelahanka
- Dasarahalli
- Gandhi Nagar
- Jayanagar, and more.

---

## 🛠️ Tech Stack
- **Power BI**: Dashboard development and visualization
- **Microsoft Excel / SQL**: Data modeling and preprocessing
- **GitHub**: Version control and documentation

---
