# Backdoors and Breaches

## Challenge 

### Description of Challenge

As part of the Kickstarter rewards, I was able to obtain the expansion pack of cards that integrate with the Backdoors and Breaches tabletop card game. On each of the cards, there are various strings on each of the cards.

Each of the 6 cards has a letter, a-f, which I assume is the order of the card. These letters are in the lower left corner. In the lower right-hand corner is the two character strings. They are found on the first 5 cards, and the 6th has a URL: <a href="tficomic.io/bnb">tficomic.io/bnb</a>. Going to that URL gives me the following message:

> Hey there. Have you found the hidden message on the Backdoors & Breaches Consultant Cards?

> Once you find the 7-character word, submit it as a "Bonus" in this platform.. Learn more about the scoreboard below.

\begin{table}[]
\begin{tabular}{lll}
Card Name & Order & Code  \\
Wheeler   & a     & Y3    \\
Martina   & b     & Vy    \\
Sally     & c     & aW    \\
Eli       & d     & 91    \\
Art       & e     & cw    \\
Arf       & f     & * URL
\end{tabular}
\end{table}

Assuming that the Arf card that contains the URL is meant as a placeholder of some type, combining all of the codes gives me:

> Y3VyaW91cw==

This looks like some type of Base number. When I fed that number into <a href="dcode.fr/en">DCode</a>, it tells me that it is indeed a Base 64 number. This decrypts to:

> curious

Entering in "curious" as a bonus code yields **25** points.

### Solution

curious
