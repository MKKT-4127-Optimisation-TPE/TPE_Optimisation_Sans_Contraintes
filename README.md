<div align="center">
    
# LISTE DES MEMBRES DU GROUPE

    
| Matricule | Noms et Prénoms |
|:---  | :--- |
| 22U2194| MEFFO TAHAFO LEA JECY  |
| 22U2080| TSEMEGNE MARTIN YVAN |
| 22t2894 | KELODJOU DJOMO NAFISSATOU IVANA |
| 22U2118 | KEMBOU FOSSO RICHEL |

</div>

# TPE : Optimisation Numérique Sans Contraintes

Ce dépot est le celui dans le lequel nous avons réalisé le 4e devoir portant sur l'optimisation sans contrainte.

L'objectif est d'implémenter des algorithmes de descente de gradient (pas fixe et pas optimal) et d'analyser leur convergence sur différentes fonctions.

## Notebooks

Chaque fonction étudiée fait l'objet d'un notebook Jupyter, contenant l'analyse théorique, l'implémentation Python et la visualisation des résultats.

POur avoir lire ou executer les différents notebooks il faut entrer dans le dossier **Notebooks** a la racine du projet 

*   **Fonction du Cours** : Experimentation_cours.ipynb
*   **Fonction de Rosenbrock** : Experimentation_Rosenbrock.ipynb
*   **Fonction Quadratique** : Experimentation_Quadratique.ipynb
*   **Fonction de Himmelblau** : Experimentation_Himmelblau.ipynb

##  Installation et Exécution

Pour tester ces notebooks sur votre machine locale :

1.  **Cloner le dépôt :**
    ```bash
    git clone https://github.com/MKKT-4127-Optimisation-TPE/TPE_Optimisation_Sans_Contraintes.git
    ```

2.  **Créer un environnement virtuel :**
    ```bash
    python -m venv venv
    # Windows
    venv\Scripts\activate
    # Linux/Mac
    source venv/bin/activate
    ```

3.  **Installer les dépendances :**
    ```bash
    pip install numpy matplotlib scipy jupyter
    ```

4.  **Lancer Jupyter Notebook :**
    ```bash
    jupyter notebook
    ```
