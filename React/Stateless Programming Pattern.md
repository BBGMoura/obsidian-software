Components have three roles:
- A stateful component class stores information as state
- A stateless component class displays that state.
- A different stateless component class displays a way to change that state.

Breaking down complex logic into seperate classes that each have one job to do helps with testing and makes code more reusable.

The parent compoenent with the state defines a functuion which changes the state of it.