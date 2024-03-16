## Hill_Cipher
## AIM:
To develop a simple Python program to implement Hill Cipher.

## DESIGN STEPS:
Step 1:
Design of Hill Cipher algorithnm

Step 2:
Implementation using C or python code

Step 3:
Testing algorithm with different key values.

## PROGRAM:
```
import numpy as np

# Key matrix
key_matrix = np.array([[17, 17, 5],
                       [21, 18, 21],
                       [2, 2, 19]])

# Function to convert text to numbers
def text_to_numbers(text):
    return [ord(char) - ord('a') if char.islower() else ord(char) - ord('A') for char in text if char.isalpha()]

# Function to convert numbers to text
def numbers_to_text(numbers):
    return ''.join([chr(num + ord('a')) for num in numbers])

# Function to encrypt plaintext
def encrypt(plaintext):
    # Convert plaintext to numbers
    numbers = text_to_numbers(plaintext)
    
    # Padding if necessary
    while len(numbers) % 3 != 0:
        numbers.append(25)  # Padding with 'z'
    
    # Reshape numbers into matrix form
    matrix = np.array(numbers).reshape(-1, 3)
    
    # Perform encryption
    encrypted_matrix = np.dot(matrix, key_matrix) % 26
    
    # Convert encrypted matrix back to numbers
    encrypted_numbers = encrypted_matrix.flatten().tolist()
    
    # Convert numbers back to text
    encrypted_text = numbers_to_text(encrypted_numbers)
    
    return encrypted_text

# Example usage
plaintext = "pay more money"
encrypted_text = encrypt(plaintext)

print("Plaintext:", plaintext)
print("Encrypted Text:", encrypted_text)

```

## OUTPUT:
![image](https://github.com/divz2711/Hill_Cipher/assets/121245222/2b1a6a85-9a1b-48b4-a180-4820521822bb)

## RESULT:
The program is executed successfully
