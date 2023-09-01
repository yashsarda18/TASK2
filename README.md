# TASK2
[Note: All the tasks are combined in a single colab file]

## TASK 2A
Building a Data Transmission System
• Using the provided CSV file, your objective is to create a basic transmission system that replicates the
device's behavior by sending packets of data over MQTT (Message Queuing Telemetry Transport).
• Transmit the data in timestamped packets (matching the CSV) and also simulate scenarios where
multiple frames are stacked together (representing data accumulation during network downtime).
• Utilize any free MQTT broker for this task

## Approach:
- Used hivemq mqtt broker for the project
- Setting up mtqq broker and enabling data transmission using python
- Used paho-mqtt library to establish connection
- After connection establishment, data was transmitted and suscribed in timestamped packets

## Step by step
- Imported the neccessary libraries
- Imported the dataset
- Performed basic preprocessing
- Removed 13 rows where the timestamps were missing.
- Removed the device column as it was of no use (instead gave Device A as the topic in MQTT broker)
- Converted timestamp to integer values as hivemq doesn't support date-time datatype
- Mapped all the 8 directions into integers (1-8)
```'N': 1,'NE': 2,'E': 3,'SE': 4,'S': 5,'SW': 6,'W': 7,'NW': 8```
- Imported the necessary libraries (csv , time , paho-mqtt)
```!pip install paho-mqtt```
- Made a cluster in hivemq and connected it to Colab notebook using ```broker_address``` and ```port```
- Transmitted data into the cluster and suscribed in timestamped packets
[Note: The screenshot is attached in github repository showing the size of the cloud data]


## TASK 2B
Building a Subscriber and Database Storage
• After completing Task 2a, write a subscriber for the above data in a different module.
• Save the received timestamped data into a MongoDB database.

## Approach:
- Tried to connect MongoDB cloud to Colab notebook
- Inserted MongoDB connection string
- Tried to establish connection with MongoDB but due to some technical issues , I was not able to do that.

## Step by step
- Import the library pymongo ```!pip install pymongo```
- Do the MongoDB configuration
- Insert the connection string
- Call a callback function whenever a message is received
- Create MQTT client instance
- Set the message callback function
- Connect to the broker and suscribe to the topic
- Start the mqtt loop to listen for incoming messages
[Note: Tried to establish the connection but due to technical issues , was unable to do that]


## TASK 2C
Data Visualization
• Load the stored data from MongoDB.
• Create basic data visualization plots using the matplotlib library.
• Specifically, compare the PM1.0, PM2.5, and PM10 values in a single time-series plot.
• Implement a user-friendly way to filter the data based on time range and PM values. You can use sliders
or input boxes for this purpose.

## Approach:
- Imported all the necessary libraries
- Plotted time series plot
- Plotted bar chart (although got nothing out of it)
- Plotted Scatter chart comparing PM1.0 vs PM2.5 . These two are highly dependent on each other according to the scatter plot
- Plotted Scatter chart comparing PM2.5 vs PM10 . These two are highly dependent on each other according to the scatter plot

[Note: All the comparison plots can be found at the bottom of the colab notebook]
