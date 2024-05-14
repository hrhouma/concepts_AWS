# Disponibilité et la durabilité en termes de "neufs"

Voici un petit exercice pour comprendre ces concepts, notamment dans le contexte d'AWS.

### 1. Calcul de la Disponibilité (SLA)
La disponibilité se mesure généralement en pourcentage de temps où un service est opérationnel et accessible. Par exemple, une disponibilité de "11 neufs" signifie 99.999999999% de disponibilité.

Pour calculer le temps d'indisponibilité permis par cette disponibilité :

- Temps total = 1 année = 365 * 24 * 60 * 60 = 31,536,000 secondes
- Temps d'indisponibilité = Temps total * (1 - Disponibilité)
- Disponibilité = 99.999999999% = 0.99999999999
- Temps d'indisponibilité = 31,536,000 * (1 - 0.99999999999)
- Temps d'indisponibilité = 31,536,000 * 0.00000000001
- Temps d'indisponibilité = 0.31536 secondes par an

Cela signifie qu'avec une disponibilité de 11 neufs, votre service peut être indisponible pendant environ 0.31536 secondes par an.

### 2. Calcul de la Durabilité
La durabilité est la probabilité qu'une donnée stockée reste intacte sur une période donnée. Pour AWS, si on parle d'une durabilité de "11 neufs", cela signifie 99.999999999% de durabilité.

Si vous avez 1 million de fichiers :

- Nombre de fichiers perdus = Nombre total de fichiers * (1 - Durabilité)
- Durabilité = 99.999999999% = 0.99999999999
- Nombre de fichiers perdus = 1,000,000 * (1 - 0.99999999999)
- Nombre de fichiers perdus = 1,000,000 * 0.00000000001
- Nombre de fichiers perdus = 0.01 fichiers

- Cela signifie qu'avec une durabilité de 11 neufs, en moyenne, vous pourriez perdre 0.01 fichiers sur 1 million de fichiers stockés chaque année.
- Ces calculs sont importants pour comprendre les implications des SLAs et garantir les exigences de qualité de service pour vos applications sur AWS.
