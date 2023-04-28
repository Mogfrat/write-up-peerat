# Pirate life for me:
## Description:
La vie d’un peerat c’est entre autres la chasse au trésor,
après l’apprentissage et le fun !

 
Cette chasse commence ici :
host : 170.75.166.191
user : peerat
passwd :
 
Pourras-tu suivre les indices, surmonter les challenges
et trouver le trésor ?
## Solution:
On a la paire login/pass (le pass possède un event style hover) d'une session ssh:
peerat/peeratSpiritNeverDie!1678
ainsi que l'ip de l'host

Nous pouvons nous y connecter:

`$ ssh peerat@170.75.166.191`
nous arrivons dans le home directory de l'user ssh nous listons les fichiers :
```$ ls```
<img src="">
nous trouvons un fichier hint.md
nous faisons:
```$ cat hint.md```

Il y a un couple login/pass d'une autre session ssh
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101476186997145651/image.png">
nous faisons : 

```$ ssh -p 8888 peerat1@localhost```
Dans le doute on regarde s'il y a d'autre indice :

```$ ls```
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101476470775349248/image.png">

```$ cat hint.md```

L'indice nous dit qu'il faut s'authentifier à l'aide d'une clé ssh qui est dans l'home directory

nous nous y connectons avec :
```$ ssh -i ./id-rsa peerat2@ssh2```

Nous pouvons faire la m^eme chose à chaque nouvelle connection ssh.
il est stipulé qu'il faut se connecter au ssh sur localhost de la première session ssh

```$ ssh -p 3333 peerat4@localhost```

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101477300635189289/image.png">

Nous voici devant un "quiz"
Nous demandant le prénom de Barlow:
(Je l'ai trouvé gr^ace à l'image que j'avais download pour un autre chall)

Prénom = philipz

Après il nous demande le nom du repo qui possède le plus de commit (le lien est sur le portail du ctf):

peer-at-code-backend

Après il nous demande l'url avec lequel on s'est inscrit :

Celui qu'il faut utiliser est l'url du formulaire d'inscription à l'event :

https://framaforms.org/inscription-team-battles-info-secu-1679950176

on a un indice nous indiquant qu'il y a un serveur web écoutant sur le port 7777 

Et une clé/mdp :
peeratFunziesPassword

On accède au site en entrant l'ip + le port 7777 dans la barre de recherche de notre navigateur favori

Il y a un input pour la clé il suffit de l'écrire dedans et d'envoyer

J'ai commencé par activer la capture réseau dans l'outil dev de firefox

Nous pouvons voir que le script du jeu fait appel à l'api grace à une fonction pour compter les points

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101478873557909548/image.png">

en analysant le code source du script nous pouvons voir la fonction qui lance la partie qui est playZP() et la fonction qui permet de marquer les points qui est sendstonks()

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101478514626134097/image.png">

En essayant humainement de faire un maximum de point le jeu nous dit qu'on en a pas assez.
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101477814290624562/image.png">

J'ai donc essayé de jouer avec js

```js
playZP();
for(let i=0; i<1000; i++){
  sendStonks();
}
```

Ainsi nous arrivon à la tout dernière étape pour obtenir le flag : 
Un calcul

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101475812491939870/image.png">

Nous devons diviser 1945800 par le numéro de port du projector du i32 concaténer avec D_rUN le tout dans le format des flags habituels:

Le numéro de port du projecteur :
<img src="https://media.discordapp.net/attachments/1070815344559665194/1101352776644186193/SPOILER_IMG_20230425_073913_822.jpg">

Donc :
1945800 / 3243 = 600

Flag final : pacBcei{600D_rUN}