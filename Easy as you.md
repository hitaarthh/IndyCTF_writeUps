<div>
   <a href="https://indy.ctf.eng.run/challenge/6"><img src="https://img.shields.io/badge/Easy as you%20--%202-Click%20to%20Solve-green[700]" height="25"></a>
  <img src="https://img.shields.io/badge/Points%3A-179-red" align="right" height="25">
</div>

<div align="center">
    <h1>Easy as you</h1>
</div>

### Description:
Could you understand and reverse it? Shouldn't be that tough...


Easy as you didn't seem to be so easy. It was one of the only reversing challenge which i solved.

### Approach:
- The given file was compiled in assembly code.
- To decompile the given code, i used <a href="https://www.hex-rays.com/products/decompiler/manual/primer.shtml">IDA Decmpiler to C</a> for decompiling the assembly code to C code.

- Execute the given code to get the flag.

<div align="center">
<img width="500" alt="IDA Compiler" src="https://user-images.githubusercontent.com/91147942/175774976-2e081a8c-760d-4e27-a26a-5688bbc76fe5.png">
</div>

### Flag: 

```ictf{Th1s_w4s_n0t_s0_d1ff1cul7}```