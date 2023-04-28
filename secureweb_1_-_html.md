# SecureWeb 1 - HTML:
## Description:
Dans cette série de 4 puzzles "SecureWeb X", il a 4 flags à trouver (un par puzzle)
 
Celui-ci est assez facile

Pourras-tu trouver les 4 sur ce <a href="https://www.peerat.dev/">site</a> ?
Indique ici le premier.

## Résolution:
Dès la redirection efféctuée j'utilise le raccourci ctrl+u pour voir le code source de la page je descend et je vois ceci :
<img src="https://cdn.discordapp.com/attachments/919873849015828510/1101575152245948469/image.png">
Je reconnais l'url encoding des "{}" qui sont %7B et %7D
Nous pouvons déterminer le flag : pacBcei{516N41H1DD3N}