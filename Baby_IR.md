<div>
   <a href="https://indy.ctf.eng.run/challenge/28"><img src="https://img.shields.io/badge/Baby IR%20--%202-Click%20to%20Solve-green[700]" height="25"></a>

  <img src="https://img.shields.io/badge/Points%3A-500-red" align="right" height="25">
</div>

<div align="center">
    <h1>Baby_IR</h1>
</div>

Description : An IR Communication was sniffed between two people. The data was a pile of binary digits. Analyze the data sniffed and use them in the circuit and get a "meaning full" flag. (Data contains junk values too.)


```
1 111111010101000010101111

2 111111011001010001111111

3 111111010000100011110111

4 000111011001010001111111

5 111111011011000001001111

6 010111001001010001110111

7 111111010001100011100111

8 010111001011010101110011

9 111111011000000001111111
10
```
### Approach: 

I observed the given code in the tinkercad and figure out the the flag as it was given in the broken parts ```ctf```, ```wh```, ```rs```,   ```fla```, ```1aG``` and gave the given inputs by converting to the hex code and took the ctf.

<div align="center">
<img width="800" alt="Piece code for reference" src="https://user-images.githubusercontent.com/91147942/175774523-dea495d7-ac25-44c8-bc61-cb1234864deb.png">
</div>

### Flag: 

```ictf{whrs_m4_f1aG}```