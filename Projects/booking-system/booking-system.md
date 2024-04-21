---

kanban-plugin: basic

---

## To-Do

- [ ] Payment Repository #phase-2 #feature
- [ ] Account Repository #phase-2 #feature
- [ ] TBC - PaymentHistory repository #phase-2 #feature
- [ ] TBC - BookingHistory Repository #phase-2 #feature
- [ ] TBC - PaymentHistory #phase-2 #feature
- [ ] TBC - Login and Security #phase-3 #feature
- [ ] AdminController #phase-3 #feature
- [ ] TBC - UserService Permission Implementation #phase-3  #feature <br>- create user with admin permission only if user is an admin<br>- can only be registered if it is in the permission list<br>- admin can add user to user to permission list<br>- password and token system<br>- initialise user account?
- [ ] TBC - Payment integration #phase-4  #feature


## Blocked



## Ready For Development

- [ ] F7 - Room Enums#phase-1 #bug  <br>Update Room names then change to update


## In Development



## Testing

- [ ] T1 - User Implementation #qa-test #phase-1
- [ ] T2 - Booking Implementation #qa-test #phase-1
- [ ] T3 - DanceClass Implementation #qa-test #phase-1


## Done

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