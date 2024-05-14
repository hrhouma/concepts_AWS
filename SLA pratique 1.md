# 1 - Exemple 1 - Disponibilité et la durabilité en termes de "neufs"

- Exercice pour comprendre ces concepts, notamment dans le contexte d'AWS.

### 1. Calcul de la Disponibilité (SLA)
La disponibilité se mesure généralement en pourcentage de temps où un service est opérationnel et accessible. Par exemple, une disponibilité de "11 neufs" signifie 99.999999999% de disponibilité.

Pour calculer le temps d'indisponibilité permis par cette disponibilité :

- *Temps total = 1 année = 365 * 24 * 60 * 60 = 31,536,000 secondes*
- *Temps d'indisponibilité = Temps total * (1 - Disponibilité)*
- *Disponibilité = 99.999999999% = 0.99999999999*
- *Temps d'indisponibilité = 31,536,000 * (1 - 0.99999999999)*
- *Temps d'indisponibilité = 31,536,000 * 0.00000000001*
- *Temps d'indisponibilité = 0.31536 secondes par an*

Cela signifie qu'avec une disponibilité de 11 neufs, votre service peut être indisponible pendant environ 0.31536 secondes par an.

### 2. Calcul de la Durabilité
La durabilité est la probabilité qu'une donnée stockée reste intacte sur une période donnée. Pour AWS, si on parle d'une durabilité de "11 neufs", cela signifie 99.999999999% de durabilité.

Si vous avez 1 million de fichiers :

- *Nombre de fichiers perdus = Nombre total de fichiers * (1 - Durabilité)*
- *Durabilité = 99.999999999% = 0.99999999999*
- *Nombre de fichiers perdus = 1,000,000 * (1 - 0.99999999999)*
- *Nombre de fichiers perdus = 1,000,000 * 0.00000000001*
- *Nombre de fichiers perdus = 0.01 fichiers*

- Cela signifie qu'avec une durabilité de 11 neufs, en moyenne, vous pourriez perdre 0.01 fichiers sur 1 million de fichiers stockés chaque année.
- Ces calculs sont importants pour comprendre les implications des SLAs et garantir les exigences de qualité de service pour vos applications sur AWS.


# Pour un service offrant une durabilité de 99% pour vos fichiers, avec 1000 objets stockés.

# 2 - Exemple 2 -  Durabilité avec 1000 Objets Stockés et Durabilité de 99%

Supposons que vous utilisiez un service de stockage en cloud offrant une durabilité de 99% pour vos fichiers.

#### Question 1 : Calcul de la Durabilité
Si votre entreprise stocke 1000 fichiers sur ce service, calculez combien de fichiers elle peut s'attendre à perdre en moyenne par an.

#### Réponse :

- **Nombre total de fichiers** : 1000
- **Durabilité** : 99% = 0.99
- **Nombre de fichiers perdus** = Nombre total de fichiers * (1 - Durabilité)
- **Nombre de fichiers perdus** = 1000 * (1 - 0.99)
- **Nombre de fichiers perdus** = 1000 * 0.01
- **Nombre de fichiers perdus** = 10 fichiers

Cela signifie qu'avec une durabilité de 99%, vous pourriez perdre en moyenne 10 fichiers sur 1000 fichiers stockés chaque année.

#### Question 2 : Impact Potentiel
Expliquez l'impact potentiel de la perte de ces fichiers sur une petite entreprise utilisant ces données pour des opérations critiques.

#### Réponse :

Avec la perte de 10 fichiers par an sur 1000, l'impact sur une petite entreprise peut être significatif, surtout si les fichiers perdus sont essentiels à ses opérations. Cette perte pourrait entraîner des interruptions d'activité, des pertes de données importantes pour les analyses ou des retards dans les processus. Cela met en évidence la nécessité pour les entreprises de mettre en œuvre des stratégies robustes de sauvegarde et de récupération pour atténuer les risques associés à ces pertes potentielles.


# 3 - Exercices  : 

- Je propose deux exercices basés sur les concepts de disponibilité et de durabilité pour aider à comprendre et appliquer ces concepts dans un contexte AWS.

## Exercice 1 : Calcul de Disponibilité

Supposons qu'une entreprise ait un SLA qui spécifie une disponibilité de 99.99% pour son service d'hébergement web. 

1. Calculez le temps d'indisponibilité maximal autorisé par an pour ce service en secondes.
2. Calculez le temps d'indisponibilité maximal autorisé par mois pour ce service en minutes.
3. Calculez le temps d'indisponibilité maximal autorisé par semaines pour ce service en minutes.
4. Si le service était indisponible pendant 2 minutes en un mois, a-t-il respecté son SLA? Justifiez votre réponse.

## Exercice 2 : Calcul de Durabilité

Une entreprise utilise un service de stockage cloud qui offre une durabilité de 99.999999999% pour ses fichiers.

1. Si l'entreprise stocke 10 millions de fichiers sur ce service, combien de fichiers peut-elle s'attendre à perdre en moyenne par an?
2. Expliquez l'impact potentiel de la perte de ces fichiers sur une entreprise qui utilise ces données pour des analyses critiques.

## Exercice 3 : Analyse Combinée de Disponibilité et Durabilité

- Une entreprise utilise un service de stockage en cloud pour ses bases de données critiques et un service d'hébergement web pour son application client.
- Le service de stockage offre une durabilité de 99.999% pour les fichiers, et le service d'hébergement web garantit une disponibilité de 99.95% pour l'accès à l'application.

### Partie 1 : Disponibilité de l'Hébergement Web

1. **Calculez le temps d'indisponibilité maximal autorisé par mois pour le service d'hébergement web en secondes et en minutes.**

   - **Nombre de secondes dans un mois** (approximativement 30 jours) = 30 * 24 * 60 * 60 = 2,592,000 secondes
   - **Disponibilité** = 99.95% = 0.9995
   - **Temps d'indisponibilité autorisé** = Temps total * (1 - Disponibilité)

2. **Si le service était indisponible pendant 10 minutes dans un mois donné, a-t-il respecté son SLA? Justifiez votre réponse.**

### Partie 2 : Durabilité du Service de Stockage

1. **Si l'entreprise stocke 500,000 fichiers sur ce service, calculez combien de fichiers elle peut s'attendre à perdre en moyenne par an.**
   
   - **Durabilité** = 99.999% = 0.99999
   - **Nombre de fichiers perdus** = Nombre total de fichiers * (1 - Durabilité)

2. **Décrivez l'impact de la perte de ces fichiers, en particulier si ces fichiers sont des sauvegardes de données transactionnelles critiques.**

### Partie 3 : Impact Combiné

1. **Évaluez l'impact global sur l'entreprise si le service d'hébergement web et le service de stockage subissent simultanément leurs pires indisponibilités dans le même mois.**

2. **Proposez des mesures de mitigation pour réduire les risques associés à ces indisponibilités et pertes de fichiers.**


  



