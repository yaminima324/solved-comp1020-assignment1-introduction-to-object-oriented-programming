Download Link: https://assignmentchef.com/product/solved-comp1020-assignment1-introduction-to-object-oriented-programming
<br>
In this assignment, you will implement a set of related classes of objects:  <strong>Customer</strong>:  A customer who orders food

<ul>

 <li><strong>FoodItem</strong>: A specification for a food item that appears on a menu</li>

 <li><strong>Restaurant</strong>: A restaurant that has a menu</li>

 <li><strong>FoodApp</strong>: A food delivery app, used to order food items from restaurants</li>

 <li><strong>Order</strong>: A class that contains all the information about a specific order</li>

</ul>

Keep all of your methods short and simple. In a properly-written object-oriented program, the work is distributed among many small methods, which call each other. Make sure to call methods already created when appropriate, instead of duplicating code for no reason. There are no methods in this entire assignment that should require more than 10 lines of code, not counting comments, blank lines, or {} lines (and many of them need no more than 3-4).

Unless specified otherwise, all instance variables must be <strong>private</strong>, and all methods should be <strong>public</strong>.  Also, unless specified otherwise, there should be <strong><em>no </em>println</strong> statements in your classes. Objects usually do not print anything, they only return <strong>String</strong> values from methods.

<h1>Testing Your Coding</h1>

We have provided sample test files for each phase to help you see if your code is working according to the assignment specifications.  These files are <em><u>starting</u></em><u> <em>points</em></u> for testing your code. Part of developing your skills as a programmer is to think through additional important test cases and to write your own code to test these cases. <em><u>For marking, we will use</u> <u>longer and more comprehensive tests</u></em>.

<h1>Phase 1: Customer and FoodItem classes</h1>

First, implement two simple classes:  a <strong>Customer</strong> class and a <strong>FoodItem </strong>class

The <strong>Customer</strong> class should have:

<ul>

 <li>Three instance variables: the customer’s name (a <strong>String</strong>), email address (a <strong>String</strong>) and street address (a <strong>String</strong>)</li>

 <li>A constructor that has three parameters, in the above order, which are used to initialize the three instance variables.</li>

 <li>A standard <strong>toString</strong> method, which returns a <strong>String</strong> containing the customer name, email address and street address (as shown in the example output below).</li>

 <li>An <strong>equals </strong>method that checks if two customers are equal. Two customers are equal if they have the same email address, since an email address should belong to only 1 customer.</li>

</ul>

The <strong>FoodItem</strong> class should have:

<ul>

 <li>Four instance variables: a name (a <strong>String</strong>), a cost (a <strong>double</strong>), a selling price (a <strong>double</strong>), and the number of items available in stock for selling (an <strong>int</strong>)</li>

 <li>A constructor that takes four parameters, in the above order, which are used to initialize the four instance variables.</li>

 <li>A method <strong>isAvailable </strong>that checks if there are items available for selling (returns false is no items are available, true otherwise)</li>

 <li>A <strong>toString</strong> method which returns a <strong>String</strong> containing the name of the food item and the selling price. If the item is not available, add “(SOLD OUT)” next to the price, making use of the isAvailable method. Follow the format shown in the example output below.</li>

 <li>A method <strong>setSellingPrice </strong>that takes a new price as a parameter, and updates the selling price instance variable.  A method <strong>decrementStock </strong>that decrements the number of items in stock by 1.</li>

 <li>A method <strong>increaseStock </strong>that takes an amount of additional stock as a parameter, and adds it to the existing stock available for selling.</li>

</ul>

You can test your classes using the supplied test program <strong>TestPhase1.java</strong>. You should get the output shown below.

<strong>-Customer Ellen Ripley </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="f5909999879c85b5949a99db969a98">[email protected]</a> </strong>

<strong>Address: 245 Alien road </strong>

<strong>-Customer John McClane </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="9df7f2f5f3fef2eafff2e4ddf5f2e9f0fcf4f1b3fef2f0">[email protected]</a> </strong>

<strong>Address: 560 Yippee-ki-yay boulevard </strong>

<strong>Both customers have different email addresses </strong>

<ul>

 <li><strong>Spaget </strong></li>

</ul>

<strong>$10.75 </strong>

<ul>

 <li><strong>Pristine deathclaw egg </strong></li>

</ul>

<strong>$14.99 (SOLD OUT) </strong>

<strong> </strong>

<ul>

 <li><strong>Pristine deathclaw egg </strong></li>

</ul>

<strong>$15.59 </strong>

<h1>Phase 2: Restaurant and FoodApp classes</h1>

Next, implement the <strong>Restaurant</strong> class, and the <strong>FoodApp </strong>class.




The <strong>Restaurant</strong> class should have:

<ul>

 <li>Three instance variables: the name of the restaurant (a <strong>String</strong>), a menu (stored as an array of <strong>FoodItem</strong>), and a profit (a <strong>double</strong>).</li>

 <li>A constructor that accepts two parameters, the name and an array of FoodItems, and initializes the corresponding instances variables. The profit shall be initialized to 0.</li>

 <li>A <strong>toString</strong> method that returns a <strong>String</strong> containing the name of the restaurant, the profit and the menu on different lines (formatting it exactly as shown in the example below).</li>

</ul>




Then, implement a <strong>FoodApp</strong> class.  This class should have:

<ul>

 <li>A class constant: the maximum number of customers a FoodApp can have (an <strong>int</strong>). Set it to 100.</li>

 <li>Four instance variables: the name of the FoodApp (a <strong>String</strong>), the fees percentage charged to restaurants (a <strong>double</strong>), an array of Customers, and the current number of customers in the array (an <strong>int</strong>)</li>

 <li>A constructor that takes two parameters, the name and the fees percentage, and initializes the corresponding instances variables. The array of customers will be a <u>partially filled array</u>. It should be initialized according to the maximum number of customers, and be empty at the beginning. The current number of customers in the array should be initialized accordingly.</li>

 <li>A method <strong>getCustomerIndex</strong>(<strong>Customer</strong>) that looks for and returns the index of the customer given as a parameter in the array of customers, <u>using the equals method of the Customer class</u>. The method must return -1 if the customer is not found in the array.</li>

 <li>An <strong>addCustomer(Customer)</strong> method that adds the Customer to the customer array, only if the customer is not already present, and returns true if the customer was added. You should make use of the getCustomerIndex method here. If there is already a customer with the same email address, the method should simply return false. You can assume that there will be enough space to add the customer otherwise (no checks required for space). Also, don’t forget to update the counter of the current number of customers.</li>

 <li>A <strong>removeCustomer(Customer)</strong> method that removes the specified customer from the customer array, only if it is found (following again the equals rule of the Customer class). The method returns true if a customer is removed, and false otherwise. When removing a customer, you must fill in the gap by shifting up all the following customers. Also, don’t forget to update the counter of the current number of customers.</li>

 <li>A <strong>toString </strong>method that returns a <strong>String</strong> containing the name of the FoodApp, the number of customers and the list of those customers (formatting it exactly as shown in the example below).</li>

</ul>




You can test your class with <strong>TestPhase2.java</strong>.  You should get the output shown below.

<strong>— Restaurant Burger Queen Profit = 0.0 </strong>

<strong>Menu: </strong>

<ul>

 <li><strong>Queen wooper </strong></li>

</ul>

<strong>$8.99 </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<strong> </strong>

<strong>— Restaurant City Sushi Profit = 0.0 </strong>

<strong>Menu: </strong>

<ul>

 <li><strong>City maki $4.99 </strong></li>

 <li><strong>City roll </strong></li>

</ul>

<strong>$6.99 </strong>

<ul>

 <li><strong>City sashimi </strong></li>

</ul>

<strong>$11.99 </strong>

<ul>

 <li><strong>City nigiri </strong></li>

</ul>

<strong>$3.99 </strong>

<ul>

 <li><strong>City teriyaki chicken </strong></li>

</ul>

<strong>$9.99 (SOLD OUT) </strong>

<strong> </strong>

<strong>— FoodApp AvoidThePlates 2 customer(s) registered: </strong>

<strong>-Customer Ellen Ripley </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="81e4ededf3e8f1c1e0eeedafe2eeec">[email protected]</a> </strong>

<strong>Address: 245 Alien road </strong>

<strong>-Customer John McClane </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="89e3e6e1e7eae6feebe6f0c9e1e6fde4e8e0e5a7eae6e4">[email protected]</a> </strong>

<strong>Address: 560 Yippee-ki-yay boulevard </strong>

<strong> </strong>

<strong>This email address already exists! </strong>

<strong> </strong>

<strong>Customer removed. </strong>

<strong>— FoodApp AvoidThePlates 1 customer(s) registered: </strong>

<strong>-Customer Ellen Ripley </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="ceaba2a2bca7be8eafa1a2e0ada1a3">[email protected]</a> </strong>

<strong>Address: 245 Alien road </strong>

<strong> </strong>

<strong>Customer added </strong>

<strong>— FoodApp AvoidThePlates 2 customer(s) registered: </strong>

<strong>-Customer Ellen Ripley </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a4c1c8c8d6cdd4e4c5cbc88ac7cbc9">[email protected]</a> </strong>

<strong>Address: 245 Alien road </strong>

<strong>-Customer John Copy </strong>

<strong>Email: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6c060304020f031b0e03152c040318010d0500420f0301">[email protected]</a> </strong>

<strong>Address: 560 Yippee-ki-yay boulevard </strong>

<h1>Phase 3: Order class</h1>

Next, implement the <strong>Order</strong> class.

The <strong>Order</strong> class should have:

<ul>

 <li>Seven instance variables: the order number (an <strong>int</strong>), the Customer who made the order, the Restaurant that receives the order, the FoodApp through which the order was placed, a list of food items ordered (stored as an array of <strong>FoodItem</strong>), the total number of items ordered (an <strong>int</strong>), and the total price of the order (a <strong>double</strong>).</li>

 <li>A class constant to set the maximum number of items that can be ordered (an <strong>int</strong>). Set it to 10.</li>

 <li>A constructor that accepts three parameters, the Customer, the Restaurant and the FoodApp, and initializes the corresponding instances variables. The array of FoodItems will be a <u>partially filled array</u>. It should be initialized according to the maximum number of items that can be ordered, and be empty at the beginning. The total number of items ordered should be initialized accordingly. The total price shall be initialized to 0. The order number shall have 6 digits, and start with a 9. Every order should have a distinct order number, starting from 900001, then 900002, then 900003 and so on. You will need to add either an instance variable or a class variable to accomplish this (choose wisely).</li>

 <li>An <strong>addToOrder(FoodItem)</strong> method that adds the FoodItem received as a parameter to the FoodItem array, only if it is available (<em>e.</em> not sold out) and if there is space left in the array. If the FoodItem was added, the method returns true (it returns false otherwise). You can assume that the FoodItem belongs to the restaurant’s menu (no need to check if it’s on the menu). Don’t forget to update here: the amount in stock for the FoodItem (decrement by 1), the total price of the order, and the total number of items ordered.</li>

 <li>A <strong>toString</strong> method that returns a <strong>String</strong> containing the FoodApp name, the order #, the customer name, the Restaurant name, the list of items ordered and the total price (formatting it exactly as shown in the example below). You will need to add some accessors in the previous classes (aka get methods) to get only the name of the Customer, FoodApp and Restaurant, instead of the full String representation of those.</li>

</ul>




You can test your class with TestPhase3.java.  You should get the output shown below:

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<strong>Total price: $0.0 </strong>

<strong> </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 </strong>

<strong>Total price: $11.99 </strong>

<strong> </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese $11.99 </strong></li>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<strong>Total price: $14.98 </strong>

<strong> </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<strong>Total price: $26.97 </strong>

<strong> </strong>

<strong>Could not add this item to the order: – Super extra steakhouse triple queen wooper with cheese </strong>

<strong>$11.99 (SOLD OUT) </strong>

<strong> </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<strong>Total price: $26.97 </strong>

<strong> </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 (SOLD OUT) </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<strong>Total price: $31.96 </strong>

<strong> </strong>

<strong>— SuperConsume order #900002 </strong>

<strong>For customer John McClane with restaurant City Sushi </strong>

<ul>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll </strong></li>

</ul>

<strong>$6.99 </strong>

<ul>

 <li><strong>City roll </strong></li>

</ul>

<strong>$6.99 </strong>

<ul>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll $6.99 </strong></li>

 <li><strong>City roll </strong></li>

</ul>

<strong>$6.99 </strong>

<ul>

 <li><strong>City roll </strong></li>

</ul>

<strong>$6.99 </strong>

<strong>Total price: $69.9 </strong>

<strong> </strong>

<h1>Phase 4: Adding some interactions between classes</h1>

In this phase, we will go back into previously defined classes and add a bit more functionality.




The <strong>FoodItem</strong> class should be updated with:

<ul>

 <li>A <strong>getMarkup</strong> method that returns the difference between the selling price and the cost of the FoodItem.</li>

</ul>




The <strong>FoodApp </strong>class should be updated with:

<ul>

 <li>An accessor (get method) for the fees percentage.</li>

</ul>




The <strong>Order</strong> class should be updated with:

<ul>

 <li>A <strong>submitOrder</strong> method that will simply call the fillOrder and the updateRecentOrders in the Restaurant and Customer classes respectively with the appropriate parameters (see details below).</li>

</ul>




The <strong>Restaurant</strong> class should be updated with:

<ul>

 <li>A <strong>fillOrder</strong> method that takes four parameters: the total price of the order, the array of FoodItems for the order, the number of FoodItems in the array, and the fees percentage taken by the FoodApp used for this order. This method updates the profit instance variable of the restaurant using the parameters representing the order. The profit on the order corresponds to the sum of markups on all the FoodItems minus the fees percentage paid to the FoodApp on the total price of the order. You can assume that the FoodItems array will not be empty.</li>

</ul>




The <strong>Customer</strong> class should be updated with:

<ul>

 <li>A new instance variable, which is a partially filled array of Orders, and stores only the 3 most recent orders.</li>

</ul>

The size of the array must be 3, and you can define a constant for that similarly to what we have done earlier.

<ul>

 <li>Adjust the constructor to initialize the array of Orders. It should be empty at the beginning.</li>

 <li>A <strong>updateRecentOrders(Order)</strong> which takes a new Order as a parameter, and adds it to the array of most recent orders. The rank of the orders should always be preserved, in such a way that we can print them from most recent to oldest. When the array is already full, update the array so that the oldest order gets removed and the most recent one gets added in, conserving the full ordering. This method should be very short, if you do it in more than 4-5 lines of code, rethink your approach.</li>

 <li>A <strong>getStringRecentOrders()</strong> which returns a String representation of the most recent orders, preceded by “Recent orders of customer [Customer name]”. Follow the formatting shown in the example below exactly. The orders must be ordered from most recent to oldest.</li>

</ul>




You can test your class with TestPhase4.java.  Don’t worry about the rounding errors that come with calculations with doubles for the profit (as long as you get the first two decimals correctly, it’s ok). You should get the output shown below:

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<ul>

 <li><strong>Queen wooper </strong></li>

</ul>

<strong>$8.99 </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<strong>Total price: $28.96 </strong>

<strong> </strong>

<strong>After submitting the order: </strong>

<strong>— Restaurant Burger Queen </strong>

<strong>Profit = 6.870000000000001 </strong>

<strong>Menu: </strong>

<ul>

 <li><strong>Queen wooper </strong></li>

</ul>

<strong>$8.99 </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<strong> </strong>

<strong>########CHECKING RECENT ORDERS BELOW </strong>

<strong> </strong>

<strong> </strong>

<strong>Recent orders of customer Ellen Ripley </strong>

<strong>— AvoidThePlates order #900001 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Super extra steakhouse triple queen wooper with cheese </strong></li>

</ul>

<strong>$11.99 </strong>

<ul>

 <li><strong>Fries </strong></li>

</ul>

<strong>$2.99 </strong>

<ul>

 <li><strong>Queen wooper </strong></li>

</ul>

<strong>$8.99 </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<strong>Total price: $28.96 </strong>

<strong> </strong>

<strong> </strong>

<strong>Recent orders of customer Ellen Ripley </strong>

<strong>— AvoidThePlates order #900004 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<strong>Total price: $4.99 </strong>

<strong>— SuperConsume order #900003 </strong>

<strong>For customer Ellen Ripley with restaurant City Sushi </strong>

<ul>

 <li><strong>City nigiri </strong></li>

</ul>

<strong>$3.99 </strong>

<ul>

 <li><strong>City sashimi </strong></li>

</ul>

<strong>$11.99 </strong>

<strong>Total price: $15.98 </strong>

<strong>— SuperConsume order #900002 </strong>

<strong>For customer Ellen Ripley with restaurant Burger Queen </strong>

<ul>

 <li><strong>Poutine </strong></li>

</ul>

<strong>$4.99 </strong>

<strong>Total price: $4.99 </strong>