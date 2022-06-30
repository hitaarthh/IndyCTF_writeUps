<div>
   <a href="https://indy.ctf.eng.run/challenge/17"><img src="https://img.shields.io/badge/5niff--1t: %20-Click%20to%20Solve-green[700]" height="25"></a>
  <img src="https://img.shields.io/badge/Points%3A-298-red" align="right" height="25">
  <img src="https://img.shields.io/badge/Category%3A%20-Hardware-orange" align="right" height="25">

</div>

<div align="center">
    <h1>5niff--1t</h1>
</div>

### Approach:

- Opened the ```.logicdata``` using <a href="https://www.google.com/search?q=Saleae+logic+software&rlz=1C5CHFA_enIN970IN976&oq=Saleae+logic+software&aqs=chrome..69i57.343j0j7&sourceid=chrome&ie=UTF-8">Saleae logic software.</a>

- Attached an async serial analyzer to both of the channels and got the detailed conversation. 

- As per the given hint i changed the bit rate 115200 and obtained the flag,

<div align="center">
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/91147942/176726972-4e63e44c-995d-4de7-92b6-7a9db1a858eb.png">
</div>

### Flag:
```ictf{part_of_a_balanced_breakfast}```
