# Hardware_Hash_Autopilot
Creating an usb stick, that enable users to scape for Autopilot enrollment

1) Going into powerhsell as admin
2) Run this command Install-Script -Name Get-WindowsAutoPilotInfo
3) After succesfully downloading, transfer the "Get-WindowsAutopilotInfo.ps1" file into the usb stick directory. 
4) For a quicker process, can create a cmd file.
  Steps:
    - Open notepad
    - Copy this in, and safe notepad as cmd file
```
@echo off
:: Collect Autopilot hardware hash to D:\compHash.csv
PowerShell -NoProfile -ExecutionPolicy Unrestricted -File "%~dp0Get-WindowsAutoPilotInfo.ps1" -OutputFile "%~dp0mycurrenthash.csv" -Append
echo.
echo ✅ Hardware hash collected to %~dp0compHash.csv
pause
```
5) Done

  - To use open cmd as admin
  - Navigate to your usb drive. eg C:\Windows\System32>D:
  - D:\>get-hash.cmd
  - It will then scrape an excel file called "mycurrenthash". It will be created inside the usb directory, ready to be use and upload to autopilot enrollment



