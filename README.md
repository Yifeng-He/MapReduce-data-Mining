# MapReduce-Data-Mining-on-a-Hadoop-Cluster
This project aims to find the most delayed flights, airports, or carriers in US.

# How to run the program on a Amazon EMR Hadoop cluster?

1. add two new Environment Variables to the your computer:
AWS_ACCESS_KEY_ID: ****
AWS_SECRET_ACCESS_KEY: ****

You can create your own Security Credentials in your Amazon AWS account.

2. enter the folder containing the Python script and the data, run the following command:

$ python find_most_delayed_airports.py -r emr --num-core-instances=4 --name=airports.csv 2008_small.csv

The program (find_most_delayed_airports.py) will be run on Amazon EMR Hadoop cluster of 5 nodes (1 Master node + 4 core nodes). The Hadoop cluster will be automatically terminated after the submitted job is completed.

# Dataset:
The dataset can be downloaded from:
http://stat-computing.org/dataexpo/2009/the-data.html

Data description:
1) Flight information (2800_small.csv)
	
1 	Year 	1987-2008

2 	Month 	1-12

3 	DayofMonth 	1-31

4 	DayOfWeek 	1 (Monday) - 7 (Sunday)

5 	DepTime 	actual departure time (local, hhmm)

6 	CRSDepTime 	scheduled departure time (local, hhmm)

7 	ArrTime 	actual arrival time (local, hhmm)

8 	CRSArrTime 	scheduled arrival time (local, hhmm)

9 	UniqueCarrier 	unique carrier code

10 	FlightNum 	flight number

11 	TailNum 	plane tail number

12 	ActualElapsedTime 	in minutes

13 	CRSElapsedTime 	in minutes

14 	AirTime 	in minutes

15 	ArrDelay 	arrival delay, in minutes

16 	DepDelay 	departure delay, in minutes

17 	Origin 	origin IATA airport code

18 	Dest 	destination IATA airport code

19 	Distance 	in miles

20 	TaxiIn 	taxi in time, in minutes

21 	TaxiOut 	taxi out time in minutes

22 	Cancelled 	was the flight cancelled?

23 	CancellationCode 	reason for cancellation (A = carrier, B = weather, C = NAS, D = security)

24 	Diverted 	1 = yes, 0 = no

25 	CarrierDelay 	in minutes

26 	WeatherDelay 	in minutes

27 	NASDelay 	in minutes

28 	SecurityDelay 	in minutes

29 	LateAircraftDelay 	in minutes

2) Airport Names (airports.csv)
airports.csv describes the locations of US airports, with the fields:

iata: the international airport abbreviation code
name of the airport
city and country in which airport is located.
lat and long: the latitude and longitude of the airport

3) Carrier codes (carriers.csv)
carriers.csv lists the carrier codes with full names
