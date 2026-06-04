```
import os

bids = {}

should_continue = True
while should_continue:
    name = input("Enter your name: ")
    bid = float(input("Enter your bid: "))
    

    bids[name] = bid

    more_bidders = input("Are there any more bidders : 'yes' or 'no' ").lower()

    input("Press enter")
    os.system('cls' if os.name == 'nt' else clear)

    if more_bidders == "no":
        should_continue = False

winner =max(bids, key=bids.get)

print(f"The winning bid is {bids[winner]}, and the Winner is {winner}.")
```

