# Disponibilité et la durabilité en termes de "neufs" : 

- voici un petit exercice pour comprendre ces concepts, notamment dans le contexte d'AWS.

### 1. Calcul de la Disponibilité (SLA)
La disponibilité se mesure généralement en pourcentage de temps où un service est opérationnel et accessible. Par exemple, une disponibilité de "11 neufs" signifie 99.999999999% de disponibilité.

Pour calculer le temps d'indisponibilité permis par cette disponibilité :

\[ \text{Temps total} = 1 \text{ année} = 365 \times 24 \times 60 \times 60 = 31\,536\,000 \text{ secondes} \]

\[ \text{Temps d'indisponibilité} = \text{Temps total} \times (1 - \text{Disponibilité}) \]

\[ \text{Disponibilité} = 99.999999999\% = 0.99999999999 \]

\[ \text{Temps d'indisponibilité} = 31\,536\,000 \times (1 - 0.99999999999) \]

\[ \text{Temps d'indisponibilité} = 31\,536\,000 \times 0.00000000001 \]

\[ \text{Temps d'indisponibilité} = 0.31536 \text{ secondes par an} \]

Cela signifie qu'avec une disponibilité de 11 neufs, votre service peut être indisponible pendant environ 0.31536 secondes par an.

### 2. Calcul de la Durabilité
- La durabilité est la probabilité qu'une donnée stockée reste intacte sur une période donnée.
- Pour AWS, si on parle d'une durabilité de "11 neufs", cela signifie 99.999999999% de durabilité.

Si vous avez 1 million de fichiers :

\[ \text{Nombre de fichiers perdus} = \text{Nombre total de fichiers} \times (1 - \text{Durabilité}) \]

\[ \text{Durabilité} = 99.999999999\% = 0.99999999999 \]

\[ \text{Nombre de fichiers perdus} = 1\,000\,000 \times (1 - 0.99999999999) \]

\[ \text{Nombre de fichiers perdus} = 1\,000\,000 \times 0.00000000001 \]

\[ \text{Nombre de fichiers perdus} = 0.01 \text{ fichiers} \]

Cela signifie qu'avec une durabilité de 11 neufs, en moyenne, vous pourriez perdre 0.01 fichiers sur 1 million de fichiers stockés chaque année.

Ces calculs sont importants pour comprendre les implications des SLAs et garantir les exigences de qualité de service pour vos applications sur AWS.
