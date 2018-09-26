# UBS coding  challenge

ABC Investment Bank is a prominent global bank, as part of the General Ledger System, you are required to develop a position calculation process.

Position Calculation process takes start of day positions and transaction files as input, apply transactions on positions based on transaction type (B/S) and account type (I/E), and computes end of day positions. Depending on the direction of the transaction (Buy/Sell) each transaction is recorded as debit and credit into external and internal accounts in the “Positions” file.
 
## Input:
>**Positions File:**  	contain start positions for instruments
**Transactions Files:** contains transactions for a day


## Process:

Read Positions and Transactions files, compute new positions and write to new end of day positions file.

For each transaction in Transaction file,

Apply TransactionQuantity into matching instrument records in the position file

If Transaction Type =B ,

	   For AccountType=E, Quantity=Quantity + TransactionQuantity

       For AccountType=I, Quantity=Quantity - TransactionQuantity

If Transaction Type =S ,

       For AccountType=E, Quantity=Quantity - TransactionQuantity

       For AccountType=I, Quantity=Quantity + TransactionQuantity

 
## Query:

 At the end of the process find instruments with largest and lowest net transaction volumes for the day. (net volume is change in positions from start of day positions to end of day positions)

### Attached files:

#### Input:

1. **Input_StartOfDay_Positions.txt**  (csv format, comma delimited, 1st line is header line)

2. **Input_Transactions.txt** (json format)  (use json library of your choice)

 

#### Expected Output: 
**Expected_EndOfDay_Positions.txt** (Output of the process should match with this Expected output)

 
# Data Dictionary:
	1. Transaction File
| Type | Description |
|--|--|
| TransactionId |  Id of transaction record |
| Instrument |  Stock symbol of the instrument |
| TransactionType |  B (Buy) / S (Sell) |
| TransactionQuantity |  Quantity of transaction |


		
	2. Positions File

| Type | Description |
|--|--|
| Instrument |  Stock symbol of the instrument |
| Account | Ledger Account Number |
| AccountType |  Account type I (Internal) / E (External) |
| Quantity | Total postion quantity |

	3. EndOfDay_Positions

| Type | Description |
|--|--|
| Instrument |  Stock symbol of the instrument |
| Account | Ledger Account Number |
| AccountType |  Account type I (Internal) / E (External) |
| Quantity | Total postion quantity |
| Delta | Net change in positions during the day |


## Criteria:

1. Coing standard
2. Unit tests
3. Exception handling


## Useful links:

https://www.investopedia.com/terms/p/position.asp
https://www.investopedia.com/terms/g/generalledger.asp

 

 

 
