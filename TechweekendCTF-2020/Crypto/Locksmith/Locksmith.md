Locksmith

Can you find the key or will you force your way in?

Files: out_1.txt, generateOut.py

Writeup:
out_1.txt contains the encoded flag.
Looking at generateOut.py, we can see that a random key is generated, consisting of 4 numbers, 4 letters, and further 4 or 3 numbers.
The flag is xored with the key cyclically and the output written to out_1.txt

A property of xor is that if
P xor Q = R then
Q xor R = P and 
P xor R = Q

Hence we can find the flag by xoring the outfile with the key. But we don't have any key, so lets use the same random key generating function to bruteforce

```
def xor:
 ....

def keyGen:
 ....

msg = open("out_1.txt","r").read()

while 1 == 1:
	key = keyGen()
	flag = xor(msg,key)
	print(flag,key)
	if flag.startswith("TECHWKND"):
		break
```

After letting the code run for about 2 hundred thousand iterations, we look at the outputs.
In such iterations, where the first few characters of the key are `8000w`, the first few characters of the decoded flag come out to be `TECHW` which means we are getting closer to the right key.
Hence first five characters of the key are `8000w`

Fixing these characters in the keyGen function, we can continue brute forcing

```
def xor:
 ....

def keyGen:
	import random
	import string
	a = "8"
	b = "0"
	c = "0"
	d = "0"
	key = a + b + c + d
	e = "w"
	...... #rest is the same

msg = open("out_1.txt","r").read()

while 1 == 1:
	key = keyGen()
	flag = xor(msg,key)
	print(flag,key)
	if flag.startswith("TECHWKND"):
		break
```

After some iterations of the brute forcing, we get the flag

```TECHWKND{bR3Ak1Ng_&_3NtErIng_gGZ93}```
And the correct key is 8000weas952