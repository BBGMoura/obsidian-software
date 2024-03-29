---

kanban-plugin: basic

---

## To Do

- [ ] F3 -Booking Repository #feature
- [ ] F4 - BookingHistory Repository #feature
- [ ] F6 - Customer Controller #feature


## Blocked



## Ready For Development

- [ ] F2 - Room Repository #feature<br>- [ ] extend CrudRepository<br>- [ ] findByName<br><br>Tests:<br>- [ ] save<br>- [ ] findByName<br>- [ ] update<br>- [ ] delete<br><br>@{2024-01-05}


## In Progress

- [ ] D1 - Make WorkFlow for each Model #design<br>- [ ] customer<br>- [ ] room<br>- [ ] booking<br>- [ ] booking history<br><br>@{2024-01-05}
- [ ] [[F5 - Customer Service v1]] #feature<br>- [ ] create customer<br>- [ ] view all customers<br>- [ ] view by id<br>- [ ] view by first name<br>- [ ] view by last name<br>- [ ] view by fist and last name<br>- [ ] view by email <br>- [ ] update customer<br>- [ ] delete customer<br><br>Interface<br>- [x] customer service interfacee<br><br>CustomerDTO<br>- [ ] create customerDTO<br><br>CustomerMapper<br>- [x] create customerMapper <br>@{2024-01-10}


## Testing



## Completed

- [ ] F1 - Customer Repository #feature <br>@{2024-01-05}<br>- [x] extends CrudRepository<br>- [x] findByEmail<br>- [x] findByFirstAndLastName<br>- [x] findByFirstName<br>- [x] findByLastName<br><br>Tests:<br>- [x] save<br>- [x] update<br>- [x] findByEmail<br>- [x] findByFirstAndLastName<br>- [x] findByFirstName<br>- [x] findByLastName<br>- [x] delete
- [ ] B1- Cannot update customer #bug <br>Cannot update customer in `CustomerRepostioryTest` as there are no set methods in `Customer`.<br><br>Add to `CustomerRepository`<br>- [x]  setFirstName<br>- [x]  setLastName<br>- [x]  setEmail<br><br>@{2024-01-05}<br>**blocking F1**




%% kanban:settings
```
{"kanban-plugin":"basic","show-relative-date":true,"hide-date-display":true,"hide-date-in-title":true}
```
%%