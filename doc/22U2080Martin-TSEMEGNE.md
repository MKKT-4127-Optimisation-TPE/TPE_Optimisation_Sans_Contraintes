# CAHIER DE SUIVI PERSONNEL - TSEMEGNE Martin Yvan

## **TPE  : Optimisation Sans Contraintes**

**Matricule:**  22U2080 

---

## jour 1: 22 Novembre 2025   
### 1. Contexte et Objectifs
Mon objectif pour ce travail etait d'appliquer les algorithmes de descente de gradient  sur une fonction en optimisation : la **fonction de Rosenbrock**.
Il s'agit de comparer l'efficacité des méthodes à **pas fixe** et à **pas optimal** et de visualiser les trajectoires de convergence.

### 2. Travail Réalisé

#### A. Analyse 
*   **Étude de la fonction de Rosenbrock :**
    *   Formule : $f(x, y) = (1 - x)^2 + 100(y - x^2)^2$.
    *   Analyse du gradient $\nabla f(x, y)$.
    *   Identification du minimum global en $(1, 1)$ où $f(1, 1) = 0$.
*   **Révision des Algorithmes :**
    *   **Gradient à pas fixe :** $x_{k+1} = x_k - s \nabla f(x_k)$ avec $s$ constant.
    *   **Gradient à pas optimal :** Le pas $s_k$ est recalculé à chaque itération pour minimiser $f$ dans la direction opposée au gradient.

#### B. Implémentation 
*   Implémentation :
    *   `rosenbrock(x)` : Calcule la valeur de la fonction.
    *   `grad_rosenbrock(x)` : Calcule le vecteur gradient.
*   Codage de l'algorithme de **Descente de Gradient à Pas Fixe**.
*   Codage de l'algorithme de **Plus Profonde Descente** (avec recherche linéaire du pas optimal via `scipy.optimize.minimize_scalar`).

#### C. Visualisation et Analyse
*   Création de graphiques contour (lignes de niveau) pour visualiser la vallée de la fonction.
*   Superposition des trajectoires des itérations $(x_k)$ sur le graphique pour observer les zigzags caractéristiques de la plus profonde descente.
*   Comparaison de la vitesse de convergence (nombre d'itérations) en fonction du choix du pas.

### 3. Observations
*   **Sensibilité du pas fixe :** Avec la fonction de Rosenbrock (qui a de fortes variations de courbure), un pas fixe trop grand entraînait une divergence immédiate.
    *   *Solution :* Test de valeurs de pas très petites (ex: $10^{-3}$) pour garantir la stabilité.
*   **Calcul du pas optimal :** Contrairement à la fonction quadratique du cours, le pas optimal pour Rosenbrock n'a pas de solution analytique simple (polynôme de degré élevé).
    *   *Solution :* Utilisation d'une recherche linéaire numérique à chaque itération.

### 4. Conclusion Partielle
La fonction de Rosenbrock illustre les limites de la méthode de plus profonde descente : bien que convergente, elle zigzague énormément dans la vallée courbe, rendant la progression vers le minimum $(1, 1)$ très lente comparée à des fonctions plus simples (quadratiques).