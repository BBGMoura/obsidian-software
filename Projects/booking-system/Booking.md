A booking system which allows a user to book rooms for different type of classes.
There are different types of classes which include:
- Practice session
- Private classes
- Group classes
- Other 

The price is dependent on the type of booking and the length of time of the booking.

Practice sessions and private classes price is based on the times of:
- 1Hr
- 0.30Hrs 
- 0.45Hrs

Group classes and Other can only be booked by an admin.

Other booking, there will be no cost (maybe give the option of having a cost?). Group classes will also have no costs.

There are two different types of users, teacher or admin.


Users can only register if the admin has invited them to register.

Teacher can cancel their own class. Teacher will need to input the reason for cancelling.

Also must have a history of classes that's been booked and cancel.

Booking will have statuses
-> booked 
-> cancelled

A teacher will have an account which the price gets recorded to.

Booking made
-> send admin and user a booking confirmation.
-> send an invoice to the teacher for the booking information and price.

A booking has a payment which includes the price and the status of the payment. Payment has an account. The account is linked to the teacher.

Main Models/Entities:
- Booking
- User
- Payment
- BookingHistory
