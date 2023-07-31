# **✨ Investigate Hotel Business using Data Visualization ✨**

**Created by:**
- Siti Hajjah Mardiah
- Email : sitihamardiah1997@gmail.com
- Linkedin : https://www.linkedin.com/in/sitihajjahmardiah/

## **📍 Table of Content 📍**
- Business Understanding
    - Problem Statement
    - Goals
    - Objectives
    - Business Metrics
- Data Preparation
    - Data Description
    - Libraries & Datasets
- Data Understanding
    - Exploring Datasets
    - Data Types Information
    - Statistical Summary
    - EDA (Exploratory Data Analysis)

## **⚙ Work Environment ⚙**

- **Tools**

[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)

- **Programming Language**

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

[![made-with-python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg)](https://www.python.org/)

- **Dataset**

[Investigate Hotel Business using Data Visualization](https://drive.google.com/file/d/1yg1UJ77Zyya1ccoRhv9KmZAzVqYvZtRP/view?usp=sharing)

## **⛳ Business Understanding ⛳**

### **📌 Problem Statement**

The Hotel Business Performance Analysis identifies issues and opportunities, makes recommendations, and proposes specific strategies to maximize revenue, financial performance, and operational efficiencies, while allowing the asset to provide the most appropriate quality and service levels. It uncovers opportunities within the operation to improve revenue, management, and, most importantly, profit.

The purpose of this project is analyzing customer behaviors by provide insights related to hotel business performance. The insight can be obtained by exploring data such as analyzing customer behaviors in booking hotel or looking for factors that influence the cancellation in hotel booking. The results will be presented through visualizations and data storytelling.

### **📌 Goals**

Improving business performance by analyzing customer behavior in booking hotel or looking for factors that influence the cancellation in hotel booking

### **📌 Objectives**

Making a report that contain of the insight related to hotel business performance using visualizations and data storytelling.

**📝 References :**

- JoAnn M. Mulnix-Morris - Hotel Performance Analysis: https://www.hospitalitynet.org/opinion/4112774.html#:~:text=The%20Hotel%20Performance%20Analysis%20identifies,It%20focuses%20on%20revenue%20maximization.

## **⛳ Data Description ⛳**

**Hotel Business Performance Dataset [link dataset](https://drive.google.com/file/d/1yg1UJ77Zyya1ccoRhv9KmZAzVqYvZtRP/view?usp=sharing)**

**Dataset Description:**

This dataset contains booking information for City Hotel and Resort Hotel, and other informations such as when the booking was made, booking canceled, number of adults, children, babies, reservation status and so on.

This dataset contains `119,390 samples` and `29 features/columns`:
- `hotel` - Hotel (City Hotel and Resort Hotel)
    - `City Hotel` is type of hotel located in urban centers and found in large cities
    - `Resort Hotel` is type of accomodation usually built on the coastline or at the foot of mountain hills, offering scenic natural view
- `is_canceled` - Value indicating if the booking was canceled (1) or not (0)
- `lead_time` - Number of days that elapsed between the entering data of the booking into the PMS (Property Management System) and the arrival date
- `arrival_date_year` - Year of arrival date
- `arrival_date_month` - Month of arrival date
- `arrival_date_week_number` - Week number of year for arrival date
- `arrival_date_day_of_month` - Day of arrival date
- `stays_in_weekend_nights` - Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay in the hotel
- `stays_in_weekdays_nights` - Number of weekdays nights (Monday to Friday) the guest stayed or booked to stay in the hotel
- `adults` - Number of adults
- `children` - Number of children
- `babies` - Number of babies
- `meal` - Type of meal booked. Categories are presented in standard hospitality meal packages:
    - Undefined/SC - no meal package
    - BB - Bed and Breakfast
 
  
    - HB - Half board (breakfast and one other meal - usually dinner)
    - FB - Full board (breakfast, lunch and dinner)
- `city` - City name
- `market_segment` Market segment designation. Categories are "TA" means "Travel Agents" and "TO" means "Tour Operators"
- `distribution_channel` - Booking distribution channel. Categories are "TA" means "Travel Agents" and "TO" means "Tour Operators"
- `is_repeated_guest` - Value indicates if the booking name was from repeated guest (1) or not (0)
- `previous_cancellations` - Number of previous bookings that were canceled by the customer prior to the current booking
- `previous_bookings_not_canceled` - Number of previous bookings that were not canceled by the customer prior to the current booking
- `booking_changes` - Number of changes made to the booking from the moment that the booking was entered on the PMS until the moment of check in or cancellation
- `deposit_type` - Indication if customer made a deposit to guarantee the booking. These variables can assume 3 categories:
    - No Deopsit - no deposit was made
    - Non Refund - a deposit was made in the value of the total stay cost
    - Refundable - a deposit was wade with a value under the total cost of stay
- `agent` - ID of the travel agency that made the booking
- `company` - ID of the company/entity that made of the booking or responsible for paying the booking. ID is presented instead of designation for anonymity reasons
- `days_in_waiting_list` - Number of days that the booking was in the waiting list before it was confirmed to the customer
- `customer_type` - Type of booking, assuming one of four categories:
    - Contract - when the booking has an allotment or other type of contract associated to it
    - Group - when the booking is associated to a group
    - Trancient - when the booking is not part of group or contract, and is not associated to other trancient booking
    - Trancient party - when the booking is trancient, but is associated to at least other trancient booking
- `adr` - Average Daily Rate as defined by dividing the sum of all lodging transactions by the total number of staying nights
- `required_car_parking_spaces` - Number of car parking spaces required by the guest
- `total_of_special_requests` - Number of special requests were made by the guest (e.q. twin bed or high floor)
- `reservation_status` - customer did/not check-in and did inform the hotel of the reason why

# **💡 Data Cleansing/Preprocessing 💡**

## **📌 Handling Duplicate Rows**
- This dataset has many duplicated rows, with a total of `33,261 rows`
- Before handling duplicate rows, the dataset had `119,390 rows`
- After handling duplicate rows, the dataset has `86,129 rows`

However, we will not drop the duplicate rows, assuming that it is due to the absence of customer IDs in the data, and it could be a coincidence that the booking criteria are the same for several customers. Thus, we assume that the data is not duplicate.

## **📌 Handling Missing Values**
**There are several missing values in the columns:**
- `company` with a total of `94%` null values, amounting to `112,593 rows`
   Filled with zero (0) values assuming that guest is not under company
- `agent` with a total of `13%` null values, amounting to `16,340 rows`
   Filled with zero (0) values assuming that guest is not booking from agent
- `children` with a total of `0.003%` null values, amounting to `4 rows`
   Filled with zero (0) values assuming that guest does not have/bring children
- `city` with a total of `0.4%` null values, amounting to `488 rows`
   Filled with `unknown` for unavailable city entries

## **📌 Data Types Information**
Changed the data type of float64 which had in these columns: children, agent and company into int64

## **📌 Handling Invalid Values**
For better definition, can replace `Undefined` to be `No Meal` as they both have the same meaning.

After replace the value, found that meal column has value:
- ['Breakfast', 'Full Board', 'Dinner', 'No Meal']

## **📌 Drop Unnecessary Data**

Remove unnecessary data with 0 guest and 0 night by creating column:
- Number of guest/customer (adult+children+babies)
- Total duration of stay (weekend+weekdays)

then remove data with 0 `total_guest` and 0 `stayed_duration`

![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/e081b978-35a2-4e87-ad28-4a50cfd543b1)

- Total rows *before* knowing invalid data (`no guest` and `no stayed duration`) was `119,390 rows`
- *After* looking for invalid data consist of `no guest` and `no stayed duration` and doing drop data, total row was `118,565 rows`

## **📌 Data Type Division**
**List of Columns Types:**

- **Categorical** (14 Columns):
    - `hotel` - Nominal -> City Hotel, Resort Hotel
    - `arrival_date_year` - Ordinal -> 2017, 2018, 2019
    - `arrival_date_month` - Ordinal -> January, February, March, ....
    - `meal` - Nominal -> Breakfast, dinner, Full Board, No Meal
    - `city` - Nominal -> Kabupaten Aceh Jaya, Kabupaten Bandung, Kabupaten Bandung Barat, Kabupaten Bangka, ...
    - `market_segment` - Nominal -> Aviation, Complementary, Corporate, Direct, Groups, Offline TA/TO, Online TA, Undefined
    - `distribution_channel` - Nominal -> Corporate, Direct, GDS, TA/TO, Undefined
    - `deposit_type` - Nominal -> No Deposit, Non Refund, Refundable
    - `agent` & `company` - Nominal -> ID
    - `customer_type` - Nominal -> Bussiness, Contract, Family, Personal
    - `reservation_status` - Nominal -> Canceled, Check-Out, No-Show 
    - `is_canceled` & `is_repeated_guest` - Nominal (Binary 0 & 1)

- **Continous** (17 Columns):
    lead_time, arrival_date_week_number, arrival_date_day_of_month, stays_in_weekend_nights, stays_in_weekdays_nights, adults, children, babies, previous_cancellations, previous_bookings_not_canceled, booking_changes, days_in_waiting_list, adr, required_car_parking_spaces, total_of_special_requests, total_guest, stayed_duration

  ## **📌 Statistical Summary**
  
  ### **💉 Numerical + Date Features**

  ![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/1b5cc2bd-f560-4a04-9c67-3d66d4ea677f)

  ![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/911b77cd-5e53-4593-b82e-95b43d56df4d)


  ### **💉 Categorical Features**

  ![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/0c6c2f31-ef22-42a2-8dbe-e9325fa81ad8)


  ## **⛳ Exploring Business Insights ⛳**

  ## **📌 Monthly Hotel booking Analysis Based on Hotel Type**
  To check the number of hotel bookings each month based on the type of hotel and analyze whether there is an increase and decrease in hotel bookings every month.
  
  ![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/24bb0a12-6a36-4eb1-a710-7a4f15d9f3f1)

  **Interpretations:**

Based on data vizualisation above, can get insights that:
- Both hotel have more guest during `High Season`, and `City Hotel` have most guest than `Resort Hotel`.
- `High Season` occurs throughout `May - July`, especially for hotels with the `City Hotel` type. During these months, there are usually `school/college holidays`. In   addition, `June in 2017-2019 was the moment of Idul Fitri`. So parents usually bring their families on vacation. This explains why May-June got more Guest from both Hotel.
- `November and December` become another `High Season` due to Christmast and New Year holidays, but it has a shorter duration compared May-Jul period.
- `City Hotel` gets sharply decreasing in guest from `August - September`, however `Resort Hotel` seems slightly increased in the same period.
- `Low Season` occurs throughout `January - March` and also in `August - September`, especially for City Hotel type, where there is a significant decreasing in bookings. This decline can be attributed to the start of the school season, as students will focus again on academic activities.

  ## **📌 Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates**
  To check whether the duration of the stay have an impact on the cancellation of the booking

  ![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/3cb80dc8-52dd-4bb8-9c41-183d49131801)

**Interpretations:**

Based on data vizualisation above, can get insights that:

- The longer of duration stay, guests who book hotels with the `City Hotel` type `tend to do cancellation`. Proven by `the highest cancellation rate of 87.23%` which occurred for `stays of more than 4 weeks`.
- In `Resort Hotel` type, `the highest cancellation rate of 46.75%` occurs for guests who book a hotel with a duration of `3 weeks`.
- Based on both of hotel types (City Hotel & Resort Hotel), it can be concluded that `the longer of duration stay ordered by guests, the greater possibility of cancellation`.
- To reduce the occurrence of cancellations, can apply a more stringent cancellation policy.

## **📌 Impact Analysis of Lead Time on Hotel Bookings Cancellation Rate**

To check whether lead time have an impact on the cancellation of the booking.

![image](https://github.com/sitihamardiah/Investigate-Hotel-Business-Performance-using-Data-Visualization/assets/134268514/6b221c37-509f-4e6b-b432-f0c291bd843e)

**Interpretations:**

Based on data vizualisation above, can get insights that:

- The Highest booking cancellation rates in both hotel type occurs on lead time within 11-12 Months,  with cancellation rates in City Hotel of 77.41% and in Resort Hotel of 43.5%.
- The Lowest booking cancellation rates in both hotel type occurs on lead time less 1 Month, with cancellation rates in City Hotel of 22.47% and in Resort Hotel of 13.11%.
- Both Resort and City Hotels have the highest cancellation rate around a 1-year lead time. This could be due to customers' vacation plans getting canceled or forgetting about their hotel reservation if the lead time is too long. Hotels can provide reminders to customers to reduce cancellations and implement a strict cancellation policy for every reservation to prevent such occurrences. Also, by applying cancellation policy on every reservation could helps the hotel to prevent this from happening.

## **✨ Summary** ##

- Both hotels have more guest during holiday season, and City Hotel have more guest than Resort Hotel. 
- High Season occurs throughout May - July, especially for hotels with the City Hotel type. During these months, there are usually school/college holidays. In addition, June in 2017-2019 was the moment of Idul Fitri. November and December become another High Season due to Christmast and New Year holidays.
- Low Season occurs throughout January - March and also in August - September, especially for City Hotel type, where there is a significant decreasing in bookings.
- The longer of duration stay, guests who book hotels with the City Hotel type tend to do cancellation. Proven by the highest cancellation rate of 87.23% which occurred for stays of more than 4 weeks. In Resort Hotel type, the highest cancellation rate of 46.75% occurs for guests who book a hotel with a duration of 3 weeks. Based on both of hotel types (City Hotel & Resort Hotel), it can be concluded that the longer of duration stay ordered by guests, the greater possibility of cancellation.
- The Highest booking cancellation rates in both hotel type occurs on lead time within 11-12 Months, with cancellation rates in City Hotel of 77.41% and in Resort Hotel of 43.5%. The Lowest booking cancellation rates in both hotel type occurs on lead time less 1 Month, with cancellation rates in City Hotel of 22.47% and in Resort Hotel of 13.11%.
- Both Resort and City Hotels have the highest cancellation rate around a 1-year lead time. This could be due to customers' vacation plans getting canceled or forgetting about their hotel reservation if the lead time is too long. Hotels can provide reminders to customers to reduce cancellations and implement a strict cancellation policy for every reservation to prevent such occurrences. Also, by applying cancellation policy on every reservation could helps the hotel to prevent this from happening.
