---

kanban-plugin: basic

---

## To-Do

- [ ] T1 - User Implementation<br>Testing scenarios:<br>- [x] Test before creating booking<br>- [x] Test after creating booking<br><br><br>**Register**<br>- [x] fail user with blank fields<br>- [x] fail user with invalid email<br>- [x] fail user with email present already in the database<br>- [x] fail invalid phone no.<br>- [x] success user with all correct fields<br><br>**Get User by ID**<br>- [x] success get user by existing ID<br>- [x] fail get user by non-existing ID<br><br>**Update User** - FAILED<br>- [x] fail cannot take empty ("firstName" : "") entries<br>- [x] fail invalid email <br>- [x] fail invalid phone no.<br>- [x] fail non existing id<br>- [x] fail already existing email for another user<br>- [x] success changes first name<br>- [x] success changes last name<br>- [x] success changes email<br>- [x] success changes phone number<br><br>**Delete User** - FAILED<br>- [x] fail user with id non-existing<br>- [x] success id existing -> will fail if user has bookings. This will be a bug.<br><br> #qa-test #phase-1
- [ ] T2 - DanceClass Implementation #qa-test #phase-1<br>Testing Scenarios:<br>- [x] Test before booking creation<br>- [x] Test after booking creation<br><br>**Create DanceClass** - FAILED<br>- [x] fail blank/null class type<br>- [x] fail if one price is 0 and other have prices. only all can be 0.<br>- [x] fail null prices. Prices must be 0 and not null.<br>- [x] success deactivates present active dance class<br><br>**get All Active**<br>- [x] success returns all active <br>- [x] success returns empty if not dance class<br><br>**Get Active Dance Class By Type**<br>- [x] success returns only one dance class<br>- [x] fail returns dance class not found. contact support. correct behaviour.<br><br>**Deactivate Dance Class**<br>- [x] fail id does not exist<br>- [x]  success deactivates present dance class
- [ ] T3 - Booking Implementation #qa-test #phase-1<br><br>- [x] Testing before dance class exists<br>- [x] testing after dance class exists<br>- [x] testing before user exists<br>- [x] -testing after user exists<br><br>**Creating Booking** - FAILED<br>- [x] fail null/empty entries<br>- [ ] success all entries correct<br>- [x] fail unknow room<br>- [x] fail unknown class type<br>- [ ] fail booking end and start time between already present lesson -FAILED<br>- [x] fail booking starts inside already present lesson<br>- [x] fail booking ends inside booking already present <br>- [x] fail booking is on different dates<br>- [x] fail booking start date/end date is after closing time<br>- [x] fail booking start date/end date is before opening time<br>- [x] fail booking ends before it starts<br><br>** Get**<br>- [x] fail gets inactive bookings<br>- [x] fail gets bookings by other rooms and <br>- [x] other users and <br>- [x] not between the times<br>- [x] success empty return if booking does not exist list<br>- [x] fail booking id does nto excist? get booking by id<br><br>**Deactive booking**<br>- [x] success deactivates present booking and booking does not appear it get all<br>- [x] fail booking id does not exist


## QA Testing



## Done





%% kanban:settings
```
{"kanban-plugin":"basic","tag-colors":[{"tagKey":"#qa-test","color":"","backgroundColor":""}]}
```
%%