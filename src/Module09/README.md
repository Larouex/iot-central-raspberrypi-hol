# IoT Central Device Training
## Module 09 - Create your Azure IoT Central Application

Let's create an application in IoT Central that we will use for connecting and testing our device based on a sample Device Capability Model specific for this workshop (thanks Ian!).

## Create your App
* [LINK: Start at IoT Central](https://apps.azureiotcentral.com)
* Goto "My Apps" and click the "+ New Application" button
* Choose "Custom Apps" Icon Button
* Name your application, make it a paid app
* Insure that the "Billing Information" section is in your subscription that you have access, etc.

## Create your DCM
* Goto "Device Templates" and click the "+ New" button
* Click the "IoT Device" image button

![alt text](../Assets/create-iot-device-iotc.png "Create IoT Device")

* Click the "Next: Customize" button at the bottom of the screen
* Click the "Next: Review" button at the bottom of the screen
* Click the "Create" button at the bottom of the screen
* Give your Device Template a name and press enter
* Click the "Import capability model" image button

![alt text](../Assets/create-iot-device-iotc.png "Import capability model")

Select the json file named "device-capability-model.json" located in Module09 folder from the git clone we did at the start of the workshop

![alt text](../Assets/import-capability-model-json-iotc.png "Import capability json model")

# STOP - Instruction Time
## We will walk through creating some simple visualizations and publish.

We will be basing our DCM in the Sample App on the Json  below...
``` Json
[
  {
    "@id": "dtmi:iotc:rpihol;1",
    "@type": "Interface",
    "contents": [
      {
        "@id": "dtmi:iotc:rpihol:ambient_temperature;1",
        "@type": [
          "Telemetry",
          "Temperature"
        ],
        "displayName": {
          "en": "Ambient Temperature"
        },
        "name": "ambient_temperature",
        "schema": "double"
      },
      {
        "@id": "dtmi:iotc:rpihol:ambient_humidity;1",
        "@type": [
          "Telemetry",
          "Humidity"
        ],
        "displayName": {
          "en": "Ambient Humidity"
        },
        "name": "ambient_humidity",
        "schema": "double"
      },
      {
        "@id": "dtmi:iotc:rpihol:chamber_temperature;1",
        "@type": [
          "Telemetry",
          "Temperature"
        ],
        "displayName": {
          "en": "Chamber Temperature"
        },
        "name": "chamber_temperature",
        "schema": "double"
      },
      {
        "@id": "dtmi:iotc:rpihol:chamber_humidity;1",
        "@type": [
          "Telemetry",
          "Humidity"
        ],
        "displayName": {
          "en": "Chamber Humidity"
        },
        "name": "chamber_humidity",
        "schema": "double"
      },
      {
        "@id": "dtmi:iotc:rpihol:message_session_started;1",
        "@type": "Property",
        "displayName": {
          "en": "Message Session Started"
        },
        "name": "message_session_started",
        "schema": "dateTime",
        "writable": true
      },
      {
        "@id": "dtmi:iotc:rpihol:message_count;1",
        "@type": "Telemetry",
        "displayName": {
          "en": "Message Count"
        },
        "name": "message_count",
        "schema": "integer"
      }
    ],
    "displayName": {
      "en": "raspberry-pi-hol"
    },
    "@context": [
      "dtmi:iotcentral:context;2",
      "dtmi:dtdl:context;2"
    ]
  }
]
```

## [Module 10 - Connecting to Azure IoT Central (Python SDK)](../Module10/README.md)