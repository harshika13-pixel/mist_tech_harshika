
# CTF Challenges

## Challenge 1: rail-fence

Here is a cipher encrypted using the rail fence with 4 rails.

Ta _7N6D8Dhlg:W3D_H3C31N__387ef sHR053F38N43DFD i33___N6

Decrypt it and put the decoded message in the picoCTF flag format.

### Solution

![alt text](<Screenshot (1).png>)

### Flag

`picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_83F6D8D7}`

### New Learnings

Learnt about how rail fence cipher works



## Challenge 2: Guess My Cheese (part 1)

Try to decrypt the secret cheese password to prove you're not the imposter.
Connect to the program on our server: `nc verbal-sleep.picoctf.net 51147`

### Solution

Connected to the server via netcat. I could encode any word and it would return me the ciphertext. The cipher used was Affine according to the hint given in the question. 
the word i encoded was `feta`. it returned `AHGJ`. 

my formula is y=(ax+b) mod 26
F -> A, x=5,y=0
E -> H, x=4,y=7

on solving this i received, a=19,b=9

In the question the given clue was `VPZKPDDFHUNNKI`
used a affine decoder to decode the clue, with a=19,b=9.

the decoded word was `COULOMMIERSSLP`

entered this in my terminal to receive the flag. 

![alt text](<Screenshot (2).png>)

![alt text](<Screenshot (3).png>)

### Flag

`picoCTF{ChEeSy7df82c21}`

