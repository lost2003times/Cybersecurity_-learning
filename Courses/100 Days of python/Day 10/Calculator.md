```

def addition(n1,n2):
    return n1 + n2
def subtract(n1,n2):
    return n1 - n2
def divide(n1,n2):
    return n1/n2
def multiply(n1,n2):
    return n1*n2

operations = {"+":addition,"-":subtract,"/":divide,"*":multiply}
def calculator():
    
    should_accumulate = True
    num1 = float(input("Enter the first number: \n"))
    while should_accumulate:
        for symbols in operations:
            print(symbols)
        operation_symbol = input("Enter the operation symbol: ")
        num2 = float(input("Enter the second number: \n"))
        answer = operations[operation_symbol](num1,num2)
        print(f"{num1}{operation_symbol}{num2} = {answer}")
        print(answer)
        
        
        choice = input("Do you want to continue: 'y' or 'n' : ")
        if choice == "y":
            num1 = answer
        else:
            should_accumulate = False

calculator()
```

