#README


Welcome
============================

AUTHOR:
Calixte Melly
Nguyen-Phuong, Le

Etat des lieux:
============================
Nous avons fini le laboratoire.
Nous avons pu acc�der aux deux sites et afficher le contenu correcte.

Nous avons eu un probl�me avec le fichier default car lorsque on utilisait un navigateur nous arrivions sur la page d'apache2 (it works)
mais nous avons pu le r�soudre et maintenant cela fonctionne.

Description des manipulations:
==============================
Nous avons modifi� les fichiers suivants :

-Vagrantfile -> Pour cr�er les 3 contenaires
-hosts -> pour la r�solution DNS
-default -> pour modifierla config du reverse proxy

Nous avons cr�� les fichiers suivants:

-live.clashofclasses.ch.conf -> pour ajouter l'h�te virtuel et sp�cifier le documentRoot
-dashboard.clashofclasses.ch.conf -> pour ajouter l'h�te virtuel et sp�cifier le documentRoot