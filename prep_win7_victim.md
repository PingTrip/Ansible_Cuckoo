####Disable the reserved partition
Press Shift+F10 while installing Windows to open a Command Prompt window.

    diskpart <Enter>
    select disk 0 
    create partition primary

####Create a second vSwitch
Cuckoo-mgr should have 2 network interfaces

####Create a "victim" VM named mine cuckoo-01

####Enable autologin for 
1. Click Start, type netplwiz, and then press Enter.
2. In the User Accounts dialog box, highlight the account you want to automatically log on to. Uncheck the _Users Must Enter A User Name And Password To Use This Computer_.
3. Click OK. 
4. In the Automatically Log On dialog box, enter the user’s password twice and click OK.

####Disable Windows Defender
1. Start, type Windows Defender and hit enter
2. Tools menu -> Options
  1. Disable “Automatic Scanning"
  2. Disable “Realtime Protection”
  3. Disable Administrator -> Use this program

####Disable notices
Under Action Center -> Change Action Center Settings turn off messages for:
  * Windows Update
  * Spyware and Related Protection
  * Virus Protection
  * Windows Backup
  * Check for Updates

####Configure IE
1. Launch Internet Explorer
2. Choose "Dont use recommended settings"
3. Under Tools -> Internet Options. about:blank click apply

####Required Programs
1. Install Python 2.7 (32bit) (https://www.python.org/ftp/python/2.7.13/python-2.7.13.msi)
  1. Add to system PATH: C:\Python27
  2. Create new system variables
    * PYTHONHOME = C:\Python27
    * PYTHONPATH = C:\Python27\DLLs;C:\Python27\Lib;C:\Python27\Lib\site-packages 

2. download and install PIL (http://effbot.org/downloads/PIL-1.1.7.win32-py2.7.exe)

####Disable UAC
1. Go to Start Menu -> Control Panel -> User Accounts and Family Safety -> User Accounts.
2. Click on Change User Account Control settings link.
3. Slide the slider bar to the lowest value with description Never notify.
4. Click OK to make the change effective.

Restart the VM.
