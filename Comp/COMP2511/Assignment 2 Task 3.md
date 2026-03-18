## Defining the Use Cases

### Use Case 1: User Subscribes to Stock A Price Update
**Description:**
A user wants to recieve an email notification when stock A prices change by $1 or more.
**Primary Actors:**
- User
**Preconditions:**
- User has access to a network
- Backend has a method of accessing the price value of Stock A
**Postcondition:**
- Notification is sent to user detailing the price change of the stock
**Trigger:**
User subscribes to Stock A updates
**Main Flow:**
- User selects Stock A and subscribes to price change notifications by inputting their email address
- User confirms their email address using a link emailed to them.
- Stock A value changes by $1 or more
- User receives email notification of the price change
**Exceptional Flow:**
- Email Authentication Fails (User fails to confirm email address)
- Website informs user that their Email authentication failed, and gives them an option to try again
- Notification Email is NOT sent when Stock A price changes by more than $1
### Use Case 2: User Request Data Spreadsheet of Stock A
**Description:**
A user wants an excel spreadsheet containing weekly price data regarding Stock A for the past 6 months.
**Primary Actors:**
- User
**Preconditions:**
- Database has 6 months of Stock A price data at a weekly frequency or a method of checking it
**Postconditions:**
- User will be given a spreadsheet, containing the Stock A price data received in the past 6 months
**Trigger:**
User requests 6 months worth of Stock A price data, formatted with weekly frequency in a spreadsheet
**Main Flow:**
- User selects Stock A
- User requests the stock data and selecting format options and presses a 'download' button
- Spreadsheet is downloaded to the User's device
**Exceptional Flow:**
- User Requests 6 months of price data, specifying a spreadsheet data format
- Database only has 2 months of price data regarding Stock A
- Software informs user that only 2 months of data can be retrieved
- Spreadsheet containing 2 months of data is downloaded to the User's device
### Use Case 3 User views current Price of Stock A
**Description:**
A user wants to view the current price that Stock A is valued at
**Primary Actors:**
- User
**Preconditions:**
- Backend has a method of retrieving the stock price of Stock A
**Postconditions:**
- The current price of Stock A will be displayed to the user
**Trigger:**
User searches/selects Stock A on the software
**Main Flow:**
- User searches for Stock A on the website
- Software displays the current price of Stock A
**Exceptional Flow:**
- User searches for Stock A on the website
- Software cannot retrieve the current price of Stock A
- Software will display an error message to the User
<div style="page-break-after: always"></div>

## Defining the Architecture
### C4 Context Level Diagram
![[A2T3Context.png]]

<div style="page-break-after: always"></div>

### C4 Container Level Diagram

![[A2T3Container.png|700]]

### Justifying Decisions
**Decision 1: Choosing the Event-Driven Architecture**
I chose to use an event-driven architecture for this software because a major part of the system is notifying users about a change in the state of the data - this reduces the cost of the program repeatedly requesting the current data state from other services, and improves the scalability of the system given that event-driven architecture is built on microservices. Use case 1 demonstrates an example of where this architecture is beneficial, with the user notification is automatically triggered when stock pricing changes.

**Decision 2: Separating the system into data retrieval services**
I chose to make a service for each method of data retrieval (scraping, download, API) which improves the modularity of the system, and also allows the system to be easily expanded upon. This way, more data sources which utilise the preexisting data retrieval methods can be added easily, and a new data retrieval method can be added otherwise.

<div style="page-break-after: always"></div>

## Defining the Behaviour
### Sequence Diagram

**Use Case 1**
![[UC1SD.png|700]]
**Use Case 2**
![[UC2SD.png]]

**Use Case 3**
![[UC3SD.png]]