# FICHE DE SUJET

## Projet F3 --- Machine Learning / Prévision sur série temporelle

## 1. Identification du projet

  -----------------------------------------------------------------------
  Élément                             Information
  ----------------------------------- -----------------------------------
  Étudiante                           Saber Sara --- Code Apogée :
                                      23009075

  Groupe / filière                    Groupe 3 --- S7 Finance

  Intitulé                            Prévision de l'inflation
                                      sous-jacente américaine à 12 mois
                                      (IPC hors alimentation et énergie
                                      --- CPILFESL)

  Période étudiée                     Janvier 1957 à octobre 2026
                                      (données mensuelles ; 838
                                      observations indiquées dans le
                                      notebook)

  Source des données                  FRED --- série CPILFESL ; source
                                      primaire : U.S. Bureau of Labor
                                      Statistics (BLS).
  -----------------------------------------------------------------------

## 2. Contexte et intérêt du sujet

L'inflation sous-jacente correspond ici à l'évolution des prix à la
consommation hors alimentation et énergie. Cette mesure est utilisée
pour observer une tendance des prix moins influencée par les
fluctuations parfois fortes de ces deux composantes. Anticiper son
évolution à douze mois peut éclairer les décisions des banques
centrales, les prévisions budgétaires des entreprises et l'analyse des
marchés obligataires.

## 3. Problématique

L'historique de l'indice des prix sous-jacent (CPILFESL) suffit-il à
prévoir l'inflation sous-jacente américaine douze mois à l'avance, mieux
que la simple persistance de l'inflation actuelle ?

## 4. Objectifs du travail

-   Construire la cible correspondant à l'inflation sous-jacente
    observée douze mois après la date de prévision.
-   Créer des variables explicatives à partir de l'historique de
    l'indice : retards de l'inflation, variations annualisées, moyenne
    mobile, accélération et volatilité.
-   Estimer un modèle de régression Ridge et le comparer à deux
    références naïves : la dernière valeur observée et la moyenne
    historique.
-   Évaluer les performances avec la RMSE comme métrique principale,
    puis la MAE et le coefficient R².

## 5. Données et variables

La variable brute est CPILFESL, indice mensuel désaisonnalisé dont la
base est 1982--1984 = 100. L'inflation sous-jacente sur douze mois est
calculée par :

**100 × (IPCₜ / IPCₜ₋₁₂ − 1)**

Les variables explicatives sont construites uniquement à partir des
informations disponibles à la date t. La cible est l'inflation à t+12.

Le notebook signale une observation manquante en octobre 2025, remplacée
par interpolation linéaire. Cette valeur reconstituée n'est pas une
publication officielle et constitue une limite à signaler dans
l'interprétation.

## 6. Méthodologie

Le problème est traité comme une régression sur série temporelle. Le
découpage apprentissage/test respecte l'ordre chronologique, avec une
période de test allant de 2010 à 2025. Le réglage des hyperparamètres
s'effectue sur l'échantillon d'entraînement à l'aide de GridSearchCV et
de TimeSeriesSplit (cinq plis, avec un écart de douze mois). La
standardisation est intégrée à un Pipeline afin qu'elle soit ajustée
uniquement sur les données d'entraînement.

Le modèle principal est la régression Ridge, qui ajoute une pénalisation
L2 aux coefficients de la régression linéaire. Cette méthode est retenue
pour stabiliser l'estimation lorsque les variables explicatives sont
corrélées, notamment les retards d'une même série.

## 7. Résultats principaux reportés dans le notebook

  -----------------------------------------------------------------------
  Indicateur                                                     Résultat
  ------------------------------ ----------------------------------------
  RMSE du Ridge sur le test                     1,03 point de pourcentage

  RMSE de la référence «                        1,20 point de pourcentage
  dernière valeur »              

  Écart relatif de RMSE               −14,2 % ; objectif initial de −10 %
                                                      atteint sur le test

  MAE du Ridge et de la                       0,78 pour les deux méthodes
  référence                      

  R² du Ridge                                                        0,37
  -----------------------------------------------------------------------

Le notebook précise toutefois que la validation croisée favorise la
référence « dernière valeur » et que le gain global du Ridge dépend
fortement de la période 2020--2023. Le modèle ne parvient pas à
anticiper le choc inflationniste de 2021--2022. Les résultats doivent
donc être interprétés avec prudence.

## 8. Limites et pistes d'amélioration

Les principales limites sont les révisions des données désaisonnalisées
(risque de biais d'anticipation), l'interpolation d'octobre 2025, les
changements de régime inflationniste, l'utilisation d'une seule série et
l'existence d'un seul découpage chronologique.

Des prolongements possibles seraient l'utilisation des millésimes
ALFRED, l'ajout de variables macroéconomiques (chômage, taux directeur,
anticipations d'inflation) et la répétition des tests avec d'autres
dates de coupure.

## 9. Livrable et dépôt

Notebook et code du projet : Dépôt GitHub ---
**23009075-SABER-SARA-Fin3**.

Date du projet indiquée dans le notebook : 17 novembre 2026.

------------------------------------------------------------------------

*Projet F3 --- Prévision de l'inflation sous-jacente américaine*
