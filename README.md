Python control of C by GE Bluetooth lightbulbs
==============================================

A simple Python API for controlling [C by GE](https://www.cbyge.com/) lighting devices.

This is not an officially supported Google product.

Example use
-----------

Retrieve authentication data from the remote API and automatically create devices:

```
import laurel

devices = laurel.laurel("username", "password")
```

Show device information:

```
print(devices[0].name)
print(devices[0].id)
print(devices[0].type)
print(devices[0].brightness)
print(devices[0].temperature)
```

Set the device brightness to 50%:

```
devices[0].set_brightness(50)
```

If the device supports colour temperature setting:

```
if devices[0].supports_temperature == True:
  devices[0].set_temperature(50)
```

Turn the device off:

```
devices[0].set_power(False)
```

Force an update of the device state (note that this is asynchronous):

```
devices[0].update_status()
```
