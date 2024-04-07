---

kanban-plugin: basic

---

## To-Do

- [ ] Payment Repository #phase-1
- [ ] Account Repository #phase-1
- [ ] TBC - BookingHistory Repository #phase-2
- [ ] TBC - PaymentHistory #phase-2
- [ ] TBC - PaymentHistory repository #phase-2
- [ ] TBC - UserService #phase-2 <br>- create user with admin permission only if user is an admin<br>- can only be registered if it is in the permission list<br>- admin can add user to user to permission list<br>- password and token system<br>- initialise user account?


## Blocked

- [ ] F - Booking Service V1 #phase-1 #feature <br>Has the following dependencies:<br>- [ ] user <br>- [ ] dance class


## Ready For Development

- [ ] Room Repository #phase-1
- [ ] DanceClass Reposiotry #phase-1
- [ ] F- DanceClass service #phase-1 #feature <br>- [ ] create class<br>- [ ] delete class<br>- [ ] get all class options dependant on user permission
- [ ] DanceClass Repo Test #phase-1 #feature


## In Development

- [ ] F5 - UserController<br>- [x] register user<br>- [x] find user by id<br>- [x] update user<br>- [x] delete user<br>- [ ] request validations<br>- [ ] exception handlers <br><br>Test<br>- [ ] create<br>- [ ] read<br>- [ ] update<br>- [ ] delete<br>- [ ] validations
- [ ] detailed message of UserRequestException is null. How do i set this with a exception id like to know so stack traces can be easier to read..
- [ ] Add a @Before each to the repositories tests
- [ ] improve exception so it does not take error list as this seems unecessary n uses abundance pf boilerplate code
- [ ] validation not working?
- [ ] error code model when start with 0 it is user
- [ ] when start with 1 it is..
- [ ] excetra for each model i made in chronological order?
- [ ] error presents below the field of registration and not general error above regsietr button? is the idea for now


## Testing



## Done

- [ ] F1 - java entities #phase-1 #feature <br>- [x] User<br>- [x] Booking<br>- [x] Room<br>- [x] Payment<br>- [x] Account<br>- [x] BookingHistory<br>- [x] DanceClass
- [ ] F2 - Booking Repository #phase-1 #feature <br>- [x] find by room and dates<br><br>Test<br>- [x] create booking<br>- [x] cancel booking<br>- [x] get by room and between dates
- [ ] F4 - UserRepository Test #phase-1 #feature <br>- [x] create user<br>- [x] delete user<br>- [x] update user properties<br>- [x] get u ser by id
- [ ] F3- User Service #phase-1 #feature <br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request<br><br>Tests<br><br>update permision if user updating it is a admin?<br>change email but only if it exists in the permission list<br><br>- [x] create a user<br>- [x] delete a user<br>- [x] update user properties<br>- [x] get user by the id<br>- [x] validation<br>- [x] user request




%% kanban:settings
```
{"kanban-plugin":"basic","show-checkboxes":false,"tag-colors":[{"tagKey":"#phase-1","color":"rgba(255, 173, 243, 1)","backgroundColor":"rgba(240, 108, 169, 0.1)"},{"tagKey":"#feature","color":"rgba(220, 245, 222, 1)","backgroundColor":"rgba(160, 240, 108, 0.1)"},{"tagKey":"#bug","color":"rgba(195, 127, 128, 1)","backgroundColor":"rgba(240, 108, 108, 0.1)"}]}
```
%%