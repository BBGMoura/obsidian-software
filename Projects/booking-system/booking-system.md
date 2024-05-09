---

kanban-plugin: basic

---

## To-Do

- [ ] booking schedule takes diff time to booking
- [ ] TBC - UserService Permission Implementation #phase-3  #feature <br>- create user with admin permission only if user is an admin<br>- can only be registered if it is in the permission list<br>- admin can add user to user to permission list<br>- password and token system<br>- initialise user account?
- [ ] TBC - BookingHistory Repository #phase-2 #feature
- [ ] TBC - BookingService - getBookingsByUser should use paging<br>currently, the method which retrieves users by id returns all bookings in the database based on user.<br><br>instead, we want an implementation which uses the paging repository. The request to the controller will be:<br>- user id<br>- current date?<br>- isUpcoming -> boolean which defines w4ether previous or upcoming bookings are needed<br>- offset<br>- amount of bookings<br><br>should return a list of booking DTOs  which matches the amount and offset. Also consider order. order of previous bookings hould start from most recent to oldest. order of upcmoing bookings should start from more recent to fuiter boookings.
- [ ] Payment Repository #phase-2 #feature
- [ ] Account Repository #phase-2 #feature
- [ ] TBC - PaymentHistory repository #phase-2 #feature
- [ ] TBC - PaymentHistory #phase-2 #feature
- [ ] User permitted to register only if in user permision database
- [ ] AdminController #phase-3 #feature
- [ ] TBC - Payment integration #phase-4  #feature
- [ ] CORS
- [ ] deactivate user should be in the admin controller -> furthermore it should delete all upcoming booking. take way the payment for upcoming bookings but leave outstadning payments
- [ ] deactivate
- [ ] can only use the get bookings by user n history if is user or admin so will need auth token or something
- [ ] booking id and booking reference- instead of using booking id we use a bookign reference
- [ ] get all rooms? if enum in frotnend, then if chang ein be then also need change in fe which could be bad but there is not plans to change the rooms so leave it
- [ ] get class types -> for admin controller


## Blocked



## Ready For Development

- [ ] UPDATED REQUIREMENTS<br>-> booking can be shareable betweem users. Up to 3 but this can change or be dependant on room?<br>- each teacher will pay the same amount for the booking for example. if teacher books a room for 60 and a teacher wants to share the room its the same for 60.<br>- price is actually one fixed price not different price per 30/45/60 mins.
- [ ] TBC - Login and Security #phase-2  #feature
- [ ] BookingImpl - many users should be able to book class<br>Implementation:<br>- when creating booking, user should have the option to allow booking to be shareable or not. isShareable boolean added to booking object<br>- new endpoint which is used for user to book already created bookings such as 'book shared booking'<br>- booking will have <List> Users instead of User<br>- booking will use @ManyToMany -> no cascading<br>- will have a join table<br>- where user is referenceed from the booking, the implementation will have to be changed<br>- update tests


## In Development



## Testing



## Done

- [ ] F7 - Room Enums #phase-1 #feature <br>Update Room names then change to update
- [ ] Canary Testing #phase-1
- [ ] Add Logging support #phase-1 #logging<br> add logs where necessary
- [ ] B22 - system print JSOn parse error in handler
- [ ] B21 - BookingImpl - can make overlapping bookings #bug #phase-1
- [ ] B10 - test for bookings which ends before they start #bug #phase-1
- [ ] B18 - delete booking should be changed to deactivate #phase-1 #bug
- [ ] F7 - Implement github actions #phase-1 #feature
- [ ] Tests #phase-1 #testing <br>- fix tests to work together  done<br>- have a test util class instead of defining new objects every class. this will help if an implementation needs to be changed. done  user , need to finis book and start dance class
- [ ] B16 - NotFoundException - make new uswer/booking not foudn exception! -> refactor danclass not found edxeption! #bug #phase-1
- [ ] b15 - BookingImpl - datefrom should not be bigger that date to -> new validation to add to booking. currently this works! noooo #bug #phase-1 <br>adad a check whioch says if dateTo is before /dateFRom then throew exception
- [ ] B14  - RequestException - this exception is returning ids. also this exception is returning the message not as error but as message. Is this correct? as other exceptions return error to show as the error and not message. #bug #phase-1 <br><br>ok to return booking id to customer for now.<br><br>This is a standard exception error returned to cusatomer: <br>```json<br>{<br>  "timestamp": "2024-04-24T11:18:29.922+00:00",<br>  "status": 400,<br>  "error": "Bad Request",<br>  "path": "/booking"<br>}<br>```
- [ ] B13 - UserImpl - cannot delete user when user has booking #bug #phase-1<br><br>-> change functionality so user can only be active or not. not deleted<br>-> change booking functionality so that new bookings can not be made by inactive users
- [ ] B11 - BookingImpl - Invalid date error handling #bug #phase-1 <br><br>Such as April 31 does not exist
- [ ] B10 - BookingImpl - Error for booking on same day not raised. #bug #phase-1 <br><br>Logic for same day and same year is not correct. CAN MAKE BOOKINGS WHICH SPAN MULTIPLE DAYS!
- [ ] B9 - BookingImpl - booking overlaps other booking error too general #bug #phase-1 <br><br>Cannot complete booking as the room is already booked within this time. Something like this.
- [ ] B8 - BookingImpl - open and closing time booking error is too general #bug #phase-1 <br><br>When making a booking which is before opening time or after closing time, the error is too general. "Cannot make a booking with invalid time"". Error should be along the lines of "Booking time is before opening time or after closing time."<br><br>Maybe also add information regarding when the opening and closing time is for what ever day?
- [ ] B7 - BookingImpl - validations not working #bug #phase-1 <br><br>Can enter null values for booking request as null validation<br><br>room can be null also wqhen making request.
- [ ] B6 - BookingImpl - incorrect room/class type enum error handling #bug #phase-1 <br><br>Currently, when making a request with an unknown class type/Room, there is a general bad request instead of feedback.
- [ ] B5 - DanceClassImpl - incorrect class type enum error handling #bug #phase-1 <br><br>Currently, when making a request with an unknown class type, there is a general bad request instead of feedback.
- [ ] B4 - DanceClassImpl - Price should all be 0 or should all be a value. #bug #phase-1<br><br>No null price values should be allowed. (change all tests)<br>all values should either be 0 or more than 0.<br><br>- [x] validation to not allow null values<br>- [x] validation which does not allow negative values<br>- [x] validation which does not allow more than 3 digits and 2 decimals -> can be changed in the future.<br>- [x] validate all values are more than 0 or all valuea re 0.
- [ ] B3 - DanceClassImpl - Can create DanceClass with NULL class type #bug #phase-1 <br><br>When creating a dance class, when submitting a requets with `"classType":` missing, dance class gets created with NULL class type. This is incorrect and should raise validation error. <br><br>Did not add @Valid in controller.<br><br>-> added @Validation to class<br>-> added @Value to class.<br>This still did not work. This is because @NotBlank value only applies for Strings and not Enums. <br><br>In this case @NotNull annotation works.
- [ ] B2 - UserImpl - User can register/update number which does not begin with 0. #bug #phase-1
- [ ] B1 - UserImpl - Cannot update just one field on user #bug #phase-1 <br><br>When updating an already existing user, it is not possible to update just one field. <br><br>When field is:<br>`"firstName": ""` <br>This is not being allowed. This is correct behaviour.<br><br>However, when field is missing we get the error `must not be empty`.
- [ ] F6 - Booking Service V1 #phase-1 #feature <br>Has the following dependencies:<br>- [x] user <br>- [x] dance class<br><br>Methods:<br>- [x] createBooking<br>- [x] getByRoomAndBetweenDates<br>- [x] delete booking<br>- [x] getAllBookingsByUser<br>- [x] getBookingById<br><br>- [x] error handling<br><br>Test<br>- [x] booking service test<br>- [x] controller tests
- [ ] F5 - UserController #feature #phase-1 <br>- [x] register user<br>- [x] find user by id<br>- [x] update user<br>- [x] delete user<br>- [x] request validations<br>- [x] exception handlers <br><br>Test<br>- [x] create<br>- [x] read<br>- [x] update<br>- [x] delete<br>- [x] validations
- [ ] F6- DanceClass service + Controller #phase-1 #feature <br>- [x] create class<br>- [x] delete class<br>- [x] get all class options <br>- [x] get by id<br>- [x] get by active class type<br>- [x] error handling<br><br>Tests<br>- [x] service test<br>- [x] controller tests
- [ ] F1 - java entities #phase-1 #feature <br>- [x] User<br>- [x] Booking<br>- [x] Room<br>- [x] Payment<br>- [x] Account<br>- [x] BookingHistory<br>- [x] DanceClass
- [ ] F2 - Booking Repository #phase-1 #feature <br>- [x] find by room and dates<br><br>Test<br>- [x] create booking<br>- [x] cancel booking<br>- [x] get by room and between dates
- [ ] F3- User Service #phase-1 #feature <br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request<br><br>Tests<br><br>update permision if user updating it is a admin?<br>change email but only if it exists in the permission list<br><br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request
- [ ] F4 - UserRepository Test #phase-1 #feature <br>- [x] create user<br>- [x] delete user<br>- [x] update user properties<br>- [x] get u ser by id


## Archive





%% kanban:settings
```
{"kanban-plugin":"basic","show-checkboxes":false,"tag-colors":[{"tagKey":"#phase-1","color":"rgba(255, 173, 243, 1)","backgroundColor":"rgba(240, 108, 169, 0.1)"},{"tagKey":"#feature","color":"rgba(220, 245, 222, 1)","backgroundColor":"rgba(160, 240, 108, 0.1)"},{"tagKey":"#bug","color":"rgba(250, 180, 181, 0.77)","backgroundColor":"rgba(245, 39, 39, 0.23)"},{"tagKey":"#qa-test","color":"rgba(162, 156, 233, 0.87)","backgroundColor":"rgba(108, 117, 240, 0.1)"}]}
```
%%