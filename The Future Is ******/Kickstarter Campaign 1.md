# Kickstarter Campaign 1

These challenges are found in the original Kickstarter campaign, found here: <a href="https://www.kickstarter.com/projects/rekcah/the-future-is-from-rekcah-comics/description">Kickstarter</a>.

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

### Solution

## Challenge 3

### Description of Challenge

### Solution

## Challenge 4

### Description of Challenge

### Solution
