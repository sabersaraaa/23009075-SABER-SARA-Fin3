# RÉFÉRENCES ET SOURCES CONSULTÉES

## Projet F3 --- Prévision de l'inflation sous-jacente américaine à 12 mois

Les références ci-dessous distinguent la source statistique utilisée
dans le projet, les organismes à l'origine des données et la
documentation technique correspondant aux méthodes et bibliothèques
mobilisées.

## A. Sources statistiques et économiques

1.  **Federal Reserve Bank of St. Louis --- FRED.** (s. d.). *Consumer
    Price Index for All Urban Consumers: All Items Less Food and Energy
    in U.S. City Average (CPILFESL).* Série mensuelle, désaisonnalisée,
    base 1982--1984 = 100. Source primaire indiquée : U.S. Bureau of
    Labor Statistics. Données extraites le 17 novembre 2026 selon le
    notebook.

    https://fred.stlouisfed.org/series/CPILFESL

2.  **U.S. Bureau of Labor Statistics.** (s. d.). *Consumer Price Index
    --- Questions and Answers.* Documentation officielle sur le calcul
    et l'interprétation de l'indice des prix à la consommation.

    https://www.bls.gov/cpi/questions-and-answers.htm

3.  **Federal Reserve Bank of St. Louis.** (s. d.). *FRED Terms of Use /
    FAQ.* Conditions d'utilisation et informations relatives aux droits
    associés aux données FRED.

    https://fred.stlouisfed.org/legal#fred-terms-faq

## B. Documentation technique --- méthodes de Machine Learning

4.  **scikit-learn developers.** *Ridge* --- régression linéaire avec
    régularisation L2 ; définition du paramètre alpha et de la fonction
    objectif.

    https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html

5.  **scikit-learn developers.** *TimeSeriesSplit* --- validation
    croisée adaptée aux données ordonnées dans le temps.

    https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html

6.  **scikit-learn developers.** *StandardScaler* --- standardisation
    des variables par centrage et réduction.

    https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html

7.  **scikit-learn developers.** *Pipeline* --- enchaînement des étapes
    de prétraitement et du modèle.

    https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html

8.  **scikit-learn developers.** *mean_squared_error* --- documentation
    de l'erreur quadratique moyenne, utilisée pour calculer la RMSE.

    https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html

## C. Supports pédagogiques et dépôt du projet

9.  **Support de cours :** notebook pédagogique « Tp_ML.ipynb »
    mentionné dans le notebook du projet. Il s'agit d'un document de
    cours fourni dans le cadre de l'enseignement ; aucun lien public
    n'est indiqué dans le fichier source.

10. **Saber Sara.** (2026). Dépôt GitHub du projet F3 :
    *23009075-SABER-SARA-Fin3*.

    https://github.com/sabersaraaa/23009075-SABER-SARA-Fin3.git

------------------------------------------------------------------------

Date de consultation des liens : 24 novembre 2026. La date d'extraction
des données utilisée dans le travail demeure celle indiquée dans le
notebook : 17 novembre 2026.

**Note de rigueur :** le notebook mentionne explicitement FRED/BLS, le
support Tp_ML.ipynb et la documentation scikit-learn. Les références
techniques ci-dessus détaillent les fonctions et méthodes visibles dans
le code ; elles constituent des liens documentaires complémentaires pour
faciliter la vérification et la reproduction du travail.

*Projet F3 --- Prévision de l'inflation sous-jacente américaine*
