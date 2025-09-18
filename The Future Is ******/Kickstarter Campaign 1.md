# Kickstarter Campaign 1

These challenges are found in the original Kickstarter campaign, found here: <a href="https://www.kickstarter.com/projects/rekcah/the-future-is-from-rekcah-comics/description">Kickstarter</a>. There is also, according to the Discord, a challenge embedded into the image for the Kickstarter campaign. 

## Challenge 1

### Description of Challenge

Challenge 1 brings me this string, which appears to be binary:

> 01101000 01110100 01110100 01110000 01110011 00111010 00101111 00101111 01101101 01100011 01110100 01100110 00101110 01101001 > 01101111 00101111 00110110 01100110 00110101 01100010 00111001 00111001 01100110

Feeding it into <a href="dcode.fr/en">DCode</a> positively identifies it as such.  Decrypted, it yields the following URL:

> <a href="https://mctf.io/6f5b99f">https://mctf.io/6f5b99f</a>

Going to the URL yields the following message:

> Here's a small bonus for finding it: KEY{6f5b99f}. Submit it as a "Bonus" here.
> Solve the challenge below for additional points. The flag will be in format KEY{...}
> The comic is set in the future... can you prove to us that you belong here?
> Access the challenge here.

So I enter the bonus code in for **15** points. Then, I click on the link and it yields the following message:

>If you access this page using Chrome browser version 476, we'll give you the flag!
> The flag will be here, once you access this page from the correct browser.

So, knowing that I have to use a particular browser version, I fire up Chrome and go to the link. From there, I right-click on the page and "Inspect" it. From here, I navigate to the "Network conditions" section, which can be found under "More tools" in the three-dot menu within the Developer Tools window. In the "User agent" section, uncheck the "Use browser default" option. From the dropdown menu, select a predefined user agent string, such as one for a specific mobile device or browser version, or enter a custom user agent string. After making the selection, refresh the page to see the website respond to the new user agent.

When I refreshed the page, it shows: 

> Congrats! Flag: KEY{0fd1e52}

This is entered in as the key for the first of the Kickstarter challenges for **75** points.

### Solution

KEY{6f5b99f}

KEY{0fd1e52}

## Challenge 2

### Description of Challenge

Challenge 2 gives me the following string:

> QUJBQkIgQUFBQkEgQkFBQkEgQUFCQUIgLiBBQkFBQSBBQkJBQiAvIDEgQUFBQkEgNjUzIEFBQkFBIDE=

It is identified as a Base 64 string, and when decrypted on DCode, it yields:

> ABABB AAABA BAABA AABAB . ABAAA ABBAB / 1 AAABA 653 AABAA 1

I know that some challenges start with mctf.io and and others are tficomic.io, so I am on the right track. I then copy that new code and paste it right back into DCode's Cipher Identifier tool. It is identified as likely being a Bacon cipher. DCode deciphers it to be:

> MCTFIOCE

Plugging the numbers in, this yields <a href="mctf.io/1C653E1">mctf.io/1C653E1</a>. Going to that URL yields the following:

> Congratulations! You found a Kickstarter Challenge!
> Here's a small bonus for finding it: KEY{1c653e1}. Submit it as a "Bonus" here.
> Solve the challenge below for additional points. The flag will be in format KEY{...}:
> We received 3 encrypted messages, but we know that all of them have been encrypted with the same XOR key and that one of them > is the flag in format KEY{...}. Here are the messages:
>> 9d c2 d3 86 cf ee 9c 9f 68 d1 62
>> 95 e8 e7 94 9e f7 bf c0 62 dc 6c
>> 9d d4 dc 8a de bd bb 93 72 c8 74
> Can you decrypt them?

Before I go any further, I enter the Bonus key for **15** points. At this point, I got lazy and utilized ChatGPT to aid in the XOR decryption using prompts. It yielded the key KEY{29A03F}, which I then entered into the platform for **75** points.

### Solution

KEY{1c653e1}

KEY{29A03F}

## Challenge 3

### Description of Challenge

> 11 1010 1 0010 010101 00 111 10010 100 10000 1010 11000 00000 11110 0

Once again, I fed this cipher into <a href="dcode.fr/en">DCode</a>, and it tells me that the cipher is Morse code.  When I decrypted it in the siter, it yielded <a href="MCTF.IO/D6C759E">MCTF.IO/D6C759E</a>. Going to the aforementioned URL yielded the bonus KEY{d6c759e}, which is entered into the platform for **15** points. It also yielded another challenge: 

> We're trying to hack into this program.
> Can you find the passphrase it checks for?

It links to <a href="https://challenges.tficomic.io/d6c759ed5c7e84c814af857d322ada5a/quantum_leaf.py">https://challenges.tficomic.io/d6c759ed5c7e84c814af857d322ada5a/quantum_leaf.py</a>. When I download it, it shows me the following code:
```
print("Quantum Leaf Login")
passphrase = input("Please provide the passphrase to login: ")
print()

def check_passphrase(p):
    c = "LZC:36|B@6zD"
    if len(p) != len(c):
        return False
    return c == "".join([chr(ord(i)+1) for i in p[::2]] + [chr(ord(i)-1) for i in p[::-2]])

if check_passphrase(passphrase):
    print("You are logged in. The passphrase is correct!")
else:
    print("Incorrect. Please try again.")
```
Right off the bat, I can see c is the length of the word that I am looking for, which is 12.
```
c = "LZC:36|B@6zD"
c (hex/positions):  0 1 2 3 4 5  6  7  8  9 10 11
chars:              L Z C : 3 6  |  B  @  6  z  D

p_even[i] = chr(ord(c[i]) - 1) for i = 0..5
→ ['K', 'Y', 'B', '9', '2', '5']

p_rev_even[j] = chr(ord(c[6+j]) + 1) for j = 0..5
→ ['}', 'C', 'A', '7', '{', 'E']

p[0] = 'K', p[2] = 'Y', p[4] = 'B', p[6] = '9', p[8] = '2', p[10] = '5'

p[11] = '}', p[9] = 'C', p[7] = 'A', p[5] = '7', p[3] = '{', p[1] = 'E'
```

This yields a solution: KEY{B79A2C5}, which is entered into the platform for **75** points.

### Solution

KEY{d6c759e}

KEY{B79A2C5}

## Challenge 4

### Description of Challenge

Challenge 4 gives me the following string:

> 84 84 111 011 05 84 25 74 89 811 64 511 301 211 221 74 74 85 201 99 301 301 711

As of this time, I've not yet completed this challenge. I think it might be some type of XOR. 

### Solution


