
Buggies Project is about Qr Code Solutions for Banking Systems. Currently this project simulates Qr Cash Out process between ATM, Banking internal
Processing System and Mobile Application which has already been installed to client's smartphone. 
The main scenario of the project is shown below:
  <ul>
  <li>A customer approaches to ATM to make cash-out operation, presses one of the buttons on the ATM (for example "5") to get the QR Code.
  The text will always be shown on the ATM Screen : "Please press 5 for QR Cash-Out operation."</li>
  <li> After the QR Code is generated and emerges on the screen, TCP Connection is created between ATM and Backend Server.</li>
  <li> The customer opens the corresponding section on the App to scan the Code.</li>
  <li>After scanning the code Accoun and Amount are chosen and the request is sent to the Server.</li>
  <li>If all validations are passed and transaction is completed succesfully, Server send TCP Packet to ATM with which request the ATM will understand
  that the respective amount of money has to be given to the Customer and the QR Code need to regenerated since each QR Code can be used only once.</li>
  
  <h1>Project consists of three diffrent parts</h1>
   
  <li>Android Project for Client</li>
  <li>Back End project for banking processing</li>
  <li>ATM codes written in JavaFX</li>
  
  <h2>You can get all information about these parts in this readme repository and in their own repositories</h2>

  
