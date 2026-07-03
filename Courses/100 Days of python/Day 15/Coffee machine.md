```
MENU = {
    "espreesso": {
        "ingredients": {
            "water": 200,
               "coffee":18
        },
        "cost":1.5
    },
    "latte": {
        "ingredients": {
            "water": 200,
              "milk": 150,
               "coffee":24
        },
        "cost":2.5
    },
    "cappuccino": {
        "ingredients": {
            "water": 250,
              "milk": 100,
               "coffee":24
        },
        "cost":3.0
    }
}
money = 0
resources = {
    "water":500,
    "milk":300,
    "coffee":100
}

def materials_left(ordered_drink):
      for item in ordered_drink:
        if ordered_drink[item] >= resources[item]:
            print(f"Sorry the machine does not have enough {item}.")
            return False
        return True

def process_coins():
    print("Please insert coins: ")
    total = int(input("how many quaters? ")) *0.25
    total += int(input("how many dimes? ")) *0.10
    total += int(input("how many nickles? ")) *0.05
    total += int(input("how many pennies? ")) *0.01
    return total

def make_coffee(drink_name,ordered_ingredients):
    for item in ordered_ingredients:
        resources[item] -= ordered_ingredients[item]
    print(f"Here is your {drink_name}")



def is_transcation_successful(money_received,cost_of_drink):
    if money_received >= cost_of_drink:
        change = round(money_received - cost_of_drink, 2)
        print(f"Here's the change ${change}")
        global money
        money += cost_of_drink
        return True
    else:
        print("Sorry that's not enough money. Money refunded")
        return False
    
is_on = True
while is_on:
    command = input("What would you like to have? Espreesso/Latte/Cappuccino? ").lower()
    if command == "off":
        is_on = False
    elif command == "report":
        print(f"Water: {resources['water']}ml")
        print(f"Milk: {resources['milk']}ml")
        print(f"Coffee: {resources['coffee']}g")
        print(f"Money: ${money}")
    else:
        drink = MENU[command]
        if materials_left(drink['ingredients']):
            payment = process_coins()
            if is_transcation_successful(payment,drink['cost']):
                make_coffee(command,drink['ingredients'])
```