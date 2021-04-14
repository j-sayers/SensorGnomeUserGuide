# Appendix D: Accessing BeagleBone as a network drive

Once a BeagleBone is connected to your computer, you can access it as a shared network drive either in Windows Explorer or the Mac equivalent. Through this method you can copy detection data as well as modify configuration files. It may also be possible to access data files on a BB even if you cannot access the Web Interface or create an FTP connection. 

This uses a connection protocol called SMBv1, which on newer versions of Windows has been disabled in favour of more secure version. You will likely have to re-enable this feature in order to access a BeagleBone as a networked drive.

There are instructions on doing that for Windows here: [https://www.windowscentral.com/how-access-files-network-devices-using-smbv1-windows-10](https://www.windowscentral.com/how-access-files-network-devices-using-smbv1-windows-10).

Once configured, you can navigate the file structure as you would any other drive by entering the following in the address bar: `\\192.168.7.2`

![Navigate to \\192.168.7.2 in the address bar](.gitbook/assets/networkdrv.png)

The folder structure will look a bit different than in FileZilla and you will see three folders 

