# NP HTML5, CSS3, and JavaScript 6e Tutorial 14, Case Problem 3


## Description:
```

1.  Use your editor to open the rb_pizza_txt.html and rb_build_txt.js files from the html14 > case3 folder. Enter your name and the date in the comment section of each file, and save them as rb_pizza.html and rb_build.js respectively.

2.  Go to the rb_pizza.html file in your editor. Link the file to the rb_build.js file, loading that file asynchronously.

3.  Take some time to study the elements in the web form, noting the IDs and classes associated with each element. Save your changes to the file and then go to the rb_build.js file in your editor.

4.  Directly below the initial comment section, create an object literal named pizzaPrice that will store the price of individual pizza components. Add the following properties and values to the object literal:
    •  size12 with a value of 11, size14 with a value of 13, and size16 with a value of 16 (the prices of 12", 14", and 16" pizzas)
    •  stuffed with a value of 3 and pan with a value of 2 (the additional price of stuff-crust and pan-style pizzas)
    •  doublesauce with a value of 1.5, doublecheese with a value of 1.5, and topping with a value of 1.5 (the prices for double sauce, double cheese, and additional pizza toppings.)

5.  Create a constructor function for the cart object class. The cart object class has two properties: the totalcost property, which stores the total cost of the items in the cart and the items array, which stores the items in the cart. Set the initial value of the totalCost property to 0 and set the items property to an empty array.

6.  Create a constructor for the foodltem object class. Add two properties to the class: the price property storing the price of the food item, and the qty property storing the quantity of the food item ordered. Do not specify a value for the properties.

7.  Add the following methods to the cart and foodItem prototypes:
    a.  Add calcItemcost() to foodItem prototype. Have the method return the product of the price property multiplied by the qty property. (Hint: Use the this keyword to reference the foodItem object.)
    b.  Add calccarttotal() to the cart prototype. Have the method, which calculates the cartTotal (the total cost of all items ordered), loop through the contents of the items array and apply the calcItemCost() method to each item in the array. Store the sum of the item costs in the totalCost property and return that value.
    c.  Add addTocart() to the foodItem prototype. The method has a single parameter named cart representing the shopping cart to which the item should be added. Use the push() Array method to add the foodItem object to the items array of the cart. (Hint: Use the this keyword to reference the foodItem object.)
    d.  Add removeFromcart() to the foodItem prototype. The method has a single parameter named cart representing the shopping cart from which the item should be removed. Loop through the items array in the cart object and for each item test whether it is equal to the foodItem object. If it is, use the splice() method to remove the object from the items array and break off the for loop. (Hint: Use the this keyword to reference the foodItem object and use the splice(index, 1) to remove the foodItem where index is the counter variable in the for loop.)

8.  Create the following constructors for pizzas and toppings on pizzas:
    a. Create a constructor for the pizza object class. Add the following properties to the class: size (for the size of the pizza), crust (for the crust style), doublesauce and doublecheese (to indicate whether pizza has double sauce or double cheese), and the toppings property (for storing the array of topping items on the pizza). Do not set an initial value for the size, crust, doubleSauce, or doubleCheese properties. Set toppings to an empty array. 
    b. Create a constructor for the topping object class. Add the name property for storing the name of the topping, and the side property for recording whether the topping should be across the full pizza, or only on the left or right side. Do not set an initial value for either property.

9. Have both the pizza and topping object class inherit the properties and methods of any food item by making their prototypes instances of the foodItem object.

10.  Add the addTopping() method to the pizza object prototype. The method has a single param¬eter named "topping". Use the push() Array method to add topping to the toppings array of the pizza.

11.  Add the calcPizzaPrice() method to the pizza prototype. The purpose of this method is to calcu¬late the total price of the pizza with all of its selected options. Add the following commands to the method:
    a.  Based on the value of the size property, set the value of the pizza's price property to either the value of the size12, size14, or size16 property of the pizzaPrice object you created in Step 4.
    b.  If the pizza crust equals "stuffed" or "pan", increase the value of the price property by the cor-responding value of the stuffed or pan properties of the pizzaPrice object.
    c.  If the doubleSauce or doubleCheese values are true, increase the price by the corresponding value of the doubleSauce or doubleCheese properties of the pizzaPrice object.
    d.  Loop through the contents of the toppings array and for each topping, calculate the qty prop erty of the topping multiplied by the value of the topping property of pizzaPrice. Add the value to the pizza's price.
    e.  Return the final calculated value of the price property.


12.  Now that you've defined the custom objects for ordering pizzas, scroll down to the event listener for the load event. Alice has already nested the buildPizza() and addPizzaToCart() functions in the event listener but you will have to complete these functions to create a working shopping cart page. Directly before the buildPizza() function, insert the following commands: 
    a.  Declare the mycart variable as an instance of a cart object.
    b.  Run the addPizzaToCart() function when the addToCartButton form button is clicked.

13. Go to the buildPizza() function that builds the pizza based on the values entered into the web form. The function has a single parameter, newPizza, which represents a new pizza that will be created based on the customer's choices. Add commands described in Steps 14 through 18 to the function.

14.  Set the qty property of newPizza to the selected value in the pizzaQuantityBox selection list. (Hint: Use the selectedValue() method that has been added to the Array prototype to return the value of the selected option in a selected list.)

15.  Set the size property of newPizza to the selected value in the pizzaSizeBox selection list. Set the crust property of newPizza to the selected value in the pizzaCrustBox selection list.

16.  Set the doubleSauce and doubleCheese properties of newPizza to the checked properties of the doubleSauceBox and doubleCheeseBox check boxes.

17.  Declare the variable checkedtoppings, which contains all the topping option buttons that have been checked by the user. (Hint: Use the CSS selector input.topping:checked to create the object collection.)

18.  Loop through the option buttons in checkedToppings and for each option, test whether the option button value is not equal to "none". If true, then do the following:
    a.  Declare mytopping as an instance of the topping object class.
    b.  Set the name property of myTopping to the name of the option button and set the side property of myTopping to the value of the option button.
    c.  If option button value is "full", then set the qty property of myTopping to 1, otherwise set the value of the qty property to 0.5.
    d.  Apply the addTopping() method to add myTopping to newPizza.

19. Next, you will complete the function that adds a pizza to the shopping cart. Go to the addPizzaToCart() function and insert the commands described in Steps 20 through 26.

20.  Declare the myPizza variable as an instance of the pizza object class. Call the buildPizza() func¬tion to build the ingredients of myPizza and then apply the addToCart() method to myPizza to add myPizza to myCart.

21.  Items in the shopping cart are displayed in table rows of the body section of the cartTable table. Create the following table row structure, saved under the variable newltemRow <tr> <td>summary</td> <td>gty</td> <td>price</td> <td> <input type="button" value="X" /> </td>  </tr> where summary is the text content of the pizzaSummary element, qty is the value of the qty property for myPizza, and price is the value returned by the calcPizzaPrice() method applied to myPizza. Format price as U.S. currency using the toLocaleString() method described in Tutorial 13. Give the element node for the input button, the variable name removeButton.

22.  Append newItemRow to the cartTableBody element.

23.  The cartTotalBox input box displays the total cost of the order. Set the value of cartTotalBox to the value returned by the calcCartTotal() method applied to my cart. Format the total cost as U.S. currency.

24.  Display the contents of myCart in the console log of your browser's debugger.

25.  Alice wants customers to be able to remove items from the shopping cart by clicking the removeItem button created in Step 21. Add an onclick event handler to removeButton that does the following:
    a.  Applies the removeFromCart() method to myPizza to remove myPizza from myCart.
    b.  Removes the newItemRow from cartTableBody.
    c.  Changes the value of cartTotalBox to the value returned by the calcCartTotal() method applied to myCart (now with the removed pizza item). Displays the new total as U.S. currency. 
    d.  Displays the revised contents of myCart in the debugger console log.

26.  Call the resetDrawPizza() function to restore the web form controls to their original appearances.

27.  Document your work on the order application with descriptive comments and then save your work.

28.  Open rb_pizza.html in your browser. Verify that you can add pizza selections to the shopping cart using the web form controls and that they will appear in the shopping cart table. Further verify that as you add and remove items from the shopping cart by clicking the "X" button, the contents of myCart, as displayed in the debugger console, are similarly updated to reflect the new shopping cart contents.


```