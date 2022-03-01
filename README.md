# QR Code-Scanning-for-Warehouse-using-Fin-Raspberry-Pi

As part of my labs residency project to design and create an affordable WMS/ERP system for businesses that cannot afford an actual WMS/ERP system and maybe try it out here in Balena’s warehouse after the project is over or use it at some point in the future.

Here’s a quick overview of what the devices using blocks will hopefully be able to do:

Using a Raspberry Pi 4 with an external screen and camera to be able to scan QR Codes which then will be sent to an excel file which will recognise and categorise the scans by item and movement (dispatch/receiving). The end goal is to being able to use these QR Codes scanning to generate a stock report (stock balance) and a movement tracker (ledger with all the movements). To achieve that the first step will be installing the hardware parts (camera, touch screen) to the raspberry pi device and then find/create code to push to the device.

Quick summary of the blocks that are needed for the device:

The Pi device accesses the camera and it’s ready to scan QR Codes and extract data as below mentioned.
Firstly the user scans from a printed list of QR Codes one of the following 6 functions:
1)Inbound (receiving items), 2) Outbound (dispatching items) 3) Stock transfer (for assembly line or transfer returned products to stock - 1st function ), 4) Inbound (finished product from assembly line), 5) Return from customer, 6) Disposal
Secondly the user scans (from a printed list of QR Codes) the QR Code of the product name.
Thirdly the user scans the individual item (EA/Case) QR Code.
After completing the above mentioned scans the data will be imported to an excel file (ideally on the cloud) and then this excel file using code/linked cells with formulas will automatically assign the QR Codes into its categories. For example the first scan will tell the formula that this is either receiving or dispatching, the second scan will tell the formula the specific item that this movement is for and thirdly the scan of the actual item QR Code will add/remove it from the stock. Alternatively, if it’s not that complicated to build the blocks, the device will prompt to the user’s screen a drop down list to select the first two steps (receiving/dispatching and entering the item name/code). By doing so, the user will only need to scan the actual QR Code of the item.

Project Limitations:
At first there were lots of issues with how the raspberry pi 4 device operated. There were plenty of Raspberry OS installments since there were lots of "freezing" and lagging. One thing that definetely improved the device was replacing the SD card with a high speed one. After replacing the SD card, the difference was noticible on how fast the update - upgrade commands worked and how fast the code for opening the camera for QR Code scanning worked. Another stumble on this project was the behavior of the QR Code scanner. Initially the code (which I found on a youtube tutorial) would open the camera and start identifing QR codes and making entries in the databse.csv file. Although, it would not stop scanning QR codes and logging entries and most times scan the same QR code multiple times which resulted duplicate entries in the database. At first, there was a lot of brainstorming ideas on how to stop the code from running indefinitely, some of these ideas were to install a physical button to stop the code from running or place a GUI button to stop the code via pressing it from the touchscreen or make the code understand QR codes that were already scanned and prevent it from re scanning. The solution was much simpler than expected as eventually there was no need for physical buttons, complicated coding or a fancy GUI. The only thing needed was writing “break” on the code just below the code that is responsible for recording the scanned information on the csv file.


The following hardware is used for this project:

Raspberry Pi 4 1GB Ram (running Raspberry OS)
3.5” Touch Screen
Raspberry Pi HQ Camera
Raspeberry Pi Camera Lens
MicroSD Card Extreme Pro
3D Printed Case
3D Pringed Fingerstylus
Device is powered with Raspberry's Official Charger or any conventional powerbank
