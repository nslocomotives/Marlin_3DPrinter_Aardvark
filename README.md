# Marlin_3DPrinter_Aardvark
Marlin Firmware - Geeetech I3 Pro B with Hemera Extruder 

# Calibration
First Calibration is written to the E-prom and the Firmware. Any changes to the printers configuration or location will be calibrated and written to the Firmware.  Any subsiquant intermediate calibration for instance moving from PLA to ABS should be written to Eprom.  

### Calibration of the Heatbed
If you want to ensure your not using Eprom values to start with and want clean facorty settings to start with other wise skip this step
```
M502 ; reset
M500 ; saved
```
Next start the bed calibration
```
M303 E-1 C5 S60
```
should get an output like this
```
output here
```
Storing to Eprom Example
```
M304 D471.14 I062.55 P471.14
```
Write the change to Eeprom
```
M500
```

### Calibration of the Hotend
If you want to ensure your not using Eprom values to start with and want clean facorty settings to start with other wise skip this step
```
M502 ; reset
M500 ; saved
```
Next start the bed calibration
```
M303 C5 [E0] S200
```
should get an output like this
```
Recv:  bias: 115 d: 115 min: 197.37 max: 202.86
Recv:  Ku: 53.35 Tu: 22.45
Recv:  Classic PID
Recv:  Kp: 32.01
Recv:  Ki: 2.85
Recv:  Kd: 89.82
Recv: PID Autotune finished! Put the last Kp, Ki and Kd constants from above into Configuration.h
```
Storing to Eeprom Example
```
M301 D089.82 E0 I002.85 P032.01
```
Write the change to Eeprom
```
M500
```

## Documentation link to E3D on how to set up the Hemera
https://e3d-online.zendesk.com/hc/en-us/articles/360014734918-Hemera-Direct-Marlin-1-Guide
