## Challenge 1: Mod 26

Cryptography can be easy, do you know what ROT13 is? cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_Ncualgvd}

### Solution

ROT13 is a simple cipher where every letter is shifted by 13 places in the alphabet.
A ---> N
B ---> O

So, i have used a decoder to shift every letter in the given clue.

### Flag

`picoCTF{next_time_I'll_try_2_rounds_of_rot13_Aphnytiq}`

### New Learnings

ROT13 is its own inverse, applying it twice returns the original, so 2 rounds would cancel out the cipher.



## Challenge 2: 13

Cryptography can be easy, do you know what ROT13 is? cvpbPGS{abg_gbb_onq_bs_n_ceboyrz}

### Solution

ROT13 is a simple cipher where every letter is shifted by 13 places in the alphabet.
A ---> N
B ---> O

So, i have shifted every letter in the given clue.

### Flag

`picoCTF{not_too_bad_of_a_problem}`



## Challenge 3: Interencdec

Can you get the real meaning from this text: `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==`


### Solution

used a base 64 decoder twice to obtain:

`d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ==`
and
`wpjvJAM{jhlzhy_k3jy9wa3k_lh60l00i}`

used a caesar decoder to decode the above text. the key was -7 (each letter shifts back 7 places).

### Flag

`picoCTF{caesar_d3cr9pt3d_ea60e00b}`

### New Learnings

sometimes texts can be encoded multiple times.

