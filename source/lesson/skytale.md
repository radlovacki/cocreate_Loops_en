# Skytale

After completing this lesson, you will be able to:

* Explain how the Skytale cipher works.
* Implement encryption and decryption using simple array or string operations.
* Understand how physical encryption devices can be modeled digitally.

The Skytale is one of the oldest known tools for encryption, dating back to
ancient Greece around 400 BC. It was a simple cylindrical device used by the
Spartans to send secret messages during military campaigns.

A strip of parchment or leather was wound around a wooden rod (the *skytale*)
of a specific diameter. The message was then written lengthwise along the rod.
Once unwound, the letters appeared scrambled and meaningless. The recipient
needed a rod of the **exact same diameter** to wrap the strip and read the
original message.

If you want to encrypt the message:

```text
attackatdawn
```

and you choose a rod that allows **4 letters per turn**, you first write the
message vertically in columns, forming rows of length 4:

```text
a t t a
c k a t
d a w n
```

The ciphertext is then created by reading row by row:

```text
acdtkatawatn
```

To decrypt, the receiver rewinds the strip around a rod of the same diameter
and reads vertically again to reconstruct the original message.

## Simple assignment

Create a console application in any programming language to encrypt and decrypt
messages using the Skytale cipher.

The allowed alphabet for messages includes only the lowercase letters of the
English alphabet:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Spaces, uppercase letters, numbers, and other characters are not allowed.

In the first line of the user input there will be a message `m` no longer than
one hundred characters. In the second line there will be an integer `k` (the
number of columns – circumference of the rod). In the third line there will be
an integer `s`, which represents the operation. If $s=1$, then `m` should be
encrypted. If $s=2$, then `m` should be decrypted.

### Test example 1

If the input is:

```text
attackatdawn
4
1
```

the output should be:

```text
acdtkatawatn
```

### Test example 2

If the input is:

```text
acdtkatawatn
4
2
```

the output should be:

```text
attackatdawn
```

## Start the assignment

**---===[ EMBED OR LINK THE GRADER ]===---**

## Solution hints

For **encryption**, write the plaintext vertically into a table with `k`
columns. Read the table row by row to form the ciphertext. For **decryption**,
write the ciphertext row by row into a table with `k` columns, read the table
vertically to reconstruct plaintext.

## Advanced Skytale Assignments (optional)

### Expand the allowed alphabet

Include uppercase letters, spaces, numbers, and punctuation.

### Use functions

Create `encrypt()` and `decrypt()` functions to keep the code modular.

### Create a Class

Implement a `SkytaleCipher` class that stores `k` and provides methods for
encryption and decryption.

### Encrypt and Decrypt Files

Modify the program to read plaintext or ciphertext from a file and write
results to another file.

### Handle incomplete rows

Modify your program so that if the last row is shorter than `k`, it still
encrypts and decrypts correctly by handling missing characters or padding.
