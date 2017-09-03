# Prédiction d'ouverture de UrLab

[UrLab](http://urlab.be), un des deux hackerspaces de Bruxelles enregistre depuis fin 2012
l'état du hackerspace : ouvert ou fermé.

Le but de ce projet est de prédire (de 1h à 1 semaine à l'avance)
si le hackerspace sera ouvert à une heure donnée.

# Data

Les données se trouvent dans [`data`](data/)

 * [`events.json`](data/events.json) : L'entièreté des événements d'ouverture/fermeture taggés à la seconde près (approx. 2100 événements)
 * [`dataraw.csv`](data/dataraw.csv) : Les mêmes données, resamplées par heure. Une heure est comptée comme ouverte si le hackersapce a été ouvert au moins 30 minutes pendant cette heure
 * [`featurised_nikita.csv`](data/featurised_nikita.csv) : Un essai de featurisation de ces données avec les congés, les semaines académiques, ...
 * [`calendars`](data/calendars) : Les calendriers académiques de l'ULB (en pdf /o\\)

# Train/Validation

Pour l'instant, on entraine sur toutes les données sauf 2017 et on valide avec 2017.

Ce n'est clairement pas idéal, il faudrait faire mieux

# Metrics

On utilise le [MCC](https://en.wikipedia.org/wiki/Matthews_correlation_coefficient).

# Results

| Who  | How                | MCC  | Dataset                 |
|------|--------------------|------|-------------------------|
| C4   | AdaBoostClassifier | 0.56 | `featurised_nikita.csv` |
|      |                    |      |                         |
|      |                    |      |                         |
