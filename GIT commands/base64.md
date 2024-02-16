## Encoding Data with Base64
```
echo 'Base64 Linux Command' > file.txt
base64 file.txt

# Output:
# QmFzZTY0IExpbnV4IENvbW1hbmQK

```
## Decoding Data with Base64
```
echo 'QmFzZTY0IExpbnV4IENvbW1hbmQK' | base64 -d

# Output:
# Base64 Linux Command
```
## Encoding and Decoding Large Files
```
echo 'This is a large file.' > large_file.txt
base64 large_file.txt > encoded_file

# To decode the file
base64 -d encoded_file > decoded_file.txt
```
## Encoding and Decoding with Line Wrapping
```
echo 'This is a text with more than 76 characters. This is a text with more than 76 characters.' | base64 -w 0

# Output:
# VGhpcyBpcyBhIHRleHQgd2l0aCBtb3JlIHRoYW4gNzYgY2hhcmFjdGVycy4gVGhpcyBpcyBhIHRleHQgd2l0aCBtb3JlIHRoYW4gNzYgY2hhcmFjdGVycy4K
```
## Ignoring Non-Alphabet Characters
```
echo 'This is a text with some #@$% non-alphabet characters.' | base64 -i

# Output:
# VGhpcyBpcyBhIHRleHQgd2l0aCBzb21lICMkQCUgbm9uLWFscGhhYmV0IGNoYXJhY3RlcnMuCg==
```
## Alternative Methods for Encoding and Decoding Data
While the base64 command is a powerful tool in Linux, it’s not the only way to encode and decode data. 
There are other methods you can use, such as OpenSSL and Python. 
These alternatives can offer more flexibility or better suit your specific needs.

## OpenSSL: A Versatile Tool
OpenSSL is a robust, full-featured open-source toolkit that implements the Secure Sockets Layer (SSL) and 
Transport Layer Security (TLS) protocols. 
It also provides a general-purpose cryptography library, including an optional command line interface 
which can be used for base64 encoding and decoding.

Here’s an example of how to use OpenSSL to encode and decode data:

```
echo 'Base64 Linux Command' | openssl base64

# Output:
# QmFzZTY0IExpbnV4IENvbW1hbmQK

echo 'QmFzZTY0IExpbnV4IENvbW1hbmQK' | openssl base64 -d

# Output:
# Base64 Linux Command
```


### Reff this url for more
```
https://ioflood.com/blog/base64-linux-command/
```















