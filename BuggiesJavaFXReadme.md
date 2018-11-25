GENERAL INFO
	
	This project is part of Buggies project which is implemented using JavaFX. It simulates ATM functionality to be able to view QR Code and other functionalities.

FLOW
	
	Firstly, QR Code is generated with HTTP Post request to backend service according to atm id. Atm id is hardcoded in our case, since software is intended to run on each ATM machine. Returned hash string is converted into image using third party library. At the same time software starts to listen for push request from backend service. Listening is implemented in the thread different from Main Application UI thread to prevent UI freezing and crashing. Listening period is limited to specified period of time. Amount is cashed out on received input param and UI is updated to show cash out processing goes on. To simulate this in our case we delayed the process for a few seconds. Later when time is out, amount is cashed out and main page is returned for new cash out operations.
	
EXTERNAL RESOURCES

	MAVEN is used as build tool
	qrgen - Maven dependency library used to generate image file from string
	gson - Maven dependency library used to map from JSON string to Java POJO object and vice-verse

IMPORTANT IMPLEMENTATION CLASSES AND INTERFACE

	NetworkManager - HTTP Post request sent to get hash string. Received string converted into image
	TimeServer - Socket listener implementation
	OnQrGenerated - interface for callback methods
