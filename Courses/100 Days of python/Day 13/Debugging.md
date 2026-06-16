```
year = int(input("Whats your year of birth?"))

if year >= 1980 and year <= 1994:
    print("You are a millennial.")
elif year > 1994:
    print("you are a gen z.")
```

## Except error

```
try:
    age = int(input("Enter your age: "))
except ValueError:
    print("You have types in a invalid format, please try again with a numeriacal response.")
    age = int(input("Enter your age: "))

if age > 18:
    print(f"You can drive at the age of {age}.")
else:
    print(f"You cannot drive at the age of {age}, you need to at least 18 years old.")
```

## Print 

```
words_per_page = 0
pages = int(input("Number page: "))
words_per_page = int(input("Number of words per page:"))
total_words = pages * words_per_page
print(total_words)
print(pages)
print(words_per_page)
```