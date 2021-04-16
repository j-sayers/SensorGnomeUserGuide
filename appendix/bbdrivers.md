# Installing BeagleBone drivers

The drivers for BeagleBone SensorGnomes can be found in the table below \(copied from the [BeagleBone homepage](http://beagleboard.org/getting-started)\). 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Operating System</th>
      <th style="text-align:left">USB Drivers</th>
      <th style="text-align:left">Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>Windows (64-bit)</p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p>Windows (32-bit)</p>
      </td>
      <td style="text-align:left">
        <p><a href="https://beagleboard.org/static/Drivers/Windows/BONE_D64.exe">64-bit installer</a>
        </p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p></p>
        <p><a href="https://beagleboard.org/static/Drivers/Windows/BONE_DRV.exe">32-bit installer</a>
        </p>
      </td>
      <td style="text-align:left">
        <p>If in doubt, try the 64-bit installer first.</p>
        <ul>
          <li><b>Note #1:</b> Windows Driver Certification warning may pop up two or
            three times. Click &quot;Ignore&quot;, &quot;Install&quot; or &quot;Run&quot;</li>
          <li><b>Note #2:</b> To check if you&apos;re running 32 or 64-bit Windows see
            this: <a href="https://support.microsoft.com/kb/827218">support.microsoft.com/kb/827218</a>.</li>
          <li><b>Note #3:</b> On systems without the latest service release, you may
            get an error (0xc000007b). In that case, please install the following and
            retry: <a href="https://www.microsoft.com/en-us/download/confirmation.aspx?id=13523">www.microsoft.com/en-us/download/confirmation.aspx?id=13523</a>.</li>
          <li><b>Note #4:</b> You may need to reboot Windows.</li>
          <li><b>Note #5:</b> These drivers have been tested to work up to Windows 10</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Mac OS X</td>
      <td style="text-align:left"><a href="https://beagleboard.org/static/Drivers/MacOSX/RNDIS/HoRNDIS.pkg">Network</a>
        <br
        /><a href="https://beagleboard.org/static/Drivers/MacOSX/FTDI/EnergiaFTDIDrivers2.2.18.pkg">Serial</a>
        <br
        />
      </td>
      <td style="text-align:left">Install both sets of drivers.</td>
    </tr>
    <tr>
      <td style="text-align:left">Linux</td>
      <td style="text-align:left"><a href="https://beagleboard.org/static/Drivers/Linux/FTDI/mkudevrule.sh">mkudevrule.sh</a>
      </td>
      <td style="text-align:left">Driver installation isn&apos;t required, but you might find a few udev
        rules helpful.</td>
    </tr>
  </tbody>
</table>

On many newer computers, such as those with Windows 10, the operating system blocks the installation of the BeagleBone drivers as they are “unsigned.” The process may simply fail without an informative message.

![Driver installation may fail because the drivers are unsigned](../.gitbook/assets/drivererror.png)

The way around this is to temporarily disable this security check. Instructions on how to do that [can be found here](https://www.howtogeek.com/167723/how-to-disable-driver-signature-verification-on-64-bit-windows-8.1-so-that-you-can-install-unsigned-drivers/). Option 2 is the simplest and the security measures will revert after the next reboot. The steps are summarized below.

**1\)** Hold down the Shift key while you click the “Restart” option in Windows. Your computer will restart into the Advanced Boot menu

![](../.gitbook/assets/htg1.png)

2\) Select the “Troubleshoot” tile on the Choose an option screen that appears

![](../.gitbook/assets/htg2.png)

3\) Select “Advanced options”

![](../.gitbook/assets/htg3.png)

4\) Click the “Startup Settings” tile

![](../.gitbook/assets/htg4.png)

5\) Click the “Restart” button to restart your PC into the Startup Settings screen

![](../.gitbook/assets/htg5.png)

6\) Type “7” or “F7” at the Startup Settings screen to activate the “Disable driver signature enforcement” option

![](../.gitbook/assets/htg6.png)

Your PC will boot with driver signature enforcement disabled and you’ll be able to install unsigned drivers. However, the next time you restart your computer, driver signature enforcement will be disabled—unless you go through this menu again. 

