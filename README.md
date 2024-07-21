# ciphertext
alphabet = ['a', 'b','c', 'd', 'e', 'f', 'g', 'h', 'i', 'j','k',
            'l', 'm', 'n', 'o', 'p' 'q', 'r', 't', 'u', 'v', 'w', 'x', 'y', 'z']

direction = input("Type 'encode' to encrpty, type 'decode' to decrept:\n")

text = input("Type your message:\n").lower()
shift = int(input("Type the shift number:\n"))

def encrypt(plain_text, shift_amount):
    cipher_text = ""
    for letter in plain_text:
        if letter in alphabet:
            position = alphabet.index(letter)
            new_postion = position + shift_amount
            new_letter = alphabet[new_postion]
            cipher_text += new_letter
        else:
            cipher_text += letter
    print(f"The encoded text is {cipher_text}")

def decrypt(cipher_text, shift_amount):
    plain_text =""
    for letter in cipher_text:
        if letter in alphabet:
            postion = alphabet.index(letter)
            new_postion = postion -  shift_amount
            plain_text += alphabet[new_postion]    
        else:
            plain_text += letter
    print(f"The decoded text is {plain_text}")

        
if direction == 'encode':
    encrypt(plain_text=text, shift_amount=shift)
elif direction == 'decode':
    decrypt(cipher_text=text, shift_amount=shift)
else:
    print("Invalid direction. Please type 'encode' or 'decode'. ") 

