# Identifier les services qui tourne sur un port

Pb rencontré : Lors de l'installation d'un nouveau projet back qui inpliquer l'utilisation  de Docker.
Le lancement de la bd mysql ne se faisait pas et retourné l'erreur :
```sh
sqlalchemy.exc.OperationalError: (pymysql.err.OperationalError) (1045, "Access denied for user 'lukoAdmin'@'localhost' (using password: YES)")
(Background on this error at: https://sqlalche.me/e/14/e3q8)
```
Cause du pb identifié : 
Le port utilisé pour faire tourner mysql via Docker etait en faite deja utilisé via une autre version mysql installer plusieurs mois en ammont pour un autre projet.

Pour verifier ce qui tourne ou si un port est disponible : `lsof -i tcp:3306`