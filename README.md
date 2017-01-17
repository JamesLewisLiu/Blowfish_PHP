# Blowfish_PHP
Blowfish file encryption written in PHP

This is an implementation of the Blowfish file encryption in PHP without using its built-in function.

### Specs
Adds a CRC at the end of file encryption which includes two 32-bit strings:   
  
1. The original length of the plaintext
2. The length after aligning the plaintext by adding zeroes to the end of the plaintext, and this is calculated as  
__$alignedLen = ($dataLen + 7) & 0xFFFFFFF8;__

Accordingly, the file decryption method will first specify if the input file meets the above format.

Encrypted file is saved under "$dir/Encrypted", while decrypted file gets saved under "$dir/Decrypted", and single backups are created.
