# TD2BlockchainPrograming



> hello.py:

This is a simple and interactive program that asks the user to input his name.
It prints "Hello [name]!"



> script1.py:

We need first to import the secrets and hashlib libraries. 
The first one is used to generate a 128-bit random number.
The second one allows us to use the `sha256()` function.

First, we generate a random number and convert it in binary.
We use the hash function `sha256()` and only keep the 4 first bits in binary.

Then, we make a string composed by:
- the 128-bit number,
- the 4-bit checksum,
so its length is exactly 132 bits.

We initialize `list`, containing 11 elements where the string is divided into 12-character substrings.

We input the BIP39 list of words (2048 words).

Each element of `list` is set into seed_words as integer and is replaced by the corresponding word.


