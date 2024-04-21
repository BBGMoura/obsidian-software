---

kanban-plugin: basic

---

## To-Do

- [ ] T3 - Booking Implementation #qa-test #phase-1<br><br>- [ ] Testing before dance class exists<br>- [ ] testing after dance class exists<br>- [ ] testing before user exists<br>- [ ] -testing after user exists<br><br>**Creating Booking**<br>- [ ] fail null/empty entries<br>- [ ] success all entries correct<br>- [ ] fail unknow room<br>- [ ] fail unknown class type<br>- [ ] fail booking end and start time between already present lesson<br>- [ ] fail booking starts inside already present lesson<br>- [ ] fail booking ends inside booking already present <br>- [ ] fail booking is on different dates<br>- [ ] fail booking start date/end date is after closing time<br>- [ ] fail booking start date/end date is before opening time<br><br>** Get**<br>- [ ] fail gets inactive bookings<br>- [ ] fail gets bookings by other rooms and <br>- [ ] other users and <br>- [ ] not between the times<br>- [ ] success empty return if booking does not exist list<br>- [ ] fail booking id does nto excist? get booking by id<br><br>**Deactive booking**<br>- [ ] success deactivates present booking and booking does not appear it get all<br>- [ ] fail booking id does not exist


## QA Testing

- [ ] T1 - User Implementation<br>Testing scenarios:<br>- [x] Test before creating booking<br>- [ ] Test after creating booking<br><br><br>**Register**<br>- [ ] fail user with blank fields<br>- [ ] fail user with invalid email<br>- [ ] fail user with email present already in the database<br>- [ ] fail invalid phone no.<br>- [ ] success user with all correct fields<br><br>**Get User by ID**<br>- [ ] success get user by existing ID<br>- [ ] fail get user by non-existing ID<br><br>**Update User** - FAILED<br>- [ ] fail cannot take empty ("firstName" : "") entries<br>- [ ] fail invalid email <br>- [ ] fail invalid phone no.<br>- [ ] fail non existing id<br>- [ ] fail already existing email for another user<br>- [ ] success changes first name<br>- [ ] success changes last name<br>- [ ] success changes email<br>- [ ] success changes phone number<br><br>**Delete User**<br>- [ ] fail user with id non-existing<br>- [ ] success id existing -> will fail if user has bookings. This will be a bug.<br><br> #qa-test #phase-1
- [ ] T2 - DanceClass Implementation #qa-test #phase-1<br>Testing Scenarios:<br>- [ ] Test before booking creation<br>- [ ] Test after booking creation<br><br>**Create DanceClass**<br>- [ ] fail blank/null class type<br>- [ ] success null prices calculate no cost? might change so this will have to take 0/ its converts null to 0<br>- [ ] success deactivates present active dance class<br><br>**get All Active**<br>- [ ] success returns all active <br>- [ ] success returns empty if not dance class<br><br>**Get Active Dance Class By Type**<br>- [ ] success returns only one dance class<br>- [ ] success returns empty dance class<br><br>**Deactivate Dance Class**<br>- [ ] fail id does not exist<br>- [ ]  success deactivates present dance class


## Done





%% kanban:settings
```
{"kanban-plugin":"basic","tag-colors":[{"tagKey":"#qa-test","color":"","backgroundColor":""}]}
```
%%