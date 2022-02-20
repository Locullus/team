# ajout depuis le PC

L'invitation à collaborer a été lancée et acceptée.
Le projet a été cloné sur le PC.
J'ajoute ce fichier pour tester progressivement l'intégration sur main sans créer de conflits.

On va s'attacher à toujours développer sur une branche feature.

## commit de dimanche 14:28

On teste une modification pour faire une PR et vérifier qu'elle peut être tirée une faois validée depuis une branche autre que main sur un autre compte

## la commande ne fonctionne pas comme attendu

En vérité faire ```git pull origin main``` depuis une branche autre que ```main``` a pour résultat de faire un merge de ```main``` dans la branche courante.
La procédure implique donc de faire un changement de branche avant de faire le ```pull```.
