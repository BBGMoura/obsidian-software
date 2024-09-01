
**Task Description:**

You are tasked with developing a `ShoppingCart` system that simulates a simple online shopping experience. The system should allow users to add items to the cart, remove items, calculate the total price, and apply various discount strategies.

## Requirements: 

1. Classes and Requirements:
	- `Item`: Represents an individual item with a name and a price.
	- `ShoppingCart`: Manages a collection of items and applies discounts.  
	- `DiscountStrategy`: Interface for different discount strategies that can be applied to the cart.

2. **Functional Requirements**:
**`Item`**:
- **Attributes**: `name` (String), `price` (double).
- **Methods**:
     - Get the item's name.
      - Get the item's price.

**`ShoppingCart`**:        
- **Attributes**: A collection of `Item` objects.
- **Methods**:
	- `addItem(Item item)`: Adds an item to the cart.
    - `removeItem(Item item)`: Removes an item from the cart.
	- `getTotalPrice()`: Returns the total price of all items in the cart.
    - `applyDiscount(DiscountStrategy discountStrategy)`: Applies a discount strategy to the total price.
 
 **`DiscountStrategy`**:
 - **Methods**:
    - `applyDiscount(double totalPrice)`: Takes the total price as input and returns the discounted price.

**Example Discount Strategies**:
- **`PercentageDiscount`**: Applies a percentage-based discount to the total price. For example, a 10% discount.
- **`FixedDiscount`**: Applies a fixed amount discount to the total price. For example, subtracting $5 from the total.

### Features to Implement:

1. **Adding and Removing Items**:
    - The cart should correctly update when items are added or removed.
    - Handle cases where the same item is added multiple times.

1. **Calculating Total Price**:
    - The total price should correctly sum the prices of all items in the cart.
    - Handle cases where the cart is empty.

2. **Applying Discounts**:
    - Implement at least two types of discount strategies (e.g., `PercentageDiscount`, `FixedDiscount`).
    - Ensure the total price reflects the discounts applied.

3. **Edge Cases**:
    - Applying a discount to an empty cart.
    - Adding or removing items not currently in the cart.
    - Applying multiple discounts sequentially.

### Instructions:

1. **Start with TDD**: Write unit tests first based on the functional requirements above. Focus on writing tests that cover normal use cases and edge cases.
2. **Implement the `Item`, `ShoppingCart`, and `DiscountStrategy` classes/interfaces**.
3. **Refactor as Needed**: Ensure your code is clean, maintainable, and follows good design principles. Refactor based on test results and code reviews.
4. **Document Your Code**: Add comments and documentation for classes, methods, and any complex logic.

### Deliverables:

- A fully implemented `Item` class.
- A `ShoppingCart` class with methods for adding, removing, and managing items.
- A `DiscountStrategy` interface with at least two concrete implementations (`PercentageDiscount` and `FixedDiscount`).
- A comprehensive set of unit tests that validate all functionality of the shopping cart and discount application.



**Note:** I need to go over Scanner and File IO