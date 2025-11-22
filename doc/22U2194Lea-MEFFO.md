--------------------------------------------------------------------------------------------------------------------------------------
# SUIVI PERSONNEL DE L'ETUDIANT
---------------------------------------------------------------------------------------------------------------------------------------

## Étude et Implémentation des Algorithmes de Descente de Gradient : Pas Optimal vs. Pas Fixe


##  Informations
- **NomS & pRENOMS :** MEFFO TAHAFO LEA JECY
- **Matricule:** 22U2194
- **Spécialité :** MASTER 1 SPÉCIALITÉ DATASCIENCES 
- **Projet :**Optimisation Numérique Sans Contraintes (Chapitre 2)


-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
##  Objectifs personnels
- **Contexte :** Comprendre l'impact des stratégies de recherche linéaire (**pas optimal** et **pas fixe**) sur la vitesse et la robustesse des algorithmes de gradient.
- **Structure :** Maîtriser la dérivation de la formule du pas optimal pour une fonction quadratique donnée.
- **Application :** Implémenter et analyser le comportement de **divergence/convergence** en fonction du choix du pas $s$ (fixe).

---

## Qu'est-ce que l'Optimisation Numérique sans Contraintes ?

L'optimisation numérique sans contraintes vise à trouver le minimum d'une fonction $f(\mathbf{x}): \mathbb{R}^n \rightarrow \mathbb{R}$ sans aucune restriction sur le domaine de $\mathbf{x}$.

### Contexte : Le Problème d'Optimisation Cible

L'expérimentation porte sur la minimisation de la fonction quadratique **strictement convexe** suivante :

$$\min_{\mathbf{x} \in \mathbb{R}^2} f(x, y) \quad \text{où} \quad f(x, y) = \frac{1}{2}x^2 + \frac{7}{2}y^2$$

Le minimum global est $\mathbf{x}^*=(0, 0)$.

### Fondamentaux Théoriques : Le Pas en Descente de Gradient

Le principe de la descente de gradient est la mise à jour : $\mathbf{x}_{k+1} = \mathbf{x}_k - s_k\nabla f(\mathbf{x}_k)$.

#### Pas Optimal ($s_{\text{optimal}}$)

* **Définition :** Il est calculé pour minimiser *exactement* la fonction le long de la direction de descente.
* **Formule Analytique (Cas Quadratique) :** Pour $f(\mathbf{x})=\frac{1}{2}\mathbf{x}^\top \mathbf{A}\mathbf{x}$, le pas optimal est :
    $$s_k = \frac{\nabla f(\mathbf{x}^k)^\top \nabla f(\mathbf{x}^k)}{\nabla f(\mathbf{x}^k)^\top \mathbf{A} \nabla f(\mathbf{x}^k)}$$
* **Caractéristique :** Garantit la descente et provoque le phénomène de **zigzag** (directions successives orthogonales) lorsque la fonction est mal conditionnée.

#### Pas Fixe ($s_{\text{fixe}}$)

* **Définition :** La valeur du pas $s$ est constante à chaque itération.
* **Condition de Convergence :** Pour garantir la convergence, $s$ doit être borné par les propriétés de la **Hessienne** ($\mathbf{A}$) :
    $$0 < s < \frac{2}{\lambda_{\max}}$$
    où $\lambda_{\max}$ est la plus grande valeur propre de $\mathbf{A}$.

### Application Numérique : $f(x, y)$

Pour la fonction $f(x, y)=\frac{1}{2}x^2+\frac{7}{2}y^2$, la Hessienne est $\mathbf{A}=\begin{pmatrix} 1 & 0 \\ 0 & 7 \end{pmatrix}$, donc $\lambda_{\max}=7$.

La condition de convergence est : $0 < s < \frac{2}{7} \approx 0.2857$.



##  Architecture Globale - Implémentation Python et Analyse

L'implémentation a permis d'analyser les deux approches :

* **Calcul du pas optimal ($s_k$) :** La fonction `descente_gradient_optimal` intègre la formule analytique pour $s_k$, garantissant l'étape (2.b) $f(\mathbf{x}_{k+1}) < f(\mathbf{x}_k)$ sans vérification explicite.
* **Vérification de la divergence :** La fonction `descente_gradient_fixe` utilise un test de sécurité (`if f(x_k_plus_1) > f(x_k): break`) pour arrêter l'algorithme lorsque $s_{\text{fixe}}$ est trop grand ($s=0.5$), confirmant la théorie.



##  Journal de travail

| Jour | Date | Activités |
| :--- | :--- | :--- |
| Jour 1 | [20 Nov 2025 ] | **Relecture théorique** : Conditions d'optimalité 1er/2nd ordre et formule générale du pas optimal pour les quadratiques. |
| Jour 2 | [20 Nov 2025] | **Implémentation Python** : Définition de $f(x,y)$, $\nabla f(x,y)$, et codage de l'algorithme à pas optimal ($s_k$). **Dérivation :** Calcul de la condition $s < 2/7$. |
| Jour 3 | [21 Nov 2025] | **Implémentation et Analyse du Pas Fixe** : Test des pas $s=0.25$ (convergence rapide), $s=0.01$ (convergence lente), et $s=0.5$ (divergence) en intégrant le critère d'arrêt de divergence. |
| Jour 4 | [21 Nov 2025] | **Visualisation** : Génération des lignes de niveau et tracé du chemin de descente. Analyse du phénomène de zigzag pour le pas optimal (malgré son "optimalité"). |



### Compétences acquises

* **Théorie :** Compréhension approfondie des conditions d'optimalité du 1er ordre ($\nabla f = 0$).
* **Calcul Analytique :** Capacité à dériver la formule exacte du pas optimal pour un problème quadratique donné.
* **Robustesse :** Compréhension des enjeux du choix du pas $s_{\text{fixe}}$ et de la nécessité d'une condition de Lipschitz/valeurs propres pour la convergence.
* **Compétences Techniques :** Implémentation des algorithmes de descente de gradient en Python (NumPy) et visualisation des chemins d'optimisation (Matplotlib).

## Améliorations futures

* **Méthode de Newton :** Étudier et implémenter la **méthode de Newton** (qui utilise la Hessienne) pour observer une convergence quadratique (très rapide) et la comparer aux méthodes de gradient.
	
	
	
	
	
	
	
