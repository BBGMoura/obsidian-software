---

kanban-plugin: basic

---

## To-Do

- [ ] Implement github actions
- [ ] Logging
- [ ] Payment Repository #phase-2 #feature
- [ ] Account Repository #phase-2 #feature
- [ ] TBC - PaymentHistory repository #phase-2 #feature
- [ ] TBC - BookingHistory Repository #phase-2 #feature
- [ ] TBC - PaymentHistory #phase-2 #feature
- [ ] TBC - Login and Security #phase-3 #feature
- [ ] User permitted to register only if in user permision database
- [ ] AdminController #phase-3 #feature
- [ ] TBC - UserService Permission Implementation #phase-3  #feature <br>- create user with admin permission only if user is an admin<br>- can only be registered if it is in the permission list<br>- admin can add user to user to permission list<br>- password and token system<br>- initialise user account?
- [ ] TBC - Payment integration #phase-4  #feature


## Blocked



## Ready For Development

- [ ] F7 - Room Enums #phase-1 #feature <br>Update Room names then change to update
- [ ] B3 - DanceClassImpl - Can create DanceClass with NULL class type #bug #phase-1 <br><br>When creating a dance class, when submitting a requets with `"classType":` missing, dance class gets created with NULL class type. This is incorrect and should raise validation error. <br><br>Did not add @Valid in controller.
- [ ] B4 - DanceClassImpl - Price should all be 0 or should all be a value. #bug #phase-1<br><br>No null price values should be allowed. (change all tests)<br>all values should either be 0 or more than 0.
- [ ] B5 - DanceClassImpl - incorrect class type enum error handling #bug #phase-1 <br><br>Currently, when making a request with an unknown class type, there is a general bad request instead of feedback.
- [ ] B6 - BookingImpl - incorrect room/class type enum error handling #bug #phase-1 <br><br>Currently, when making a request with an unknown class type/Room, there is a general bad request instead of feedback.
- [ ] B7 - BookingImpl - validations not working #bug #phase-1 <br><br>Can enter null values for booking request as null validation
- [ ] B8 - BookingImpl - open and closing time booking error is too general #bug #phase-1 <br><br>When making a booking which is before opening time or after closing time, the error is too general. "Cannot make a booking with invalid time"". Error should be along the lines of "Booking time is before opening time or after closing time."<br><br>Maybe also add information regarding when the opening and closing time is for what ever day?
- [ ] B9 - BookingImpl - booking overlaps other booking error too general #bug #phase-1 <br><br>Cannot complete booking as the room is already booked within this time. Something like this.
- [ ] B10 - BookingImpl - Error for booking on same day not raised. #bug #phase-1 <br><br>Logic for same day and same year is not correct. CAN MAKE BOOKINGS WHICH SPAN MULTIPLE DAYS!
- [ ] B11 - BookingImpl - Invalid date error handling #bug #phase-1 <br><br>Such as April 31 does not exist
- [ ] B12 - BookingImpl - Request Param and REquest body is handling LocalDateTime with different formats. Booking schedule. #bug #phase-1
- [ ] B13 - UserImpl - cannot delete user when user has booking #bug #phase-1


## In Development

- [ ] B2 - UserImpl - User can register/update number which does not begin with 0. #bug #phase-1


## Testing



## Done

- [ ] B1 - UserImpl - Cannot update just one field on user #bug #phase-1 <br><br>When updating an already existing user, it is not possible to update just one field. <br><br>When field is:<br>`"firstName": ""` <br>This is not being allowed. This is correct behaviour.<br><br>However, when field is missing we get the error `must not be empty`.
- [ ] F6 - Booking Service V1 #phase-1 #feature <br>Has the following dependencies:<br>- [x] user <br>- [x] dance class<br><br>Methods:<br>- [x] createBooking<br>- [x] getByRoomAndBetweenDates<br>- [x] delete booking<br>- [x] getAllBookingsByUser<br>- [x] getBookingById<br><br>- [x] error handling<br><br>Test<br>- [x] booking service test<br>- [x] controller tests
- [ ] F5 - UserController #feature #phase-1 <br>- [x] register user<br>- [x] find user by id<br>- [x] update user<br>- [x] delete user<br>- [x] request validations<br>- [x] exception handlers <br><br>Test<br>- [x] create<br>- [x] read<br>- [x] update<br>- [x] delete<br>- [x] validations
- [ ] F6- DanceClass service + Controller #phase-1 #feature <br>- [x] create class<br>- [x] delete class<br>- [x] get all class options <br>- [x] get by id<br>- [x] get by active class type<br>- [x] error handling<br><br>Tests<br>- [x] service test<br>- [x] controller tests
- [ ] F1 - java entities #phase-1 #feature <br>- [x] User<br>- [x] Booking<br>- [x] Room<br>- [x] Payment<br>- [x] Account<br>- [x] BookingHistory<br>- [x] DanceClass
- [ ] F2 - Booking Repository #phase-1 #feature <br>- [x] find by room and dates<br><br>Test<br>- [x] create booking<br>- [x] cancel booking<br>- [x] get by room and between dates
- [ ] F3- User Service #phase-1 #feature <br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request<br><br>Tests<br><br>update permision if user updating it is a admin?<br>change email but only if it exists in the permission list<br><br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request
- [ ] F4 - UserRepository Test #phase-1 #feature <br>- [x] create user<br>- [x] delete user<br>- [x] update user properties<br>- [x] get u ser by id




%% kanban:settings
```
{"kanban-plugin":"basic","show-checkboxes":false,"tag-colors":[{"tagKey":"#phase-1","color":"rgba(255, 173, 243, 1)","backgroundColor":"rgba(240, 108, 169, 0.1)"},{"tagKey":"#feature","color":"rgba(220, 245, 222, 1)","backgroundColor":"rgba(160, 240, 108, 0.1)"},{"tagKey":"#bug","color":"rgba(250, 180, 181, 0.77)","backgroundColor":"rgba(245, 39, 39, 0.23)"},{"tagKey":"#qa-test","color":"rgba(162, 156, 233, 0.87)","backgroundColor":"rgba(108, 117, 240, 0.1)"}]}
```
%%