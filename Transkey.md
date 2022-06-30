<div>
   <a href="https://indy.ctf.eng.run/challenge/16"><img src="https://img.shields.io/badge/Transkey: %20-Click%20to%20Solve-green[700]" height="25"></a>
    <img src="https://img.shields.io/badge/Points%3A-179-red" align="right" height="25">
<img src="https://img.shields.io/badge/Category%3A%20-Crypto-orange" align="right" height="25">
</div>

<div align="center">
    <h1>Transkey</h1>
</div>

### Approach:

- Maybe i haven't approached the challenge in the correct way but i tried couple of online encryption/decryption programmes and somehow i got the key as ```cabd``` and then i used the key again in the decryption programme to get the flag.

```
import math

key = "XXXXXX"
def encryptMessage(msg):
    cipher = ""
    k_indx = 0
    msg_len = float(len(msg))
    msg_lst = list(msg)
    key_lst = sorted(list(key))
    col = len(key)
    row = int(math.ceil(msg_len / col))
    fill_null = int((row * col) - msg_len)
    msg_lst.extend('_' * fill_null)
    matrix = [msg_lst[i: i + col]
              for i in range(0, len(msg_lst), col)]
    for _ in range(col):
        curr_idx = key.index(key_lst[k_indx])
        cipher += ''.join([row[curr_idx]
                          for row in matrix])
        k_indx += 1
    return cipher

msg = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
cipher = encryptMessage(msg)
print("Encrypted Message: {}".format(cipher))

//Encrypted Message: ctsinp_e_hytrpt_hiaw_}i{nsoir_ytefaoicessik_
```


### Flag: 

```ictf{transposition_cipher_is_easy_with_key}```
