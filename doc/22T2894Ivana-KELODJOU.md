# CAHIER DE SUIVI PERSONNEL - KELODJOU DJOMO Nafissatou Ivana

## **TPE : Optimisation Sans Contraintes - Étude de Cas**

**Matricule :** 22T2894

---

## Jour 1 : 23 Novembre 2025

### 1. Contexte et Objectifs
Mon objectif de cette session était d'analyser le comportement des algorithmes d'optimisation (descente de gradient) sur une fonction spécifique non convexe : la **fonction quadratique**.
Il s'agissait de confronter les résultats numériques obtenus via un notebook Python avec la théorie des conditions d'optimalité (gradient et hessienne) vue en cours.

### 2. Travail Réalisé

#### A. Analyse Théorique
Avant toute expérimentation, j'ai appliqué les conditions nécessaires et suffisantes d'optimalité pour le cas sans contraintes :

* **Condition du 1er ordre (Point stationnaire) :**
    J'ai calculé le gradient $\nabla f(x, y) = \begin{pmatrix} 2x \\ -2y \end{pmatrix}$. En résolvant $\nabla f(x) = 0$, j'ai identifié un unique point critique à l'origine $(0, 0)$.

* **Condition du 2nd ordre (Nature du point) :**
    J'ai calculé la matrice Hessienne $H_f(x) = \begin{pmatrix} 2 & 0 \\ 0 & -2 \end{pmatrix}$.
    * *Analyse :* Les valeurs propres sont $\lambda_1 = 2$ et $\lambda_2 = -2$.
    * *Conclusion :* La matrice étant indéfinie (ni définie positive, ni définie négative), le point $(0,0)$ n'est pas un extremum local mais un **point selle**. La fonction n'est pas convexe.

#### B. Implémentation
* **Modélisation :** Codage de la fonction $f(x,y) = x^2 - y^2$ et de son gradient.
* **Algorithme :** Mise en place d'une descente de gradient à pas fixe.

#### C. Expérimentation et Visualisation
J'ai testé la robustesse de l'algorithme en variant le point de départ $x_0$ :
1.  **Départ sur l'axe X ($y=0$) :** L'algorithme converge vers $(0,0)$.
2.  **Départ hors de l'axe X ($y \neq 0$) :** L'algorithme diverge vers $-\infty$ selon l'axe des $y$.

Création d'un graphique des lignes de niveau (contour plot) pour visualiser la forme et les trajectoires de divergence.

### 3. Observations
* **Instabilité Numérique :** L'expérimentation confirme la théorie : bien que le gradient s'annule en $(0,0)$, aucun algorithme de descente standard ne peut s'y stabiliser durablement s'il y a la moindre perturbation sur $y$, car la courbure est négative dans cette direction (valeur propre $-2$).
* **Limites de la CN du 1er ordre :** L'annulation du gradient est une condition nécessaire mais piègeuse ici ; seule l'étude de la Hessienne permet de conclure à l'absence de minimum.

### 4. Conclusion
Ce travail démontre qu'un problème d'optimisation sur un ouvert (sans contraintes) nécessite une vérification rigoureuse de la convexité ou de la Hessienne. Pour la fonction quadratique $x^2 - y^2$, la recherche d'un minimum global est impossible car la fonction n'est pas bornée inférieurement.