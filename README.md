# VIGENERE-CIPHER
## EX. NO: 1(D)
 

## IMPLEMETATION OF VIGENERE CIPHER
 

## AIM:

To implement the Vigenere Cipher substitution technique using C program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:

STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.

STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.

STEP-3: Repeat this process for all 26 rows and construct the final key matrix.

STEP-4: The keyword and the plain text is read from the user.

STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.

STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.

STEP-7: The junction character where these two meet forms the cipher character.

STEP-8: Repeat the above steps to generate the entire cipher text.

## Program :

Name : Muthulakshmi D
Reg : 212223040122
```
def vigenere_encrypt(text, key):
    text_len = len(text)
    key_len = len(key)
    encrypted_text = list(text)
    
    for i in range(text_len):
        c = text[i]
        if 'A' <= c <= 'Z':
            encrypted_text[i] = chr(((ord(c) - ord('A') + ord(key[i % key_len]) - ord('A')) % 26) + ord('A'))
        elif 'a' <= c <= 'z':
            encrypted_text[i] = chr(((ord(c) - ord('a') + ord(key[i % key_len]) - ord('A')) % 26) + ord('a'))
    
    return "".join(encrypted_text)

def vigenere_decrypt(text, key):
    text_len = len(text)
    key_len = len(key)
    decrypted_text = list(text)
    
    for i in range(text_len):
        c = text[i]
        if 'A' <= c <= 'Z':
            decrypted_text[i] = chr(((ord(c) - ord('A') - (ord(key[i % key_len]) - ord('A')) + 26) % 26) + ord('A'))
        elif 'a' <= c <= 'z':
            decrypted_text[i] = chr(((ord(c) - ord('a') - (ord(key[i % key_len]) - ord('A')) + 26) % 26) + ord('a'))
    
    return "".join(decrypted_text)

key = input("enter key:") 
message = input("\nenter plain text:")  

# Encrypt the message
encrypted_message = vigenere_encrypt(message, key)
print("\nEncrypted Message:", encrypted_message)

# Decrypt the message
decrypted_message = vigenere_decrypt(encrypted_message, key)
print("\nDecrypted Message:", decrypted_message)
```
## Output :
![424297893-b46b6bd6-03f0-49a9-b7f7-a64ae6aa5204](https://github.com/user-attachments/assets/f8e1e7f6-6714-4c47-beff-61f17814b1b0)

## RESULT
   The program is executed successfully

