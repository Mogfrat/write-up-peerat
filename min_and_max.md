# Min and Max:

## Description:
Voici un <a href="https://cdn.peerat.dev/pacXcei0423/requests">fichier</a> avec le nombre de requêtes
que j'effectue par jour vers le cyberespace.

 

 
Je suis intéressé de connaitre le résultat de la soustraction entre le maximum et le minimum.

## Solution:
Nous pouvons utiliser le module requests de python pour aller plus vite mais lorsque je l'ai fait je n'y ai pas pensé:

```python 
def minimum():
    maxi = float("inf")
    with open('web-client/ui.txt','r') as file:
        a = file.readlines()
        for i in a:
            maxi = min(maxi,int(i))
    return maxi


def maximum():
    mini = float("-inf")
    with open('web-client/ui.txt', 'r') as file:
        b = file.readlines()
        for i in b:
            mini = max(mini, int(i))
    return mini

print(maximum()-minimum())
```

Le "flag" est : 99983963