# Group4
# This project is a part of the CPE314 Computer Networks course | KMUTT


------------------------------------------------------
		The required dependencies
------------------------------------------------------
install pyhon3 
pip install paho-mqtt
pip install openpyxl
pip install mysql-connector-python
------------------------------------------------------


------------------------------------------------------
		Database setup scripts
------------------------------------------------------
Type the following command in MySQL. If you have more 
than one server, you need to create additional tables 
with the same data but with different names, for 
example, server2, server3, etc or you can import the 
attached sql file.

CREATE DATABASE network_project;
USE network_project;
CREATE TABLE server1 (
    RowID int NOT NULL,
    NodeID varchar(255) NOT NULL,
    Humidity varchar(255),
    Temperature varchar(255),
    Thermal_array varchar(4096),
    Reading_time varchar(255),
    PRIMARY KEY(RowID,NodeID)
);

------------------------------------------------------


------------------------------------------------------
			client.py
------------------------------------------------------

This file contains the system's publisher program. It 
delivers the sensor data to the MQTT broker after 
reading data from an Excel file. These messages use 
the Paho MQTT client library to be transmitted to the 
MQTT broker and contain information like humidity, 
temperature, and a thermal array. Each chunk of the 
message is delivered as a distinct message, with each 
chunk being no more than 250 bytes. The node_id is 
defined in the code if you want to run multiple nodes 
you need to change the node_id in the file.

- cd project_network
- python3 client.py

------------------------------------------------------


------------------------------------------------------
			server.py
------------------------------------------------------

This file contains the system's subscriber program 
that receives messages from an MQTT broker. 
The messages are sent from the publisher who publishes 
the topic that subscribers subscribe to. 
The maximum size for a message transmitted is 250 bytes, 
and the data that was previously separated before 
sending will be concatenated in this file before being 
updated in the database.

- cd project_network
- python3 server.py

------------------------------------------------------


------------------------------------------------------
	SampleInput.xlsx - Example sensor data
------------------------------------------------------


------------------------------------------------------
		Created By Group4-sec32
------------------------------------------------------

MR. Puridach Wutthihathaithamrong  		ID:63070503440
MR. Pooritouch Boontaweesawad  		ID:63070503441
MS. Yuwapa Saykhamton  				ID:63070503446
MR. Apirak Senarak  				ID:63070503458
MR. Kunnithi Treecharoensomboon  		ID:63070503461

------------------------------------------------------

