## BDD

Behaviour-Driven Development focuses on clearly identifying the desired behaviour of a feature from the start.

A behaviour is how a product or a feature operates. It is defined as a scenario of inputs, actions and outcomes.

Behaviour examples:
- logging into a web page
- clicking links on a navigation bar
- submitting forms
- making successful service calls
- receiving expected errors

BDD helps to close the gap between business people and technical people by:
- encouraging collaborations across roles
- working in rapid, small iterations to increase feedback and flow
- produces documentations

## Gherkin

Gherkin is a plain-text language with a simple structure. It is designed to be easy to learn by non-programmers. It is intended to be structured and create concise descriptions of test scenarios and illustrate business rules.

``` gherkin
Feature: Account Holder withdraws cash

Scenario: Account has sufficient funds
Given The account balance is 100
And the car is valid
And the machine contains enough money
When the Account Holder requests 20
Then the ATM should dispense 20
And the account balance should be 80
And the card should be returned
```

Gherkin uses a set of special **keywords** to give structure and meaning to **executable specifications**.

Comments are permitted at the start of a new line. # 
Either spaces or tabs can be used for indentation.
Block comments are not supported.

Each line that isn't a blank line has to start with a Gherkin keyword, followed by any text.

Exceptions are free-form descriptions placed underneath `Example/Scenario, Background, Scenario, Outline` and `Rule`.
- Feature
- Rule
- Example (For scenario)
- Given, When, Then, And But
- Background
- Scenario Outline
- Examples (For scenarios)

## Three Amigos

The meeting where everyone sits down and writes down the Gherkin. There needs representation from:

- The Product Owner -> concerned with scope. translating user stories into series of features
- The Tester -> generating scenarios and edge cases
- The Developer -> will add many of the steps to the scenarios and think of details that go into each scenario

All these roles are needed to produce great tests - it's important. These meetings can have more than 3 people and can be various meetings.

## BDD & Agile
- works in tangent with Agile
- acceptance criteria is augmented and standardised with Gherkin so that Product, Engineering, and Testing all agree on delivery.

A three step, iterative process.

Take a **User Story**
- **Talk** about concrete examples (scenarios) of the new functionality to explore, discover and agree on the details of what's expected to be done
- **Document** those examples in a way which can be automated, and check for agreement
- **Implement** the behaviour described by each documented example, starting with an automated test to guide the development of the code.

We call these practices Discovery, Formulation, and Automation.

The idea is to make each change small and iterate rapidly.

## Good Gherkin
Describe the **intended behaviour** of the system, not the implementation. 

Describe **what**, not **how**.

_Will this wording need to change if the implementation changes?_

Be declarative - provide a fact and convey information 

``` gherkin
# GOOD example 

When "Bob" logs in

# BAD scenario
Given I visit "/login"
	When I enter "Bob" in "Username" field
		And I enter "tester" in the "password" field
		And I press the "login" button
	Then I should see the welcome page
```

The second example is not good as it is **how**. If implementation changes, this will also change.

### Imperative - BAD

``` gherkin
Feature: Subscribers see different articles based on their subscription level

Scenario: Free subscribers see only the free articles
	Given users with a free subscription can access "FreeArticle1" but not "PaidArticle1"
	When I type "freeFrieda@example.com" in th email field
		And I type "validPassword123" in the password field
		And I press the "Submit" button
	Then I see "FreeArticle1" on the home page
		And I do not see "PaidArticle1" on the home page
```

- too specific -> there is emails, passwords, and specific articles
- should be generalised behaviour

### Declarative - GOOD

``` gherkin
Feature: Subscribers see different articales based on their subscription level

Scenario: Free subscribers see only the free articles
	Given Free Frieda has a free subscription
	When Free Freida logs in with her valid credentials
	Then she sees a free article
```

- doesn't matter specific credentials
- doesn't matter what specific article

# Try it
``` gherkin
Feature: Return purchased item

Scenario: User can return purchased item
	Given User has valid Reciept
		And User is logged in
	When User request refund with item identifier, receipt identifier and reason for return
	Then User refund approved


Scenario: User cannot return purchased item as user has invalid receipt

Scenario: User cannot return purchased item as user is not logged in

Scenario: User cannot return purchased item indentifier does not exist

```

