---

kanban-plugin: basic

---

## To Do

- [ ] F2 - Room Repository #feature
- [ ] F3 -Booking Repository #feature
- [ ] F4 - BookingHistory Repository #feature
- [ ] F5 - Customer Service #feature
- [ ] F6 - Customer Controller #feature


## Blocked



## Ready For Development

- [ ] D1 - Make WorkFlow for each Model #design


## In Progress



## Testing

- [ ] F1 - Customer Repository #feature <br>@{2024-01-05}<br>- [x] extends CrudRepository<br>- [x] findByEmail<br>- [x] findByFirstAndLastName<br>- [x] findByFirstName<br>- [x] findByLastName<br><br>Tests:<br>- [x] save<br>- [x] update<br>- [x] findByEmail<br>- [x] findByFirstAndLastName<br>- [x] findByFirstName<br>- [x] findByLastName<br>- [x] delete
- [ ] B1- Cannot update customer #bug <br>Cannot update customer in `CustomerRepostioryTest` as there are no set methods in `Customer`.<br><br>Add to `CustomerRepository`<br>- [x]  setFirstName<br>- [x]  setLastName<br>- [x]  setEmail<br><br>@{2024-01-05}<br>**blocking F1**


## Completed





%% kanban:settings
```
{"kanban-plugin":"basic","show-relative-date":true,"hide-date-display":true,"hide-date-in-title":true}
```
%%