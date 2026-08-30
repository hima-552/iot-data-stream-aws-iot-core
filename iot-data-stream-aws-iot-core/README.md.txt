IoT Data Stream to the Cloud using AWS IoT Core

Student Details

Name: Hima. L

Department: CSE

College: Don Bosco Institute of Technology

Program: Cloud Computing

Project Overview

This project demonstrates an end-to-end IoT data streaming pipeline using AWS IoT Core.

A Python-based sensor simulator generates temperature and humidity readings and publishes them using MQTT. AWS IoT Core receives the messages and processes them using an IoT Rule. The processed sensor data is stored in Amazon DynamoDB and monitored using Amazon CloudWatch.

System Architecture

Python Sensor Simulator
        |
        v
MQTT Topic: sensors/temperature01/data
        |
        v
AWS IoT Core
        |
        v
IoT Rule: StoreTemperatureData
        |
        v
DynamoDB: IoTSensorDataHistory
        |
        v
CloudWatch: Success / Failure Monitoring

Technologies Used

Python

MQTT

AWS IoT Core

Amazon DynamoDB

Amazon CloudWatch

Sensor Data

The simulated device is:

TemperatureSensor01

The MQTT topic used by the project is:

sensors/temperature01/data

Each sensor message contains:

device_id

temperature

humidity

timestamp

AWS IoT Rule

The project uses an AWS IoT Rule named:

StoreTemperatureData

The rule processes messages from the sensor MQTT topic and routes the required data to DynamoDB using a DynamoDBv2 action.

The SQL statement used is:

SELECT device_id, temperature, humidity, timestamp
FROM 'sensors/temperature01/data'

DynamoDB

The project uses two DynamoDB tables:

IoTSensorData – stores the latest sensor reading.

IoTSensorDataHistory – stores historical sensor readings.

The historical table uses:

Partition key: device_id

Sort key: timestamp

The stored records contain the device ID, timestamp, humidity, and temperature values.

CloudWatch Monitoring

A CloudWatch dashboard named:

IoTSensorDashboard

was created to monitor the IoT Rule action.

The dashboard contains:

Success metric

Failure metric

During testing, successful rule activity was observed and the Failure metric remained at zero during the final verification period.

Project Evidence

AWS IoT Rule

The repository contains a screenshot showing the active StoreTemperatureData IoT Rule, MQTT topic, SQL statement, and DynamoDBv2 action.

DynamoDB

The repository contains a screenshot showing sensor records stored in IoTSensorDataHistory.

CloudWatch

The repository contains a screenshot showing the IoTSensorDashboard with Success and Failure metrics.

See the screenshots folder for the evidence images.

Documentation

The complete project report is available in the report folder.

Python Dependency

The required Python package is listed in requirements.txt.

Install it with:

pip install -r requirements.txt

Security Note

AWS IoT certificates and private keys are not included in this repository.

Do not upload:

Private keys

AWS credentials

Device certificates containing sensitive credentials

Other secret authentication files

Result

The project successfully demonstrates an IoT data stream to the cloud using AWS IoT Core. Sensor data was published through MQTT, processed by an AWS IoT Rule, stored in DynamoDB, and monitored using CloudWatch.

Author

Hima. L

CSE | Don Bosco Institute of Technology | Cloud Computing