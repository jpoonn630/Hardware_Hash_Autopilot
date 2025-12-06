# Hardware_Hash_Autopilot
Creating an usb stick, that enable users to scape for Autopilot enrollment

1) Going into powerhsell as admin
2) Run this command Install-Script -Name Get-WindowsAutoPilotInfo
3) After succesfully downloading, transfer the "Get-WindowsAutopilotInfo.ps1" file into the usb stick directory. 
4) For a quicker process, can create a cmd file.
  Steps:
    - Open notepad
    - Copy this in
```
@echo off
:: Collect Autopilot hardware hash to D:\compHash.csv
PowerShell -NoProfile -ExecutionPolicy Unrestricted -File "%~dp0Get-WindowsAutoPilotInfo.ps1" -OutputFile "%~dp0mycurrenthash.csv" -Append
echo.
echo ✅ Hardware hash collected to %~dp0compHash.csv
pause
```
  - Then save the notepad as cmd
5) Done

  - To use open cmd as admin
  - Navigate by your usb drive. eg C:\Windows\System32>D:
  - D:\>get-hash.cmd
  - It will then scrape and a, excel file called "mycurrenthash" will be created inside the usb directory, ready to be upload to autopilot enrollment



