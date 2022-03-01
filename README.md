# Barcode-Scanning-for-Warehouse-using-Fin-Raspberry-Pi
As part of my labs residency project to design and create an affordable WMS system for businesses that cannot afford an actual WMS system/ERP system and maybe try it out here in Balena’s warehouse after the project is over or at some point in the future.

Here’s a quick overview of what the devices using blocks will hopefully be able to do:

Using a Raspberry Pi 4 or similar with an external screen and camera to be able to scan barcodes which then will be sent to an excel file which will recognise and categorise the scans by item and movement (dispatch/receiving). The end goal is to being able to use these barcodes scanning to generate a stock report (stock balance) and a movement tracker (ledger with all the movements). To achieve that the first step will be installing the hardware parts (camera, touch screen and maybe an external battery) to the raspberry pi/Balena Fin device and then find/create code to push to the device.

Quick summary of the blocks that are needed for the device:

The Fin/Pi device accesses the camera and it’s ready to scan barcodes and extract data as below mentioned.
Firstly the user scans from a printed list of barcodes one of the following 6 functions:
1)Inbound (receiving items), 2) Outbound (dispatching items) 3) Stock transfer (for assembly line or transfer returned products to stock - 1st function ), 4) Inbound (finished product from assembly line), 5) Return from customer, 6) Disposal
Secondly the user scans (from a printed list of barcodes) the barcode of the product name.
Thirdly the user scans the individual item (EA/Case) barcode.
After completing the above mentioned scans the data will be imported to an excel file (ideally on the cloud) and then this excel file using code/linked cells with formulas will automatically assign the barcodes into its categories. For example the first scan will tell the formula that this is either receiving or dispatching, the second scan will tell the formula the specific item that this movement is for and thirdly the scan of the actual item barcode will add/remove it from the stock. Alternatively, if it’s not that complicated to build the blocks, the device will prompt to the user’s screen a drop down list to select the first two steps (receiving/dispatching and entering the item name/code). By doing so, the user will only need to scan the actual barcode of the item.

We have the following hardware available here at the office but feel free to recommend other if needed:

Raspberry Pi 4 (running Raspberry OS)
3.5” Touch Screen
Raspberry Pi HQ Camera
Raspeberry Pi Camera Lens
MicroSD Card Extreme Pro

