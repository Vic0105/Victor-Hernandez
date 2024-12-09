# Victor-Hernandez 
No team members
12/8/23
Programming Approaches
Modular Arithmetic,String Manipulation,Dynamic Input, and Efficiency
Basic Instructions on How to Use the Program
Launching the Program:

Run the compiled C++ program executable.
Input Requirements:

Enter the plaintext message when prompted.
Enter the keyword when prompted.
Using the Program:

The program will encrypt the plaintext using the provided keyword and display the ciphertext.
The program will then decrypt the ciphertext back to plaintext and display the original message.
Output:

The program will show both the encrypted message (ciphertext) and the decrypted message (plaintext).
My code:

START

// Input
PRINT "Enter the plaintext:"
INPUT plaintext
PRINT "Enter the keyword:"
INPUT keyword

// Convert to uppercase
plaintext = TO_UPPERCASE(plaintext)
keyword = TO_UPPERCASE(keyword)

// Repeat keyword to match length of plaintext
keyLength = LENGTH(keyword)
plaintextLength = LENGTH(plaintext)
repeatedKey = ""
FOR i = 0 TO plaintextLength - 1
    repeatedKey += keyword[i MOD keyLength]
END FOR

// Encryption
PRINT "Encrypting message..."
ciphertext = ""
FOR i = 0 TO plaintextLength - 1
    P = ASCII_VALUE(plaintext[i]) - ASCII_VALUE('A')
    K = ASCII_VALUE(repeatedKey[i]) - ASCII_VALUE('A')
    C = (P + K) MOD 26
    ciphertext += CHARACTER(C + ASCII_VALUE('A'))
END FOR
PRINT "Ciphertext: " + ciphertext

// Decryption
PRINT "Decrypting message..."
decryptedText = ""
FOR i = 0 TO plaintextLength - 1
    C = ASCII_VALUE(ciphertext[i]) - ASCII_VALUE('A')
    K = ASCII_VALUE(repeatedKey[i]) - ASCII_VALUE('A')
    P = (C - K + 26) MOD 26
    decryptedText += CHARACTER(P + ASCII_VALUE('A'))
END FOR
PRINT "Decrypted text: " + decryptedText

END
