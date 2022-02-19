# team

modification depuis linux.
La clé ssh a été ajoutée sur linux

NOTE : les git pull ne concernent bien QUE la branche sur laquelle le pull est fait !
Les git st sur une branche ne reflettent pas forcément l'état du repo distant... Faire un git pull met à jour des fichiers alors que le status annonce le contraire.

Le fait de développper sur la branche develop provoque des conflits, ce qui n'arrive pas quand on développe sur une branche par fonctionnalité que l'on PR ensuite avec develop.

Le workflow semble être le suivant :
- ne jamais coder sur main !
- créer une branche de référence commune nommée develop
- personne ne code non plus sur cette branche qui est utilisée come référenciel pour les PR
- le développement doit sde faire sur des branches par foncxtionnalité.

Une fois la fonctionnalité terminée, le dev fait : 
```bash
git checkout develop
git pull
git merge