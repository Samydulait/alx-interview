# 0x04 utf8 Validation

## Project Tasks

```0. UTF-8 Validation```

Write a method that determines if a given data set represents a valid UTF-8 encoding.

* Prototype: def validUTF8(data)
* Return: True if data is a valid UTF-8 encoding, else return False
* A character in UTF-8 can be 1 to 4 bytes long
* The data set can contain multiple characters
* The data will be represented by a list of integers
* Each integer represents 1 byte of data, therefore you only need to handle the 8 least significant bits of each integer

```bash
carrie@ubuntu:~/0x04-utf8_validation$ cat 0-main.py
# !/usr/bin/python3
"""
Main file for testing
"""

validUTF8 = __import__('0-validate_utf8').validUTF8

data = [65]
print(validUTF8(data))

data = [80, 121, 116, 104, 111, 110, 32, 105, 115, 32, 99, 111, 111, 108, 33]
print(validUTF8(data))

data = [229, 65, 127, 256]
print(validUTF8(data))

carrie@ubuntu:~/0x04-utf8_validation$
carrie@ubuntu:~/0x04-utf8_validation$ ./0-main.py
True
True
False
carrie@ubuntu:~/0x04-utf8_validation$
```

File: 0-validate_utf8.py

UTF-8 Encoding: UTF-8 (Unicode Transformation Format - 8-bit) is a variable-length character encoding that is widely used to represent Unicode characters. Unicode is a universal character set that includes characters from various writing systems and covers almost all the world's writing scripts
In UTF-8 encoding, characters can be represented using one to four bytes, depending on their code point (unique numeric value assigned to each character in the Unicode standard). Here are the rules for encoding characters in UTF-8
 1. Single-byte characters: Characters with code points from 0 to 127 are represented using a single byte. The most significant bit (MSB) of the byte is always 0, indicating a single-byte character
 2. Multi-byte characters: Characters with code points above 127 are represented using multiple bytes. The first byte starts with a pattern of 1s followed by a 0 (e.g., 110xxxxx for two-byte characters, 1110xxxx for three-byte characters, and 11110xxx for four-byte characters). Subsequent bytes in a multi-byte character start with the pattern 10xxxxxx
 3. Overlong encoding: To prevent issues with backward compatibility, UTF-8 prohibits overlong encoding, which means representing a character with more bytes than necessary

