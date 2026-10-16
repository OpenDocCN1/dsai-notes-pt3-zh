# Example of Snowflake Schema

Sales Fact Table

time
time_key
day
day_of_the_week
month
quarter
year

time_key

item_key

branch_key

location_key

units_sold

dollars_sold

avg_sales

Measures

branch
branch_key
branch_name
branch_type

item
item_key
item_name
brand
type
supplier_key

supplier
supplier_key
supplier_type

location
location_key
street
city_key

city
city_key
city
state_or_province
country