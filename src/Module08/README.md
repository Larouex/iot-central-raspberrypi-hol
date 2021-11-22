# IoT Central Device Training
## Module 08 - Communicating with Sensors, LED, etc

### We will setup and run a simple Python application to cycle through 3 Led's

* Navigate to Module08 directory
* Run the following command...

```
pip3 install -r requirements.txt
```

* Run the foillowing command...

```
python3 ./mod8.py
```

This will execute the following...

``` Python
import RPi.GPIO as GPIO
import time
import struct 

# --------------------------------------------------------
# Status
# --------------------------------------------------------
Stop = 25
Caution = 8
Go = 7

# --------------------------------------------------------
# Set Mode Leds
# --------------------------------------------------------
GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)
GPIO.setup(Stop, GPIO.OUT)
GPIO.setup(Caution, GPIO.OUT)
GPIO.setup(Go, GPIO.OUT)

# --------------------------------------------------------
# Start the Loop...
# --------------------------------------------------------
try:
    while(1):

        print ("Setting the STOP LED [ON]")
        GPIO.output(Stop, GPIO.HIGH)
        time.sleep(5) 
        GPIO.output(Stop, GPIO.LOW)

        print ("Setting the Wait LED [ON]")
        GPIO.output(Caution, GPIO.HIGH)
        time.sleep(5) 
        GPIO.output(Caution, GPIO.LOW)

        print ("Setting the Good LED [ON]")
        GPIO.output(Go, GPIO.HIGH)
        time.sleep(5) 
        GPIO.output(Go, GPIO.LOW)

except (RuntimeError, TypeError, NameError):
    print ("Failed to Set up the LED Routine. Error %s" % RuntimeError)
    time.sleep(10)
    pass
except KeyboardInterrupt:  
    # Turn off all LED's
    GPIO.output(Stop, GPIO.LOW)
    GPIO.output(Caution, GPIO.LOW)
    GPIO.output(Go, GPIO.LOW)
    GPIO.cleanup()
    
```




## [Module 09 - Create your Azure IoT Central Application](../Module09/README.md)