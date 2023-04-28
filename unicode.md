# Unicode:
## Description:

Un dernier petit exercice sur ce <a href="https://cdn.peerat.dev/pacXcei0423/independance.txt">fichier</a> avant de passer aux choses sérieuses...

Si tu ne gardes que les lettres majuscules, quelle est la chaine qu'il te reste ?

## Solution:

```python
with open('ui.txt','r') as file:
    flag = ''
    for i in file.read():
        if i.isupper():
           flag +=i
    print(flag)
```

Nous avons donc le flag qui est : UPJPBHMBTGHCHJMNABTPCICÉUNTCSOOOESCALRWEOIMASVVMJDGAVVNJVLVNVLNGTVCVVVVBLNCSNCLNNNLINNNLRONMAÉUCJWMMTBCVPDIECAFRSIÉUPVACDLCINNPDSPCTD