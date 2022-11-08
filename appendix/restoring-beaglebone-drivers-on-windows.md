# Restoring BeagleBone drivers on Windows

Newer versions of Windows will occasionally reset the drivers for BeagleBones, making it impossible to connect to them. You can reset the driver selection using the following steps.

1. Connect the BeagleBone to the computer using USB and confirm it's powered on
2. Open "Device Manager" on your computer. Under the "View" menu, ensure that "Show hidden devices" is checked
3. Expand the Ports section. If the BB is connected and powered on you should see one of these indicating "active" with the darker shading
4. Right click on the active port and select "Update Driver"
5. Select "Browse my computer for drivers"
6. Select "Let me pick from a list of available drivers"
7. You should see a option for "Linux USB Ethernet/RNDIS Gadget". Select that.
