---

kanban-plugin: basic

---

## To-Do

- [ ] Payment Repository #phase-2 #feature
- [ ] Account Repository #phase-2 #feature
- [ ] TBC - PaymentHistory repository #phase-2 #feature
- [ ] TBC - BookingHistory Repository #phase-2 #feature
- [ ] TBC - PaymentHistory #phase-2 #feature
- [ ] TBC - UserService #phase-2 #feature <br>- create user with admin permission only if user is an admin<br>- can only be registered if it is in the permission list<br>- admin can add user to user to permission list<br>- password and token system<br>- initialise user account?
- [ ] AdminController?
- [ ] TBC - Login and Security #phase-3 #feature
- [ ] TBC - Payment integration #phase-4  #feature


## Blocked



## Ready For Development

- [ ] F7 - Room Enums#phase-1 #feature <br>Update Room names then change to update


## In Development

- [ ] F6 - Booking Service V1 #phase-1 #feature <br>Has the following dependencies:<br>- [x] user <br>- [x] dance class<br><br>Methods:<br>- [x] createBooking<br>- [x] getByRoomAndBetweenDates<br>- [x] delete booking<br>- [x] getAllBookingsByUser<br>- [x] getBookingById<br><br>- [x] error handling<br><br>Test<br>- [x] booking service test<br>- [ ] controller tests
- [ ] F6- DanceClass service + Controller #phase-1 #feature <br>- [x] create class<br>- [x] delete class<br>- [x] get all class options <br>- [x] get by id<br>- [x] get by active class type<br>- [x] error handling<br><br>do i need a dance classrquest?<br><br>Tests<br>- [x] service test<br>- [ ] controller tests


## Testing

- [ ] F5 - UserController #feature #phase-1 <br>- [x] register user<br>- [x] find user by id<br>- [x] update user<br>- [x] delete user<br>- [x] request validations<br>- [x] exception handlers <br><br>Test<br>- [ ] create<br>- [x] read<br>- [ ] update<br>- [ ] delete<br>- [ ] validations


## Done

- [ ] F1 - java entities #phase-1 #feature <br>- [x] User<br>- [x] Booking<br>- [x] Room<br>- [x] Payment<br>- [x] Account<br>- [x] BookingHistory<br>- [x] DanceClass
- [ ] F2 - Booking Repository #phase-1 #feature <br>- [x] find by room and dates<br><br>Test<br>- [x] create booking<br>- [x] cancel booking<br>- [x] get by room and between dates
- [ ] F3- User Service #phase-1 #feature <br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request<br><br>Tests<br><br>update permision if user updating it is a admin?<br>change email but only if it exists in the permission list<br><br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request
- [ ] F4 - UserRepository Test #phase-1 #feature <br>- [x] create user<br>- [x] delete user<br>- [x] update user properties<br>- [x] get u ser by id




%% kanban:settings
```
{"kanban-plugin":"basic","show-checkboxes":false,"tag-colors":[{"tagKey":"#phase-1","color":"rgba(255, 173, 243, 1)","backgroundColor":"rgba(240, 108, 169, 0.1)"},{"tagKey":"#feature","color":"rgba(220, 245, 222, 1)","backgroundColor":"rgba(160, 240, 108, 0.1)"},{"tagKey":"#bug","color":"rgba(195, 127, 128, 1)","backgroundColor":"rgba(240, 108, 108, 0.1)"}]}
```
%%