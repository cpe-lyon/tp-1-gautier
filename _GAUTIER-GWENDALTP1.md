# Rendu TP 1 Gwendal GAUTIER 

# Exercice 1 
Installation réussie; 

# Exercice 2 

## Manuel
### Question 1 

La commande `which`
retourne  le  chemin  des  fichiers  qui  seraient exécutés dans l'environnement courant si ses arguments avaient été donnés comme  commandes  dans un interpréteur de commandes strictement conforme à POSIX. Pour ce faire, which cherche dans la variable PATH les fichiers  exécutables correspondants aux noms des arguments.which ne déréférence pas les liens symboliques.
Exemple : 
```
 which -a [nom du fichier]
```

### Question 2 
Pour entrer dans la manuel, on utilise la commande :
```
man man
```
Une fois entré dans le manuel, on entre un __/__ , et on écrit le terme qu'on recherche.

### Question 3 

On quitte le manuel à tout moment en utilisant la touche __q__

### Question 4 

Pour afficher la première page de la section 6, on utilisra la commande : 
```
man 6 intro
```
Cete section parle de Jeux sous Linux.

## Navigation dans l'arborescence
## Question 1

Pour aller dans le dossier `/var/log/`, on utilisera la commande : 
```
cd /var/log
```

## Question 2 
Pour remonter dans le dossier parent par un chemin relatif, on utilisera : 
```
cd ..
```

## Question 3 
Pour retourner dans le dossier `Home`, on utilisera : 
```
cd ~
```

## Question 4 
Pour revenir au dossier précédent sans utiliser de chemin, on utilisera : 
```
cd -
```

## Question 5 
Quand on essaye d'accéder au dossier root (`avec cd root`) on obtient : 
```
cd /root
bash: cd: /root: Permission non accordée
```

## Question 6
En essayant avec `sudo cd /root` : 
```
sudo cd /root
[sudo] password for gwendal.gautier: 
sudo: cd: command not found
```

On constate que l'on ne peut pas faire un cd accompagné d'un sudo. 

## Question 7 
Pour créer l'arborescence suivante : 
```
mkdir Dossier1
mkdir Dossier2

cd Dossier1
touch Fichier1
cd ..

cd Dossier2
mkdir Dossier2.1 Dossier2.2
cd Dossier2.2

touch Fichier2 Fichier3

```

## Question 8 
Si on essaye de supprimer le Fichier1, Dossier1 (en utilisant la commande `rm`), on obtient : 
```
rm Fichier1

Se déroule sans encontre, après ls, le fichier a bien été supprimé.

rm Dossier1
rm: impossible de supprimer «Dossier1»: est un dossier

```

## Question 9
Pour supprimer un dossier vide, on utilisera `rmdir` :
```
rmdir Dossier1
```

## Question 10
Quand on applique `rmdir` à Dossier 2, on obtient : 
```
rmdir Dossier2
rmdir: échec de suppression de «Dossier2»: Le dossier n'est pas vide
```

## Question 11
Pour supprimer en une seule commande Dossier2 et son contenu, on utilisera `rm` avec l'option `-r`
```
rm -r Dossier2
```
## Commandes importantes
## Question 1
Pour afficher l'heure, on utilisera la commande `date`. La commande time sert à chronométrer le temps de *run* d'un programme. 
```
date
mardi 11 février 2020, 11:49:29 (UTC+0100)

time 
real	0m0.000s
user	0m0.000s
sys	0m0.000s
```
## Question 2 
En utilisant `ls`, on affiche tous les fichiers d'un dossier. Ne utilisant la (ou `ls -a`) on affiche aussi les fichiers cachés : 
```
ls 
ls -a
```
## Question 3 
Le programme `ls` se situe sous : 
```
which ls
$/bin/ls
```
## Question 4 
Si on essaye la commande `ll` (ou `ls -alF`) : 
on obtient un format de retour qui long (on peut visionner les droits de lecture ecriture des differents groupes en plus du nom de fichier par exemple). 
## Question 5 
On utilise de nouveau `ls`: 
```
ls /bin
```
## Question 6
 Elle liste les fichiers ou dossiers (excepté les fichiers cachés)présent dans un dossier cible, ou par défaut, les fichiers ou dossiers présents dans le fichier où se trouve l'utilisateur.
## Question 7 
Pour récupérer le chemin du dossier courant, on utilisera la commande : 
```
pwd
```
## Question 8
La commande `echo 'yo' > plop` écrit "yo" dans le fichier plop, mais en écrasant le précédent contenu. La première fois que la commande est éxécuté, on crée le fichier plop et on y écrit yo. La seconde, on efface le premier yo pour le remplacer par le second. 

## Question 9
À la différence de la précedente commande, l'opérateur >> permet ici d'écrire à la fin du fichier plop, au lieu d'en écraser le précédent contenu.

## Question 10 
```
file plop 
plop: ASCII text, with CRLF line terminators
```
la commande `file` permet d'botenir le type de fichier et certaines de ses spécifités.

## Question 11
Suite à ces commandes : 
```
echo 'Hello Toto !' > toto
ln toto titi
```
On obtient un fichier toto qui contient la chaine indiqué, ainsi qu'un lien titi qui renvoie vers toto. Si on modifie toto...
```
echo 'Hello !' > toto
```
On observe que titi fonctionne toujours et affiche le fichier modifié. En revanche, si on supprime toto...
```
rm toto
```
... et bien titi affiche le dernier contenu de toto.

## Question 12 
Si on crée maintenant un lien *symbolique* de tutu vers titi avec la commande suivante , et qu'on modifie titi: 
```
ln -s titi tutu
echo ' Hel lo !' > titi
```
On remarque que titi a bien changé, mais pas tutu. 

Si on supprime titi :
````
rm titi
````
tutu affiche toujours la dernière version avant suppression de titi.

## Question 13 
Pour interrompre ou reprendre le défilement de l'écran, on utilisera le raccourci : 
```
ctrl+c
```

## Question 14 
Pour afficher les 5 premières lignes, on utilisera `head` :
```
head -n 5
```

Pour afficher les 15 dernières, on utilisera `tail` : 
```
tail -n 10
```

Pour afficher les lignes 10 à 20, on fera: 
```
head -n 10 | tail -n 20
```


## Question 15 
La commande : `dmesg | less` a pour effet d'afficher les messages du kernel, en permetttant de passer de l'un à l'autre en utilisant ESPACE. 

## Question 16
Le fichier */etc/passwd* contient les informations relatives à chaque utilisateur. 
```
man 5 passwd
```

## Question 17
On utilisera ici la commande sort :
```
cut -c1 /etc/passwd | sort -r
```

## Question 18 
On utilisera la commande : 
```
getent passwd | wc -l
```
## Question 19 

## Question 20
Pour trouver tous les fichiers contenant le mot passwd, on utilisera :
```
find -name "passwd"
```
## Question 21

```
find -name "passwd" > list_passwd_files.txt 2>/dev/null
```

## Question 23
On localisera le fichier history.log avec la commande suivante : 
```
sudo apt install mlocate  
locate history.log
```
## Question 24
Non, locate ne trouve pas le fichier

## Exercice 3 
## Question 1 
```
cp /var/log/syslog /home/gwendal
```

## Question2
On remplacera toutes les occurences du mot "kernel" par "noyau" en utilisant un `Ctrl+W` pour recherche toute les itérations de kernel. 

## Question 3 
Afin de déplacer les 10 premières lignes à la fin du fichier, on fera un `Ctrl + X`
et `Ctrl+V`.

## Question 4 
On annulera la dernière action en utilisant `Alt+U`

## Question 5 
