Vérifier vos paramètres
Si  vous  souhaitez  vérifier  vos  réglages,  vous  pouvez  utiliser  la  commande  
git config --list
  pour
lister tous les réglages que Git a pu trouver jusqu’ici :
$ git config --list
user.name=John Doe
user.email=johndoe@example.com
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
Vous  pourrez  voir  certains  paramètres  apparaître  plusieurs  fois  car  Git  lit  les  mêmes  paramètres
depuis plusieurs fichiers (
/etc/gitconfig
 et 
~/.gitconfig
, par exemple). Git utilise la dernière valeur
pour chaque paramètre.
Vous  pouvez  aussi  vérifier  la  valeur  effective  d’un  paramètre  particulier  en  tapant  
git  config
<param
è
tre>
 :
$ git config user.name
John Doe