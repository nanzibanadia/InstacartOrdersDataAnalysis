# InstacartOrdersDataAnalysis

Data Analyzing the Order Dataset provided by Instacart 

## Loading the InstacartOrdersByDepartment dataset

Instacart is a grocery store delivery service. People place orders online, requested products are gathered at the grocery store, and delivered to the person’s location, sometimes within an hour. Instacart made data for several million of these orders publicly available on their website (https://www.instacart.com/datasets/grocery-shopping-2017 (Links to an external site.))

Each row is a summary of orders associated with a particular hour in the day and a particular department.

1. order_hour_of_day: The hour of the day when the order was placed (0 = 12am, 1 = 1am etc)
2. department: The department the products came from (e.g. alcohol, produce)
3. num_orders_hour: The number of products ordered from this particular department during this particular hour.
4. Tot_orders_dept: The total number of products ordered from this particular department across all hours of the day.

## The InstacartOrdersByDepartment.csv file is loaded in train variable using read_csv pandas method.

	order_hour_of_day	department	num_orders_hour	tot_orders_dept
0	0	alcohol	33.0	5598.0
1	1	alcohol	32.0	5598.0
2	2	alcohol	5.0	5598.0
3	3	alcohol	3.0	5598.0
4	4	alcohol	2.0	5598.0
5	5	alcohol	12.0	5598.0
6	6	alcohol	34.0	5598.0
7	7	alcohol	92.0	5598.0
8	8	alcohol	161.0	5598.0
9	9	alcohol	343.0	5598.0

## Columns and unique departments
1. The columns of the dataset: order_hour_of_day, department, num_orders_hour, tot_orders_dept
2. Departments: alcohol, babies, bakery, beverages, breakfast, bulk, canned goods, dairy eggs, deli, dry goods pasta, frozen, household, international, meat seafood, missing, other, pantry, personal care, pets, produce, snacks,
3. Departments for food only: alcohol, bakery, beverages, breakfast, bulk, canned goods, dairy eggs, deli, dry goods pasta, frozen, meat seafood, pantry, snacks

The columns of the dataset:  Index(['order_hour_of_day', 'department', 'num_orders_hour',
       'tot_orders_dept'],
      dtype='object')
Departments:  ['alcohol' 'babies' 'bakery' 'beverages' 'breakfast' 'bulk' 'canned goods'
 'dairy eggs' 'deli' 'dry goods pasta' 'frozen' 'household' 'international'
 'meat seafood' 'missing' 'other' 'pantry' 'personal care' 'pets' 'produce'
 'snacks']
 
Departments for food only:  ['alcohol', 'bakery', 'beverages', 'breakfast', 'bulk', 'canned goods', 'dairy eggs', 'deli', 'dry goods pasta', 'frozen', 'meat seafood', 'pantry', 'snacks']
order_hour_of_day	num_orders_hour	tot_orders_dept
count	504.000000	504.000000	504.000000
mean	11.500000	2747.255952	65934.142857
std	6.929064	5324.675357	92421.685490
min	0.000000	0.000000	1359.000000
25%	5.750000	141.500000	11902.000000
50%	11.500000	726.000000	35986.000000
75%	17.250000	2821.750000	81242.000000
max	23.000000	35391.000000	409087.000000

## Data analysis
Steps:
1. At first we remove the unnecessary records of items which are not in food department.
2. The records of indiviual food departments are taken into separate varibles.
3. We plot the records of each varibles seperately taking 'order_hour_of_day' for x-axis and 'num_orders_hour' for y-axis.
4. We use combination of color and markers to seperate each department legend.
5. We'll look for the departments who are intersect each other, signifying that we item orders crosses other orders for a particular time.
Research question: Do people order different foods at different times of day?
A new pandas dataframe is created and initialized with only the food departments indexed the labels (0 = 12 A.M. , 23 = 11 P.M. )
The number orders from particular food department during this particular hour is plotted using pandas plot method using both line and bar kind.
Visualization : It can be visualized that people generally do not order different foods at different times of day but with an exception for a breakfast (black) and meat_seafood (cyan with 'o' marker).

## 
