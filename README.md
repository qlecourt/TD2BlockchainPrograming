# TD2BlockchainPrograming


> program.py

**How to use:**

The user can choose to create a random mnemonic seed or to check a seed. 
In the second case, it needs to get the 12 words to check if the key is valid or not. 
If the key is valid, the user can ask to extract the master private key and the master chain code. 
Then, the user selects if he wants to generate a child key with the index only or with a level of derivation (M should be greater than 1). 
The program prints the important informations at the end of each step.



**Details:**

This file contains:
- 2 imported libraries;
- the BIP39 list of 2048 words;
- the user-defined functions, the 1st one is the verification of 12 input words and keeps the table with the binary numbers corresponding to these words, an other function to hash with ths SHA512 algorithm and a last one to concatenate strings;
- a menu that asks the user to choose a functionality. If the users inputs a wrong number, it prints an error;
- a first part that creates a random mnemonic seed (cf. script1.py);
- a second part that calls the function `importSeedMnemonique()`;
- if it is True (the key is valid), the user can choose to keep going and extract the master key and the master chain code, which are respectively the first and last 256 bits of the hash obtained with `sha512()`.
- then the user can create a child key with an index or use a loop to get the desired level of derivation. To generate child keys and child indexes, we used the private key in the concatenation whereas it should be with the public key to make it easier.



> hello.py:

This is a simple and interactive program that asks the user to input his name.
It prints "Hello [name]!"


> script1.py:

We need first to import the secrets and hashlib libraries, secrets is used to create a random number and the second one allows us to use the `sha256()` function.

First, we generate a random number and convert it in binary. 
If it has a length smaller than 128, we add zeros on the left to get the correct length. 
We use the hash function `sha256()` and only keep the 4 first bits in binary.

Then, we make a string composed by:
- the 128-bit number,
- the 4-bit checksum, 
so its length is exactly 132 bits.

We initialize `list`, containing 12 elements where the string is divided into 11-character substrings.

We input the BIP39 list of words (2048 words).

Each element of `list` is set into seed_words as integer and is replaced by the corresponding word. 
We finally obtain a list of 12 words: the mnemonic seed.


