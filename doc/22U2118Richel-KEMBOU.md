## TPE D ' OPTIMISATION SANS CONTRAINTE (Himmelblau)


##  Informations
- **NomS &et Prénoms :** KEMBOU FOSSO RICHEL
- **Matricule:** 22U2118
- **Spécialité :**  DATASCIENCE



-----------------------------------------------------------------------------------------------------------------------------------------
### 1. Contexte et Objectifs

Mon objectif pour ce travail etait d'appliquer l'algorithme formel de descente de gradient  sur une fonction en optimisation : la **fonction de Himmelblau**.
Il s'agit de comparer l'efficacité des méthodes à **pas fixe** et à **pas optimal** et de visualiser les trajectoires de convergence sur les lignes de niveau


## Jour 1: 22 Novembre 2025   
### 2. Travail Réalisé
---
#### A. Analyse 
*   **Étude de la fonction de Himmelblau :**
    *   Formule : $f(x, y) = (x + y^2 - 7)^2 + (x^2 + y - 11)^2$.
    *   Analyse du gradient $\nabla f(x, y)$ = $[4x(x^2 + y - 11) + 2x + 2y^2 - 14, 2x^2 + 4y(x + y^2 - 7) + 2y - 22]$.
    *   On constate l'existence de 4 minimums globaux que sont : $ (3.0, 2.0),
    (-2.805118, 3.131312),
    (-3.779310, -3.283186),
    (3.584428, -1.848126)
$.
*   **Révision des Algorithmes :**
    *   **Gradient à pas fixe :** $x_{k+1} = x_k - s_k \nabla f(x_k)$ avec $s_k$ constant.
    *   **Gradient à pas optimal :** Le pas $s_k$ est recalculé à chaque itération pour minimiser $f$.

---

#### B. Implémentation 
*   Implémentation :
    *   `f_himmelblau(x)` : Calcule la valeur de la fonction.
    *   `grad_himmelblau(x)` : Calcule le vecteur gradient.
*   Codage de l'algorithme de **Descente de Gradient à Pas Fixe**.
*   Codage de l'algorithme de **Descente de gradient à pas optimal**.

---
#### C. Visualisation et Analyse
*   Création de graphiques contour (lignes de niveau) pour visualiser la vallée de la fonction. 
*   Superposition des trajectoires des itérations $(x_k)$ sur le graphique pour observer les mouvements caractéristiques de la descente.
*   Comparaison de la vitesse de convergence (nombre d'itérations) **entre la descente de gradient à pas fixe et pas optimal.**

--- 
### 3. $Observations$
* La convergence de cette fonction dépend plus des choix des points de départ dans l'algorithme. 
* Un mauvais choix d'un point même très proche d'un extrema $a$ au sens des moindres carrées peut mener à une convergence vers un autre extrema $b$ plus éloigné de ce point.

* On constate également que dans le cas précis, le nombre d'itérations pour un pas fixe de $0.01$ est plus grand que le nombre d'itération avec **$pas$ $optimal$.**, **ce qui correspond bien aux observations vues en cours**

---
### 4. Difficultés
La plus grande difficulté dans le processus de descnte de gradient de cette fonction est les valeurs des extremas à retrouver
-   Le gradient ne permet pas de trouver les valeurs des points critiques. 
- Cela se ramène à trouver les dérivées secondes et calculer les valeurs de x et y correspondantes.
- utiliser ces valeurs pour approximmer les extrema du Gradient de la fonction de Himmelblau
- Approximer les extrema à partir de ces valeurs

-----