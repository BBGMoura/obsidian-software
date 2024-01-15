## Customer
#### Create Customer
- check if any values are null
- email Regex?
- check if email  is unique
	- If does not pass these checks -> reject
- persist customer
- return customer detail back to view
- HIGHLIGHT id is needed to update

#### View Customer
- search customer by first name, last name and email.
- view all customers
- return a list of customers.

#### Update Customer
- ID is required to update customer
- Can change first name, last name and email
- update values which are non null coming from the request
	- if all are null, nothing to update
- return new customer details

#### Delete Customer
- check if customer has bookings
	- check if bookings aren't cancelled
	- reject if there is bookings
- if no bookings/only cancelled bookings, customer deleted

