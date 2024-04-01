# Off-Platform Project: Coded Correspondence

You and your pen pal, Vishal, have been exchanging letters for some time now. Recently, he has become interested in cryptography and the two of you have started sending encoded messages within your letters.

In this project, you will use your Python skills to decipher the messages you receive and to encode your own responses! Put your programming skills to the test with these fun cryptography puzzles. Here is his most recent letter:

    Hey there! How have you been? I've been great! I just learned about this really cool type of cipher called a Caesar Cipher. Here's how it works: You take your message, something like "hello" and then you shift all of the letters by a certain offset. 

    For example, if I chose an offset of 3 and a message of "hello", I would encode my message by shifting each letter 3 places to the left with respect to the alphabet. So "h" becomes "e", "e" becomes "b", "l" becomes "i", and "o" becomes "l". Then I have my encoded message, "ebiil"! Now I can send you my message and the offset and you can decode it by shifting each letter 3 places to the right. The best thing is that Julius Caesar himself used this cipher, that's why it's called the Caesar Cipher! Isn't that so cool! Okay, now I'm going to send you a longer encoded message that you have to decode yourself!
    
        xuo jxuhu! jxyi yi qd unqcfbu ev q squiqh syfxuh. muhu oek qrbu je tusetu yj? y xefu ie! iudt cu q cuiiqwu rqsa myjx jxu iqcu evviuj!
    
    This message has an offset of 10. Can you decode it?
    

#### Step 1: Decode Vishal's Message
In the cell below, use your Python skills to decode Vishal's message and print the result.

Stuck? Open this cell to view Hints: 

<span hidden>
You can account for shifts that go past the end of the alphabet using the modulus operator, but I'll let you figure out how!

Watch out for spaces and punctuation! Your code should only shift characters that are in the alphabet.

You'll want to find a way to represent the letters of the alphabet as numbers, where `a = 0`, `b = 1`, etc. Remember, the characters of a string can be accessed with integer indices.
</span>


```python
message = "xuo jxuhu! jxyi yi qd unqcfbu ev q squiqh syfxuh. muhu oek qrbu je tusetu yj? y xefu ie! iudt cu q cuiiqwu rqsa myjx jxu iqcu evviuj!"
offset = 10

# Function for decryption
def ceasar_decode(message, offset):
    # Stores the letters of the alphabet
    letters = 'abcdefghijklmnopqrstuvwxyz'
    # Empty string variable to catch the deciphered text
    cipher = ''
    
    # Loop through the characters of the encrypted message
    for i in message:
        # checks if each character of the encrypted message matches a character in letters  
        if i in letters:
            # Deciphers each character of the encrypted message and adds each deciphered character to the cipher variable
            cipher += letters[(letters.index(i) + offset)%(len(letters))]
        # Adds characters in the encrypted message that are not characters in the letters variable 
        else:
            cipher += i
    # Returns the deciphered message
    return cipher

# Calls the decrypt function with variables message and shift as arguments and stores the output to the variable decrypted
decrypted = ceasar_decode(message, offset)        

# Prints decrypted message 
print(f"Decrypted message is: {decrypted}")

```

    Enter encrypted message to decrypt: xuo jxuhu! jxyi yi qd unqcfbu ev q squiqh syfxuh. muhu oek qrbu je tusetu yj? y xefu ie! iudt cu q cuiiqwu rqsa myjx jxu iqcu evviuj!
    Enter the shift value: 10
    Decrypted message is: hey there! this is an example of a caesar cipher. were you able to decode it? i hope so! send me a message back with the same offset!


#### Step 2: Send Vishal a Coded Message
Great job! Now send Vishal back a message using the same offset. Your message can be anything you want! Remember, encoding happens in opposite direction of decoding.


```python
message = "playing with ciphers is pretty fun!"
offset = 10
letters = 'abcdefghijklmnopqrstuvwxyz'

def ceasar_encode(message, offset):
    cipher = ''
    
    for i in message:
        if i in letters:
            cipher += letters[(letters.index(i) + offset)%(len(letters))]
        else:
            cipher += i
    return cipher
    
encoded = ceasar_encode(message, offset)
print(f"Encrypted message is: {encoded}")
```

    Encrypted message is: zvkisxq gsdr mszrobc sc zboddi pex!


#### Step 3: Make functions for decoding and coding 

Vishal sent over another reply, this time with two coded messages!
    
    You're getting the hang of this! Okay here are two more messages, the first one is coded just like before with an offset of ten, and it contains a hint for decoding the second message!

    First message:
    
        jxu evviuj veh jxu iusedt cuiiqwu yi vekhjuud.
        
    Second message:
    
        bqdradyuzs ygxfubxq omqemd oubtqde fa oapq kagd yqeemsqe ue qhqz yadq eqogdq!
    
Decode both of these messages. 

If you haven't already, define two functions `caesar_decode(message, offset)` and `caesar_encode(message, offset)` that can be used to quickly decode and encode messages given any offset.


```python
first_message = "jxu evviuj veh jxu iusedt cuiiqwu yi vekhjuud."
offset = 10

decrypted1 = ceasar_decode(first_message, offset)

print(f"First message decoded: {decrypted1}")
```

    First message decoded: the offset for the second message is fourteen.
    Second message decoded: performing multiple caesar ciphers to code your messages is even more secure!



```python
second_message = "bqdradyuzs ygxfubxq omqemd oubtqde fa oapq kagd yqeemsqe ue qhqz yadq eqogdq!"
offset2 = 14

decrypted2 = ceasar_decode(second_message, offset2)

print(f"Second message decoded: {decrypted2}")
```

    Second message decoded: performing multiple caesar ciphers to code your messages is even more secure!


#### Step 4: Solving a Caesar Cipher without knowing the shift value

Awesome work! While you were working to decode his last two messages, Vishal sent over another letter! He's really been bitten by the crypto-bug. Read it and see what interesting task he has lined up for you this time.

    Hello again friend! I knew you would love the Caesar Cipher, it's a cool, simple way to encrypt messages. Did you know that back in Caesar's time, it was considered a very secure way of communication and it took a lot of effort to crack if you were unaware of the value of the shift? That's all changed with computers! Now we can brute force these kinds of ciphers very quickly, as I'm sure you can imagine.
            
    To test your cryptography skills, this next coded message is going to be harder than the last couple to crack. It's still going to be coded with a Caesar Cipher but this time I'm not going to tell you the value of the shift. You'll have to brute force it yourself.
            
    Here's the coded message:
            
        vhfinmxkl atox kxgwxkxw tee hy maxlx hew vbiaxkl hulhexmx. px'ee atox mh kxteer lmxi ni hnk ztfx by px ptgm mh dxxi hnk fxlltzxl ltyx.
            
    Good luck!
            
Decode Vishal's most recent message and see what it says!

Stuck? Open this cell to view Hints: 

<span hidden>
Since you don't know the cipher's offset, you'll need to try every possible option until you find the right one. Use a Python statement that will allow you to execute `caesar_decode()` multiple times with different `offset` arguments.
</span>


```python
import string

def encrypt(text, shift):
    encrypted_text = list(range(len(text)))
    alphabet = string.ascii_lowercase # 'abcdefghijklmnopqrstuvwxyz'
    first_half = alphabet[:shift]
    second_half = alphabet[shift:]
    shifted_alphabet = second_half + first_half
    
    for i, letter in enumerate(text.lower()):

        if letter in alphabet:
            original_index = alphabet.index(letter)
            new_letter = shifted_alphabet[original_index]
            encrypted_text[i] = new_letter    
        else:
            encrypted_text[i] = letter

    return "".join(encrypted_text)

def decrypt(text, shift):
    """ when the shift is known """
    decrypted_text = list(range(len(text)))
    alphabet = string.ascii_lowercase
    first_half = alphabet[:shift]
    second_half = alphabet[shift:]
    shifted_alphabet = second_half + first_half
    
    for i, letter in enumerate(text.lower()):

        if letter in alphabet:
            index = shifted_alphabet.index(letter)
            original_letter = alphabet[index]
            decrypted_text[i] = original_letter 
        else:
            decrypted_text[i] = letter

    return "".join(decrypted_text)

def brute_force_decrypt(text):
    """ when the shift is unknown """
    for n in range(26):
        print(f"Using a shift value of {n}")
        print(decrypt(text, n))
        print("\n***\n")
 
e = "vhfinmxkl atox kxgwxkxw tee hy maxlx hew vbiaxkl hulhexmx. px'ee atox mh kxteer lmxi ni hnk ztfx by px ptgm mh dxxi hnk fxlltzxl ltyx."
brute_force_decrypt(e)
```

    Using a shift value of 0
    vhfinmxkl atox kxgwxkxw tee hy maxlx hew vbiaxkl hulhexmx. px'ee atox mh kxteer lmxi ni hnk ztfx by px ptgm mh dxxi hnk fxlltzxl ltyx.
    
    ***
    
    Using a shift value of 1
    ugehmlwjk zsnw jwfvwjwv sdd gx lzwkw gdv uahzwjk gtkgdwlw. ow'dd zsnw lg jwsddq klwh mh gmj ysew ax ow osfl lg cwwh gmj ewkksywk ksxw.
    
    ***
    
    Using a shift value of 2
    tfdglkvij yrmv iveuvivu rcc fw kyvjv fcu tzgyvij fsjfcvkv. nv'cc yrmv kf ivrccp jkvg lg fli xrdv zw nv nrek kf bvvg fli dvjjrxvj jrwv.
    
    ***
    
    Using a shift value of 3
    secfkjuhi xqlu hudtuhut qbb ev jxuiu ebt syfxuhi eriebuju. mu'bb xqlu je huqbbo ijuf kf ekh wqcu yv mu mqdj je auuf ekh cuiiqwui iqvu.
    
    ***
    
    Using a shift value of 4
    rdbejitgh wpkt gtcstgts paa du iwtht das rxewtgh dqhdatit. lt'aa wpkt id gtpaan hite je djg vpbt xu lt lpci id ztte djg bthhpvth hput.
    
    ***
    
    Using a shift value of 5
    qcadihsfg vojs fsbrsfsr ozz ct hvsgs czr qwdvsfg cpgczshs. ks'zz vojs hc fsozzm ghsd id cif uoas wt ks kobh hc yssd cif asggousg gots.
    
    ***
    
    Using a shift value of 6
    pbzchgref unir eraqrerq nyy bs gurfr byq pvcuref bofbyrgr. jr'yy unir gb ernyyl fgrc hc bhe tnzr vs jr jnag gb xrrc bhe zrffntrf fnsr.
    
    ***
    
    Using a shift value of 7
    oaybgfqde tmhq dqzpqdqp mxx ar ftqeq axp oubtqde aneaxqfq. iq'xx tmhq fa dqmxxk efqb gb agd smyq ur iq imzf fa wqqb agd yqeemsqe emrq.
    
    ***
    
    Using a shift value of 8
    nzxafepcd slgp cpyopcpo lww zq espdp zwo ntaspcd zmdzwpep. hp'ww slgp ez cplwwj depa fa zfc rlxp tq hp hlye ez vppa zfc xpddlrpd dlqp.
    
    ***
    
    Using a shift value of 9
    mywzedobc rkfo boxnobon kvv yp droco yvn mszrobc ylcyvodo. go'vv rkfo dy bokvvi cdoz ez yeb qkwo sp go gkxd dy uooz yeb wocckqoc ckpo.
    
    ***
    
    Using a shift value of 10
    lxvydcnab qjen anwmnanm juu xo cqnbn xum lryqnab xkbxuncn. fn'uu qjen cx anjuuh bcny dy xda pjvn ro fn fjwc cx tnny xda vnbbjpnb bjon.
    
    ***
    
    Using a shift value of 11
    kwuxcbmza pidm zmvlmzml itt wn bpmam wtl kqxpmza wjawtmbm. em'tt pidm bw zmittg abmx cx wcz oium qn em eivb bw smmx wcz umaaioma ainm.
    
    ***
    
    Using a shift value of 12
    jvtwbalyz ohcl yluklylk hss vm aolzl vsk jpwolyz vizvslal. dl'ss ohcl av ylhssf zalw bw vby nhtl pm dl dhua av rllw vby tlzzhnlz zhml.
    
    ***
    
    Using a shift value of 13
    iusvazkxy ngbk xktjkxkj grr ul znkyk urj iovnkxy uhyurkzk. ck'rr ngbk zu xkgrre yzkv av uax mgsk ol ck cgtz zu qkkv uax skyygmky yglk.
    
    ***
    
    Using a shift value of 14
    htruzyjwx mfaj wjsijwji fqq tk ymjxj tqi hnumjwx tgxtqjyj. bj'qq mfaj yt wjfqqd xyju zu tzw lfrj nk bj bfsy yt pjju tzw rjxxfljx xfkj.
    
    ***
    
    Using a shift value of 15
    gsqtyxivw lezi virhivih epp sj xliwi sph gmtlivw sfwspixi. ai'pp lezi xs vieppc wxit yt syv keqi mj ai aerx xs oiit syv qiwwekiw weji.
    
    ***
    
    Using a shift value of 16
    frpsxwhuv kdyh uhqghuhg doo ri wkhvh rog flskhuv revrohwh. zh'oo kdyh wr uhdoob vwhs xs rxu jdph li zh zdqw wr nhhs rxu phvvdjhv vdih.
    
    ***
    
    Using a shift value of 17
    eqorwvgtu jcxg tgpfgtgf cnn qh vjgug qnf ekrjgtu qduqngvg. yg'nn jcxg vq tgcnna uvgr wr qwt icog kh yg ycpv vq mggr qwt oguucigu uchg.
    
    ***
    
    Using a shift value of 18
    dpnqvufst ibwf sfoefsfe bmm pg uiftf pme djqifst pctpmfuf. xf'mm ibwf up sfbmmz tufq vq pvs hbnf jg xf xbou up lffq pvs nfttbhft tbgf.
    
    ***
    
    Using a shift value of 19
    computers have rendered all of these old ciphers obsolete. we'll have to really step up our game if we want to keep our messages safe.
    
    ***
    
    Using a shift value of 20
    bnlotsdqr gzud qdmcdqdc zkk ne sgdrd nkc bhogdqr narnkdsd. vd'kk gzud sn qdzkkx rsdo to ntq fzld he vd vzms sn jddo ntq ldrrzfdr rzed.
    
    ***
    
    Using a shift value of 21
    amknsrcpq fytc pclbcpcb yjj md rfcqc mjb agnfcpq mzqmjcrc. uc'jj fytc rm pcyjjw qrcn sn msp eykc gd uc uylr rm iccn msp kcqqyecq qydc.
    
    ***
    
    Using a shift value of 22
    zljmrqbop exsb obkaboba xii lc qebpb lia zfmebop lyplibqb. tb'ii exsb ql obxiiv pqbm rm lro dxjb fc tb txkq ql hbbm lro jbppxdbp pxcb.
    
    ***
    
    Using a shift value of 23
    ykilqpano dwra najzanaz whh kb pdaoa khz yeldano kxokhapa. sa'hh dwra pk nawhhu opal ql kqn cwia eb sa swjp pk gaal kqn iaoowcao owba.
    
    ***
    
    Using a shift value of 24
    xjhkpozmn cvqz mziyzmzy vgg ja ocznz jgy xdkczmn jwnjgzoz. rz'gg cvqz oj mzvggt nozk pk jpm bvhz da rz rvio oj fzzk jpm hznnvbzn nvaz.
    
    ***
    
    Using a shift value of 25
    wigjonylm bupy lyhxylyx uff iz nbymy ifx wcjbylm ivmifyny. qy'ff bupy ni lyuffs mnyj oj iol augy cz qy quhn ni eyyj iol gymmuaym muzy.
    
    ***
    


#### Step 5: The Vigenère Cipher

Great work! While you were working on the brute force cracking of the cipher, Vishal sent over another letter. That guy is a letter machine!

    Salutations! As you can see, technology has made brute forcing simple ciphers like the Caesar Cipher extremely easy, and us crypto-enthusiasts have had to get more creative and use more complicated ciphers. This next cipher I'm going to teach you is the Vigenère Cipher, invented by an Italian cryptologist named Giovan Battista Bellaso (cool name eh?) in the 16th century, but named after another cryptologist from the 16th century, Blaise de Vigenère.
            
    The Vigenère Cipher is a polyalphabetic substitution cipher, as opposed to the Caesar Cipher which was a monoalphabetic substitution cipher. What this means is that opposed to having a single shift that is applied to every letter, the Vigenère Cipher has a different shift for each individual letter. The value of the shift for each letter is determined by a given keyword.
           
    Consider the message:
           
        barry is the spy

    If we want to code this message, first we choose a keyword. For this example, we'll use the keyword
           
        dog
               
    Now we repeat the keyword over and over to generate a keyword phrase that is the same length as the message we want to code. So if we want to code the message "barry is the spy" our keyword phrase is "dogdo gd ogd ogd". Now we are ready to start coding our message. We shift each letter of our message by the place value of the corresponding letter in the keyword phrase, assuming that "a" has a place value of 0, "b" has a place value of 1, and so forth.

                  message:    b  a  r  r  y    i  s    t  h  e    s  p  y
                
           keyword phrase:    d  o  g  d  o    g  d    o  g  d    o  g  d
                 
    resulting place value:    24 12 11 14 10   2  15   5  1  1    4  9  21
      
    So we shift "b", which has an index of 1, by the index of "d", which is 3. This gives us an place value of 24, which is "y". Remember to loop back around when we reach either end of the alphabet! Then continue the trend: we shift "a" by the place value of "o", 14, and get "m", we shift "r" by the place value of "g", 15, and get "l", shift the next "r" by 4 places and get "o", and so forth. Once we complete all the shifts we end up with our coded message:
            
        ymlok cp fbb ejv
                
    As you can imagine, this is a lot harder to crack without knowing the keyword! So now comes the hard part. I'll give you a message and the keyword, and you'll see if you can figure out how to crack it! Ready? Okay here's my message:
            
        txm srom vkda gl lzlgzr qpdb? fepb ejac! ubr imn tapludwy mhfbz cza ruxzal wg zztcgcexxch!
                
    and the keyword to decode my message is 
            
        friends
                
    Because that's what we are! Good luck friend!
           
And there it is. Vishal has given you quite the assignment this time! Try to decode his message. It may be helpful to create a function that takes two parameters &mdash; the coded message and the keyword &mdash; then work towards a solution from there.

Stuck? Open this cell to view Hints: 

<span hidden>
Like before, you'll only want to shift characters that are in the alphabet. Your keyword phrase should ignore any spaces and punctuation in the original message.

For example, given the message

  ciphers are awesome!

and the keyword

  cat

the keyword phrase would be:

  catcatc atc atcatca

and the encoded string would be:

  aiwfeyq ayc adcsvke!
</span>


```python
def decrypt(ciphertext, key):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    decrypted_text = ""
    key_index = 0

    for char in ciphertext:
        if char.isalpha():
            # Find the position in the alphabet
            char_index = alphabet.find(char.lower())
            # Find the position of the key character
            key_char = key[key_index % len(key)]
            key_char_index = alphabet.find(key_char)
            # Decrypt the character
            decrypted_char = alphabet[(char_index + key_char_index) % len(alphabet)]
            # Append the decrypted character to the decrypted text
            decrypted_text += decrypted_char
            # Only increment key_index if a letter was encrypted/decrypted
            if char.isalpha():
                key_index += 1
        else:
            # If the character is not a letter, add it as it is (preserving spaces)
            decrypted_text += char

    return decrypted_text

# Encrypted message and key
encrypted_message = "txm srom vkda gl lzlgzr qpdb? fepb ejac! ubr imn tapludwy mhfbz cza ruxzal wg zztcgcexxch!"
key = "friends"

# Repeat the key to match the length of the encrypted message
repeated_key = (key * (len(encrypted_message) // len(key))) + key[:len(encrypted_message) % len(key)]

# Decrypt the message using the repeated key
decrypted_message = decrypt(encrypted_message, repeated_key)

print(f"Decrypted message: {decrypted_message}")
```

    Decrypted message: you were able to decode this? nice work! you are becoming quite the expert at crytography!


#### Step 6: Send a message with the  Vigenère Cipher
Great work decoding the message. For your final task, write a function that can encode a message using a given keyword and write out a message to send to Vishal!

*As a bonus, try calling your decoder function on the result of your encryption function. You should get the original message back!*


```python
def vigenere_encrypt(plaintext, key):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    encrypted_text = ""
    key_index = 0

    for char in plaintext:
        if char.isalpha():
            # Find the position in the alphabet
            char_index = alphabet.find(char.lower())
            # Find the position of the key character
            key_char = key[key_index % len(key)]
            key_char_index = alphabet.find(key_char)
            # Encrypt the character
            encrypted_char = alphabet[(char_index - key_char_index) % len(alphabet)]
            # Append the encrypted character to the encrypted text
            encrypted_text += encrypted_char
            # Only increment key_index if a letter was encrypted/decrypted
            if char.isalpha():
                key_index += 1
        else:
            # If the character is not a letter, add it as it is (preserving spaces or special characters)
            encrypted_text += char

    return encrypted_text

# Plain message and key
plain_message = "this cipher was a difficult one for me"
key = "fun"

# Repeat the key to match the length of the plain message
repeated_key = (key * (len(plain_message) // len(key))) + key[:len(plain_message) % len(key)]

# Encrypt the message using the repeated key
encrypted_message = vigenere_encrypt(plain_message, repeated_key)

print(f"Encrypted message: {encrypted_message}")

def decrypt(ciphertext, key):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    decrypted_text = ""
    key_index = 0

    for char in ciphertext:
        if char.isalpha():
            # Find the position in the alphabet
            char_index = alphabet.find(char.lower())
            # Find the position of the key character
            key_char = key[key_index % len(key)]
            key_char_index = alphabet.find(key_char)
            # Decrypt the character
            decrypted_char = alphabet[(char_index + key_char_index) % len(alphabet)]
            # Append the decrypted character to the decrypted text
            decrypted_text += decrypted_char
            # Only increment key_index if a letter was encrypted/decrypted
            if char.isalpha():
                key_index += 1
        else:
            # If the character is not a letter, add it as it is (preserving spaces)
            decrypted_text += char

    return decrypted_text

# Encrypted message and key
encrypted_message = "onvn ivknrm cnn g qdlsdihgz bik sjx zz"
key = "fun"

# Repeat the key to match the length of the encrypted message
repeated_key = (key * (len(encrypted_message) // len(key))) + key[:len(encrypted_message) % len(key)]

# Decrypt the message using the repeated key
decrypted_message = decrypt(encrypted_message, repeated_key)

print(f"Decrypted message: {decrypted_message}")
```

    Encrypted message: onvn ivknrm cnn g qdlsdihgz bik sjx zz
    Decrypted message: this cipher was a difficult one for me


#### Conclusion
Over the course of this project you've learned about two different cipher methods and have used your Python skills to code and decode messages. There are all types of other facinating ciphers out there to explore, and Python is the perfect language to implement them with, so go exploring! 
