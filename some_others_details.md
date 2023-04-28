# Some others details
## Description:
Ici j'ai utilisé une autre manière de cacher des infos dans une <a href="https://cdn.peerat.dev/pacXcei0423/profile.png">image</a>.

 
Pourras-tu trouver le flag ?
## Solution:

J'ai utilisé ce site pour lire les données exifs:
https://exifinfo.org

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101569972964163636/image.png">

Une valeur dans le champs rights des données xmp attire mon oeil:

cGFjQmNlaXsxM19EMTQ4MTNfNTNfN3IwVVYzX0Q0TjVfMTM1X0QzNzQxMTV9

Je décide donc d'utiliser le décodage b64 de https://cyberchef.org

<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101570682749464688/image.png">

Nous obtenons le flag : pacBcei{13_D14813_53_7r0UV3_D4N5_135_D374115}