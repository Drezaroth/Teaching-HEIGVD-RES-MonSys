#README


Welcome
============================

AUTHOR:
Calixte Melly
Nguyen-Phuong, Le

Etat des lieux:
============================
Nous avons fini le laboratoire.
Nous avons pu accèder aux deux sites et afficher le contenu correcte.

Nous avons eu un problème avec le fichier default car lorsque on utilisait un navigateur nous arrivions sur la page d'apache2 (it works)
mais nous avons pu le résoudre et maintenant cela fonctionne.

Description des manipulations:
==============================
Nous avons modifié les fichiers suivants :

-Vagrantfile -> Pour créer les 3 contenaires
-hosts -> pour la résolution DNS
-default -> pour modifierla config du reverse proxy

Nous avons créé les fichiers suivants:

-live.clashofclasses.ch.conf -> pour ajouter l'hôte virtuel et spécifier le documentRoot
-dashboard.clashofclasses.ch.conf -> pour ajouter l'hôte virtuel et spécifier le documentRoot