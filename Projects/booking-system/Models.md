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

Booking {
	id
	User
	BookingStatus
	createdOn
	bookedFrom
	bookedTo
	duration? 
}

BookingStatus enum{
	BOOKED
	CANCELLED
}

Payment {
	id
	Price
	PaymentStatus
	Booking
	Account?
}

PaymentStatus{}




maybe i want booking in payment and not payment in booking?
maybe booking should have price and paymnet have booking and payment status.....
got to think about this as i want payment logic and booking time seperated?
payment is Directly linked to a booking but not all bookings actually have payments!

booking logic could be done in blocks? not sure 