# (201902 Fordgobike Trip Data Exploration)
## by (Martin Ikpe)


## 201902 Fordgobike Trip Dataset
This dataset includes information about individual rides made in a bike-sharing system covering the greater San Francisco Bay area. This Datsset was gotten from udacity server. Below are the basic features of the Dataset:
Trip Duration (seconds)
Start Time and Date
End Time and Date
Start Station ID
Start Station Name
Start Station Latitude
Start Station Longitude
End Station ID
End Station Name
End Station Latitude
End Station Longitude
Bike ID
User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual)
Member Year of Birth
Member Gender

Cleaning the Null Values
The below null values were discovered in the dataset and were cleaned before data exploration to get accurate visualization. start_station_id: 197, start_station_name: 197, end_station_id: 197, end_station_name: 197, member_birth_year: 8265, member_gender: 8265, The date was clean using the start_station_id and member_birth_year column since start_station_id, start_station_name, end_station_id and end_station_name has common null values; member_birth_year and member_gender also have common null values. After cleaning the null values the dataset dropped from 183412 rows to 174952 rows

Dealing with Erroneous Datatype
The below erroneous datatype were discovered and corrected
bike_share_for_all_trip initially has object dataype and was converted to category datatype
start_time initially has object dataype and was converted to Datetime datatype
end_time initially has object dataype and was converted to datetime datetype

Added Columns
The below features were added to the dataset for more effective and efficient data exploration:
start_month,
end_month,
start_day,
end_day,
start_hour,
end_hour,
age,
same_station_round_trip,
start_session


## Summary of Findings

A thorough investigations were carried out and we were able to get some insight into the dataset. 
We have more number of Bike riders than female. 
We have more number of subscribers than customer. 
we have more of the young adult population participating in the bike ride. 
More trips were taken on a weekday than weekend with Thursday having the largest number of trips recorded. 
Most Trips took place in the morning between the hours of 7-10 AM and in the afternoon. 
Some trips started from aparticular station and ended on same station. 
We discovered that there were aged people participating in the bike ride whose ages were above 80 years. 
We observed that only subscribers have their bike shared while customers did not share their bike at all. 
Male subscribers and customers has more duration when compared with those of their female counterparts. 
We have less female participants that shared their by bike but more aged people when compared with those of their male counterparts.

## Key Insights for Presentation
Investigating some key features that influences trip duration. Below are the key insights:
1. This visualization shows that most trips took place within the weekdays while less trips were taken on weekends. The trips were also taken more in the morning and than afternoon.
2. The users that participated in this Bike trip were divided into two categories namely: the subcribers and the Customers. Secondly the subscribers were only the ones that shared their Bike while the customers did not share their bike at all.
3. The Age of the paticipants has negative correlation on the duration of the trip
