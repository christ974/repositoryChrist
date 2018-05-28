Paramétrage à la première utilisation de Git



Maintenant  que  vous  avez  installé  Git  sur  votre  système,  vous  voudrez  personnaliser  votre
environnement Git. Vous ne devriez avoir à réaliser ces réglages qu’une seule fois ; ils persisteront
lors  des  mises  à  jour.  Vous  pouvez  aussi  les  changer  à  tout  instant  en  relançant  les  mêmes
commandes.
Git  contient  un  outil  appelé  
git config
  pour  vous  permettre  de  voir  et  modifier  les  variables  de
configuration  qui  contrôlent  tous  les  aspects  de  l’apparence  et  du  comportement  de  Git.  Ces
variables peuvent être stockées dans trois endroits différents :
•
Fichier  
/etc/gitconfig
 :  Contient  les  valeurs  pour  tous  les  utilisateurs  et  tous  les  dépôts  du
système. Si vous passez l’option 
--system
 à 
git config
, il lit et écrit ce fichier spécifiquement.
19
•
Fichier  
~/.gitconfig
 :  Spécifique  à  votre  utilisateur.  Vous  pouvez  forcer  Git  à  lire  et  écrire  ce
fichier en passant l’option 
--global
.
•
Fichier  
config
  dans  le  répertoire  Git  (c’est-à-dire  
.git/config
)  du  dépôt  en  cours  d’utilisation :
spécifique au seul dépôt en cours.
Chaque niveau surcharge le niveau précédent, donc les valeurs dans 
.git/config
 surchargent celles
de 
/etc/gitconfig
.
Sur   les   systèmes   Windows,   Git   recherche   le   fichier   
.gitconfig
   dans   le   répertoire   
$HOME
(
%USERPROFILE%
 dans l’environnement natif de Windows) qui est 
C:\Documents and Settings\$USER
 ou
C:\Users\$USER
    la    plupart    du    temps,    selon    la    version    (
$USER
    devient    
%USERNAME%
    dans
l’environnement de Windows). Il recherche tout de même 
/etc/gitconfig
, bien qu’il soit relatif à la
racine MSys, qui se trouve où vous aurez décidé d’installer Git sur votre système Windows. Si vous
utilisez une version 2.x ou supérieure de Git pour Windows, il y a aussi un fichier de configuration
système  à  
C:\Documents  and  Settings\All  Users\Application  Data\Git\config
  sur  Windows  XP,  et
dans 
C:\ProgramData\Git\config
 sur Windows Vista et supérieur. Ce fichier de configuration ne peut
être modifié qu’avec la commande 
git config -f <fichier>
 en tant qu’administrateur.
Votre identité
La première chose à faire après l’installation de Git est de renseigner votre nom et votre adresse de
courriel.  C’est  une  information  importante  car  toutes  les  validations  dans  Git  utilisent  cette
information et elle est indélébile dans toutes les validations que vous pourrez réaliser :
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
Encore une fois, cette étape n’est nécessaire qu’une fois si vous passez l’option 
--global
, parce que
Git  utilisera  toujours  cette  information  pour  tout  ce  que  votre  utilisateur  fera  sur  ce  système.  Si
vous souhaitez surcharger ces valeurs avec un nom ou une adresse de courriel différents pour un
projet  spécifique,  vous  pouvez  lancer  ces  commandes  sans  option  
--global
  lorsque  vous  êtes  dans
ce projet.
De nombreux outils graphiques vous aideront à le faire la première fois que vous les lancerez.
Votre éditeur de texte
À  présent  que  votre  identité  est  renseignée,  vous  pouvez  configurer  l’éditeur  de  texte  qui  sera
utilisé  quand  Git  vous  demande  de  saisir  un  message.  Par  défaut,  Git  utilise  l’éditeur  configuré  au
niveau  système,  qui  est  généralement  Vi  ou  Vim.  Si  vous  souhaitez  utiliser  un  éditeur  de  texte
différent, comme Emacs, vous pouvez entrer ce qui suit :
$ git config --global core.editor emacs
20
WARNING
Vim  et  Emacs  sont  des  éditeurs  de  texte  populaires  chez  les  développeurs  sur
les systèmes à base Unix tels que Linux et Mac. Si vous n’êtes habitué à aucun
de  ces  deux  éditeurs  ou  utilisez  un  système  Windows,  il  se  peut  que  vous
deviez  chercher  les  instructions  pour  renseigner  votre  éditeur  favori.  Si  vous
ne renseignez pas un éditeur et ne connaissez pas Vim ou Emacs, vous risquez
fort d’avoir des surprises lorsqu’ils démarreront.
