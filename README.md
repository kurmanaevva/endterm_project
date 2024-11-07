# endterm_project

Our project is flower shop named FLORAL. The store offers a seamless shopping experience, where users can add products to their cart, proceed to checkout, and receive products delivered to their specified address. My part was index.html, basket.html, pay.html, pricing.html.

In our project, there are layers that correspond to Layered Architecture:
1) Presentation Layer: this layer is responsible for displaying data to the user. In my code, this is all the HTML elements, visual components, and styles.
2) Application Logic Layer: this layer handles the processing of data and business logic. In my code, this consists of functions that manage the application's state, such as handling the cart, calculating totals, updating data in localStorage, and managing page navigation.
3) Data Layer: this layer is responsible for data storage, retrieval, and updates. In your code, this is the use of localStorage for storing cart and order data.

Design patterns used in my part:

Creational:
1) Singleton: used to work with the shopping cart via localStorage. The location of the basket is controlled in one place using localStorage.getItem("cart") and localStorage.setItem("cart", ...), which simulates the Singleton pattern for working with the basket state. This provides a unique data warehouse that the entire site interacts with.
2) Factory: functions that create HTML content and control the state of the interface like displayCart(), displayOrders() considered as a kind of factory that creates certain elements.

Behavioral:
1) Observer: used in the code when updating the status of the cart (for example, changing the quantity of an item) automatically causes the content on the page to be redrawn. The display Cart() and displayOrders() functions are "observers" that automatically update the UI when data changes in localStorage.
2) Command: used when buttons are clicked (for example, AddToCart, increaseQuantity, decreaseQuantity,  removeFromCart, clearCart, goToPayPage). Each of these functions implements a specific command that is executed in response to a user action. Also used in processPayment() function such that it encapsulates the logic for executing a specific command in response to a button click.
3) Strategy: used in the context of validating the entered data using regular expressions: checking each field (name, email, phone number, card number), changing the quantity, deleting an item.

Structural:
1) Facade: used in a modal window and in related functionality. The user interface hides the complex logic of working with the shopping cart (for example, adding products, managing quantity status, checking data) behind simple interfaces (buttons and forms), providing a more simplified and understandable work with the shopping cart and ordering.
2) Composite: applied to the cart and order structure, where each item in the cart or order can be represented as a separate item.


Sequence of operations:

1) Builder Pattern goes like this:
- A user adds items to the cart.
- The CartBuilder class adds the items one by one to the cart and updates the total cost.
- Once the items are added, the cart can be finalized, and the total is displayed.

2) Iterator Pattern looks like this:
-The user triggers an action that requires accessing all items in the cart.
-The CartIterator object is created using the cart object.
-The iterator goes through each item, returning one item at a time until the end of the list is reached.

3) Layered Architecture Pattern works like this
-The user interacts (e.g., by adding an item to the cart).
-The action triggers methods in the Application Logic Layer (e.g., adding the item to the cart and calculating the total).
-The Data Layer is accessed to store the cart and order data in localStorage or retrieve it when needed.
-The Presentation Layer is updated to reflect the current state of the cart or orders.


