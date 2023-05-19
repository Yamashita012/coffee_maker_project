# coffee_maker_project
This is a simulation of a coffee making machine, it allows you to make 3 different flavors of coffee {Latte, Cappuccino, Espresso} and also allows you to view the resources left to make your coffee.

# Coffee Shop Application

The provided Python script is an interactive coffee shop application that allows users to place drink orders, process payments, and prepare the requested beverages. It utilizes the following modules:

- `Menu`: Manages the menu options and drink selection.
- `MenuItem`: Represents a single drink item with its name, ingredients, and cost.
- `CoffeeMaker`: Models the coffee-making machine and handles the resources required for drink preparation.
- `MoneyMachine`: Simulates the money processing system, handling payments and providing change.

## Usage

1. Import the necessary classes from the respective modules:

```python
from menu import Menu, MenuItem
from coffee_maker import CoffeeMaker
from money_machine import MoneyMachine
```

2. Create instances of the required classes:

```python
my_money_machine = MoneyMachine()
my_coffee_maker = CoffeeMaker()
menu = Menu()
```

3. Start the coffee shop application by setting the `is_on` flag to `True`:

```python
is_on = True
```

4. Enter the main loop, where the user can select options from the menu:

```python
while is_on:
    options = menu.get_items()
    choice = input(f"What would you like? ({options}): ").lower()

    if choice == "off":
        is_on = False

    elif choice == "report":
        my_money_machine.report()
        my_coffee_maker.report()

    else:
        drink = menu.find_drink(choice)
        if my_coffee_maker.is_resource_sufficient(drink):
            if my_money_machine.make_payment(drink.cost):
                my_coffee_maker.make_coffee(drink)
```

The application provides the following functionality:

- Entering "off" shuts down the application.
- Entering "report" generates reports for the money machine and coffee maker, displaying available resources and financial information.
- Choosing a drink option deducts the required resources from the coffee maker, processes the payment using the money machine, and prepares the selected beverage if sufficient resources are available.

Note: Ensure that the `MenuItem` and `Drink` classes, referred to in the code, are defined appropriately with the necessary attributes.

## Disclaimer

Please be aware that this script provides a simplified demonstration of a coffee shop application and does not include all functionalities and edge cases that a real-world application would require. It serves as a starting point for building a more comprehensive system to handle various scenarios and additional features.
