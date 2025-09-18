# Ashcan

An ashcan version of a comic book is a preliminary, often low-quality or limited-run publication created primarily to secure trademark or copyright rights for a title or character, rather than for commercial sale.
The term originated in the 1930s and 1940s during the early days of the comic book industry, when publishers rushed to claim popular-sounding titles before competitors could.
To legally prove a title had been published, they would produce a quick, inexpensive mock-up, typically the same size as a regular comic, often with a black and white cover made by pasting a new title onto recycled artwork from a previous issue.
Interior pages might contain unfinished pencil sketches, previously published material, or even be blank.
These editions were usually printed in very small quantities—sometimes as few as two copies—one sent to the US Patent & Trademark Office and the other kept on file.
The name "ashcan" reflects their intended fate: after fulfilling their legal purpose, they were often discarded in the trash.

To find the ashcan challenge, I found the copy in the Discord channel. I'd upload it here, but it is too big.

## Challenge 1 

### Description of Challenge

In the Discord, I was able to find the Ashcan version. The file name is "SPOILER_TFI_AshcanEdition_DONT_DISTRIBUTE.pdf". I downloaded it, and on page 3, there is the challenge. 

![Ashcan](https://github.com/user-attachments/assets/93b4ccb1-a318-43b1-abbc-242a05b6b871)

To start, let's go to <a href="tficomic.io/ashcan">tficomic.io/ashcan</a>. The page gives us this:

> Hey there. Are you trying to crack the cover password?
> You've been given a list of letters and 6 images of clocks.
> How many letters are in the list?
> Looks like the minute hand only shows 0 or 30 minutes in all of the images. How many possible clock positions are there if you are limited to 30 minute increments?

And, looking at the reference inmage, the string is:

> MUHSULYRWETICPBGFKJNDAZO

To answer the first question, there are **24** letters in the string. And this is a type of clock cipher.

And counting the number of positiong for each clock setting, I then eliminated that number of letters and then choose the letter after.
Clock 1: 3:30 was 7 positions, and letter 8 = R

Clock 2: 4:30 was 9 positions, and letter 10 = E

Clock 3: 8:30 was 17 positions, and letter 18 = K

Clock 4: 6:00 was 12 positions, and letter 13 = C

Clock 5: 10:30 was 21 positions, and letter 22 is A

Clock 6: 1:00 was 2 positions, and letter 3 is H

Submitted this in the platform for **100** points.
### Solution

REKCAH
