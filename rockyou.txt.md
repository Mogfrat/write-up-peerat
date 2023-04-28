# Rockyou.txt
## Description
Voici une <a href="https://cdn.peerat.dev/pacXcei0423/rotUltimateQuestionOfLife.zip">archive zip</a>,

 
pourras-tu découvrir le mot de passe ?
## Solution:
J'ai utilisé ma vm kali.
J'ai d'abord executé zip2john pour dump le hash du fichier zip:

```$ zip2john rotUltimateQuestionOfLife.zip > hash.txt```

J'ai du modifié le dump pour n'avoir que le hash:
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101599708188786718/image.png">
Ensuite on peut utiliser hashcat pour cracker le hash:

```$ hashcat -a 0 -m 17210 hash.txt /usr/share/wordlists/rockyou.txt```

- Le paramètre -a permet de définir l'attaque par dictionnaire;

- Le paramètre -m permet de définir le type de hash qu'on souhaite cracké;
 
- hash.txt est le hash qu'on souhaite cracké
 /usr/share/wordlists/rockyou.txt est la wordlist utilisée (nom du chall).
### source : https://hashcat.net/wiki/doku.php?id=example_hashes
  

Le mot de passe de l'archive est cracké le mot de passe est : 1iwantacookie.

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101600381550735461/image.png">

Nous pouvons déverouiller l'archive avec le mot de passe seulement le flag est chiffré avec le chiffrement césar. J'ai bruteforce pour la rotation gr^ace à https://cyberchef.org:
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101601585680883744/image.png">

flag : pacBcei{8r4V0_P0Ur_C3773_4774QU3_P4r_D1C710NN41r3}.
