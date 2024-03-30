User {
	id
	firstName
	lastName
	email
	phoneNumber
	Permission
}

Permission enum {
	ADMIN,
	USER
}

---

Booking {
	id
	User
	Room
	ClassPricing
	bookedFrom
	bookedTo
	Total
}

BookingHistory {
	id
	booking
	BookingStatus
	createdOn
	updatingUser -> as this could be the admin who is making the changes
}

BookingStatus enum{
	BOOKED
	CANCELLED
}

ClassPricing {
	LessonType
	pricePer60
	pricePer30
	pricePer45
}

ClassType enum {
	PRIVATE,
	PRACTICE,
	GROUP,
	OTHER
}

Room {
	id
	name
	availableFrom
	availableTo
}


---

Payment {
	id
	Total
	PaymentStatus
	Booking
	Account?
}

PaymentStatus{
	outstanding
	paid
	voided
}

Account {
	id
	user
	outstandingBalance
}




maybe i want booking in payment and not payment in booking?
maybe booking should have price and paymnet have booking and payment status.....
got to think about this as i want payment logic and booking time seperated?
payment is Directly linked to a booking but not all bookings actually have payments!

booking logic could be done in blocks? not sure 
booking history createdon
booking history has booking status

lesson pricing has lesson type and pricing.
pricePer30
pricePer45
pricePer60
? do in minutes like htis, not sure?