# coffee_maker_project
This is a simulation of a coffee making machine, it allows you to make 3 different flavors of coffee {Latte, Cappuccino, Espresso} and also allows you to view the resources left to make your coffee.


# Coffee Maker

The `CoffeeMaker` class models a coffee-making machine. It allows you to check the availability of resources, make coffee orders, and deduct the required ingredients from the available resources.

## Usage

Instantiate a `CoffeeMaker` object to create a coffee-making machine with initial resource quantities. The available resources include water, milk, and coffee. Here's an example:

```python
coffee_machine = CoffeeMaker()
```

### Reporting Resources

You can print a report of the available resources using the `report()` method. It provides the current quantities of water, milk, and coffee in milliliters (ml) and grams (g), respectively.

```python
coffee_machine.report()
```

### Checking Resource Sufficiency

To determine if a coffee order can be fulfilled based on the available resources, use the `is_resource_sufficient(drink)` method. Pass the drink object as an argument, which should have an `ingredients` attribute containing the required resources. The method returns `True` if the order can be made or `False` if the ingredients are insufficient.

```python
if coffee_machine.is_resource_sufficient(drink):
    print("Order can be made.")
else:
    print("Insufficient resources for the order.")
```

### Making Coffee

To make coffee, use the `make_coffee(order)` method. Pass the order object as an argument, which should have a `name` attribute representing the drink name and an `ingredients` attribute containing the required resources. The method deducts the required ingredients from the available resources and outputs a message indicating the prepared drink.

```python
coffee_machine.make_coffee(order)
```

## Example

Here's an example demonstrating the usage of the `CoffeeMaker` class:

```python
# Instantiate a CoffeeMaker object
coffee_machine = CoffeeMaker()

# Print resource report
coffee_machine.report()

# Create a drink order
order = Drink("Latte", {"water": 50, "milk": 100, "coffee": 25})

# Check resource sufficiency
if coffee_machine.is_resource_sufficient(order):
    # Make coffee
    coffee_machine.make_coffee(order)
else:
    print("Insufficient resources for the order.")
```

Please note that the `Drink` class used in the example is not provided in the code. You would need to define it separately with the appropriate attributes for the drink name and required ingredients.
