# XOR

XOR *(Exclusive OR)* is a logical operation that outputs true (1) only when
inputs differ. It's a fundamental binary operation with important applications
in computer science and cryptography.

| A | B | A XOR B |
| - | - | ------- |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

For example, to encrypt the word "HELLO" using the key "KEY", you should first
convert `HELLO` to binary...

* `H` (ASCII 72): `01001000`
* `E` (ASCII 69): `01000101`
* `L` (ASCII 76): `01001100`
* `L` (ASCII 76): `01001100`
* `O` (ASCII 79): `01001111`

...then convert `KEY` to binary...

* `K` (ASCII 75): `01001011`
* `E` (ASCII 69): `01000101`
* `Y` (ASCII 89): `01011001`

...and finally do the encryption - XOR each character with key, repeating the
key as many times as necessary:

* `H ⊕ K`: `01001000 ⊕ 01001011` = `00000011` (ASCII 3)
* `E ⊕ E`: `01000101 ⊕ 01000101` = `00000000` (ASCII 0)
* `L ⊕ Y`: `01001100 ⊕ 01011001` = `00010101` (ASCII 21)
* `L ⊕ K`: `01001100 ⊕ 01001011` = `00000111` (ASCII 7)
* `O ⊕ E`: `01001111 ⊕ 01000101` = `00001010` (ASCII 10)

The resulting ciphertext are all ASCII non-printable characters with values 3,
0, 21, 7 and 10. If a malicious attacker intercepts this encrypted text, he
won't see anything, because all charachers are non-printable.

To decrypt the ciphertext you should XOR ciphertext with same key:

* `3 ⊕ K`: `00000011 ⊕ 01001011` = `01001000` (ASCII 72: H)
* `0 ⊕ E`: `00000000 ⊕ 01000101` = `01000101` (ASCII 69: E)
* `21 ⊕ Y`: `00010101 ⊕ 01011001` = `01001100` (ASCII 76: L)
* `7 ⊕ K`: `00000111 ⊕ 01001011` = `01001100` (ASCII 76: L)
* `10 ⊕ E`: `00001010 ⊕ 01000101` = `01001111` (ASCII 79: O)

In real world applications, reusing the same key for multiple messages is
vulnerable to frequency analysis and known-plaintext attacks. XOR doesn't hide
patterns well without proper key management - the key should be at least as
long as the message for good security. But, for educational purposes to
understand cryptographic concepts, and basic data protection where security
isn't critical, the XOR is perfect!

## Simple assignment

Create a console application in any programming language to encrypt and decrypt
messages using the XOR operation.

The allowed alphabet for messages (for plaintext and for the key) can include
only lowercase letters of the English alphabet:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

Spaces, uppercase letters, numbers, and other characters are not allowed.

In the first line of the user input there will be a message `m` no longer than
one hundred ASCII characters for plaintext or 800 bits for ciphertext, in the
second line there will be a key `k` no longer than five characters, and in the
third line there will be an integer `s`, which represents the operation. If
$s=1$ then `m` is plaintext and should be encrypted, and if $s=2$, then `m` is
ciphertext in binary and should be decrypted.

### Test example 1

If the input is:

```text
nikolatesla
ser
1
```

the output should be:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
```

### Test example 2

If the input is:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
ser
2
```

the output should be:

```text
nikolatesla
```

## Start the assignment

**---===[ EMBED OR LINK THE GRADER ]===---**

## Solution hints

Each character is stored in memory as an 8-bit ASCII value (for lowercase
letters a–z, the codes range from 97 to 122). To encrypt a character, take its
ASCII value and the ASCII value of the corresponding key character (cycling
through the key), apply XOR (^) between them and output the result as an 8-bit
binary number.

To decrypt, follow the reverse process, take each 8-bit binary block from
ciphertext, convert it back to an integer (0–255), XOR with the ASCII value of
the corresponding key character and convert the result back to a character.

## Advanced XOR Assignments (optional)

### Expand the allowed alphabet

Allow lowercase and uppercase letters, spaces, numbers, and punctuation.
Non-letter characters are XORed with the key in the same way.

## Use functions

Create two functions: `encrypt()` for encrypting messages and `decrypt()` for
decrypting messages. Use the created functions in your main program.

### Create a Class

Create an `XorCipher` class that:

* Stores the key,
* Provides `encrypt()` and `decrypt()` methods,
* Optionally includes a private helper to repeat the key over the message length.

Use the created class in your main program.

### Accept Command Line Arguments

Instead of waiting for the user input, create a console application that
accepts the following command line arguments:

1. argument `m` for specifying the message,
2. argument `k` for specifying the key, and
3. argument `s` for specifying the operation (`1` to encrypt, `2` to decrypt).

### Encrypt and Decrypt Files

Use the knowledge you gained so far to create a program that can:

* read plaintext or binary ciphertext from a file,
* encrypt or decrypt it with a given key, and
* write the result back to a new file.
