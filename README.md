# CCS811
Python3 periphery code for the CCS811 I2C sensor

This is test code for how to keep the sensor running so that the heater is on for whenever a reading is desired, and a separate instance of the code can be periodically invoked to grap a data reading value.

One instance of the code is started and left running with the following:
```
from CCS811 import CCS811
ccs = CCS811(MASTER)
```


In the code that consumes data, insert the following code:
```
from CCS811 import CCS811
ccs = CCS811(MASTER)
co2 = ccs.get_co2()
```
This code is still in development an a bit messy.  There is a second data pull strategy included (to be removed) that writes the co2 value to a file after each reading.  The MASTER version should set up the data with a polling frequency, but should not actually call get_co2()
