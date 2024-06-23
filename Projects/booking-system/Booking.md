CRUD Operations:
- create a booking
- cancel a booking
- amend a booking -> cancel and create a new booking? This can be an UI thing where you press cancel and are directed straight to a page.? or could be just a popup come up for the new booking and they can put when they want.
- get all by room and week

- get all bookings by between bookedFrom and bookedTo (? is this something i need?)#

add to the enum permission based? so can only use the other and unavailable based on the permission being admin.


think about more what i need...
- view from customer calender view all bookings based on room and within a week
- get all bookings if the booking: startDate is after or equal to bookeddFrom and before   bookedTo. the endDate has to be after bookedFrom or before bookedTo. and room is equal to.


When share is true, we actually want a list of bookings?

lets say we have one booking from 9 to 10 which can be shared.
Other users can then 
 book inside the 9-10 any time between those.
 