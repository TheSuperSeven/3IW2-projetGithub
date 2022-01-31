# 3IW2-projetGithub
Projet GitHub

Pour bien mettre en place un projet d'une manière similaire.

Git init dans un dossier qui serviras uniquement à ce projet 

Déclarer vos informations dans votre config git (local ou globale) est aussi une bonne pratique
  
Lié une clé SSH à vôtre projet. 

ssh-key -t votreAlgoDeChiffrement -C "votre adressemail"

Récuperer le résultat de la clé SSH et aller dans votre profil GitHub pour rajouter la clé SSH dans la section "SSH and GPG keys"

Cela tombe bien, nous parlons de clé PGP (ou GPG en anglais).

Nous allons en profiter pour en créer une

Pour la créer c'est tout simple

gpg --full-gen-key

Ensuite il va nous demander le type de clé, ici nous voulons une clé par défault donc 1.

Ensuite autant prendre une clé longue donc la taille maximum de 4096 bits de longueur.

Ensuite autant faire en sorte que cette clé soit valide éternellement, mais dans certains contextes il peut être intéressant qu'elle ne le soit pas. Donc "0".

On va ensuite vous demander, votre nom, et votre adresse email et un commentaire.

La clé va prendre quelques secondes à se créer, par conséquent n'ayez pas peur.

On peut ensuite rajouter la clé sur github.

Pour la rajouter il faut copier la clé qui apparait quand on la génére, ensuite utiliser la commande
gpg --armor --export laCléQueVousVenezDeCopier

Pour la rajouter sur github il suffit de copier le retour de la commande précédente.

En cas de doute, github fourni une doc assez complète pour rajouter une clé efficacement, SSH ou GPG.


Avec ceci fait nous allons pouvoir nous attaquer à des choses plus intéressante.

Nous allons désigner la clé GPG comme notre clé pour signer nos commit. De cette manière on sauras que c'est bien vous !

Pour cela quelques lignes.

git config --global user.signingkey laCléQueVousVenezDeCopier

git config --global commit.gpgsign true (active la clé qui permet GPG) 

git commit -m "Mon premier commit signé !" 

Voilà, avec cela vos commit sont signé !

Pour notre projet nous allons créer deux autres branches. Une branches fix et une branche feature. Inutile de préciser l'utilité de ces deux branches.

git branch nomDeLaNouvelleBranche




