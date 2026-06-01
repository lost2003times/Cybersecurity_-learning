```
alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
   
def ceaser(original_text,shifted_amount,encode_or_decode):
    output_text = ""
    
    if encode_or_decode == "decode":
        shifted_amount *= -1

    elif encode_or_decode == "encode":
        pass  
    
    for letter in original_text:
        if letter not in alphabet:
            output_text += letter    
        else:
            shifted_position = alphabet.index(letter) + shifted_amount
            shifted_position %= len(alphabet)
            output_text += alphabet[shifted_position]
    
    print(f"Your {encode_or_decode}d message is {output_text}.")

should_continue = True

while should_continue:

    direction = input("Type encode to encrypt or type decode to decrypt.\n").lower()
    if direction not in ["encode", "decode"]:
        print("Invalid choice.")
        continue
    message = input("Type your message.\n").lower()
    shift = int(input("Enter the shift: \n"))
    ceaser(message,shift,direction)

    go_on = input("Type yes or no depending on you want to continure or not.\n").lower()
    if go_on == "no":
        should_continue = False
```

