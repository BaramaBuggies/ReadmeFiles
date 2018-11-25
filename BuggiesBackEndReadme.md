# BuggiesBackend
This project is backend side of open source Buggies project for 6th Barama Fintech Hackathon.

Tables and Procedure:

Backend Services are written in PHP and MySql Database is used.

ATM_HASHES

	Every ATM has its own QR Code per Transaction which a String (Hash Code). After each transaction QR Code on the ATM Screen is regenerated and updated in this table.
	The expired Code is also kept in the table but status is changed to C (Close).

ATM_INFO

	Each ATM has its own unique ID and static IP address that are used in the requests sent from ATM to Backend and vice versa. 

LOGIN_INFO

	The customer has Key per session and this key is mapped to CIF in this table. Key is regenerated at each Log In.

TRANSACTIONS

	This is simple log table containing transactions: account, cif, amount, hash (QR) of that transaction, status and timestamp.

USER_INFO

	This table keeps information about Customer: account, cif, pan and balance.

CARD DEBIT
	
	This procedure is the main component of the project at db side. It takes log per transaction, process the request and make corresponding changes 
	to the account(balance).
	
Flows:

USER_LOGIN.PHP 

	This flow is to assign a unique Session Key to customer. Key is regenerated at each log in and used for the requests. 
	Cif is fetched from db by key and used in the transactions.
	
GET_ACCOUNTS.PHP

	It is a sipmle GET service which is fetching all the accounts by CIF.
	
GET_TRANSACTIONS.PHP

	It is the other kind of GET service, which is fetching all transactions - history from TRANSACTIONS table and return them to UI.
	
DATABASE.PHP
	
	It includes DB connection parameters and it is imported and used at all services.
	
CARD_DEBIT.PHP

	This is the transaction flow, it calls CARD_DEBIT restored database procedure and after the succesful transaction it sends TCP request to the ATM
	to tell it that current QR code is expired and it needs to be regenerated for the next transaction.
	
ATM_HASHES.PHP
	
	This is the model of the atm_hashes table. It consists of table parameter variables, read and write function. Read function is for getting 
	last open hash according to atm id input. Write function is for inserting new hash according to atm id input.
	
GENERATE_QR.PHP
	
	File has one function to generate random hash string of randomly chosen values from numbers, lowercase and uppercase letters.
	
GET_QR.PHP

	This file is for getting latest added open hash according to atm id. Firstly, validation and insertion executed. Then selecting hash from DB on successful insertion
	executed and returned to requestor, ATM in this case.

INSERT_QR.PHP

	This file is the flow of generating random hash string using generate_qr functionality, then validating and inserting it to DB.
