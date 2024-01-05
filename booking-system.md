---

kanban-plugin: basic

---

## To Do

- [ ] F2 - Room Repository #feature
- [ ] F3 -Booking Repository #feature
- [ ] F4 - BookingHistory Repository #feature


## Blocked



## Ready For Development



## In Progress

- [ ] F1 - Customer Repository #feature<br>- [x] extends CrudRepository<br>- [x] findByEmail<br>- [ ] findByFirstAndLastName<br>- [ ] findByFirstName<br>- [ ] findByLastName<br><br>Tests:<br>- [x] save<br>- [ ] update<br>- [ ] findByEmail<br>- [ ] findByFirstAndLastName<br>- [ ] findByFirstName<br>- [ ] findByLastName<br>- [ ] delete


## Testing

- [ ] B1- Cannot update customer #bug <br>Cannot update customer in `CustomerRepostioryTest` as there are no set methods in `Customer`.<br><br>Add to `CustomerRepository`<br>- [x]  setFirstName<br>- [x]  setLastName<br>- [x]  setEmail<br><br>**blocking F1**


## Completed





%% kanban:settings
```
{"kanban-plugin":"basic"}
```
%%