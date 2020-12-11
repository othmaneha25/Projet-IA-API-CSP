
#                       ---------------------------------------------------------------------------------
# 			|	 Thème| Modèles basés sur les variables: CSP et réseaux bayésiens 
#			         Binôme : Othmane Elhamdouni & Imene Ouahrani     			|
#                       ---------------------------------------------------------------------------------


#Référence : CS 221 - Pense-bête des modèles basés sur les variables (stanford.edu)

#(*)-Ce projet est un solutionneur de problèmes de satisfaction de contraintes utilisant le backtracking (retour en arrière) et le forward check.

1. Le retour en arrière (retour sur piste/backtracking) : le principe de cet algorithme est de tester toutes les solutions possibles pour résoudre un problème de données. L'orsque le programme a testé toutes les possibilités d'une branche, il revient en arrière pour explorer les chemins restants qu'il n'a pas pris d'où le nom retour sur trace. Ces opérations sont répétées jusqu'à explorer toutes les pistes. Les algorithmes de backtracking utilise la réccursivité au sein d'une fonction qui s'appelle elle même.

2. Filtrage (Filtering): garder une trace des domaines pour les variables non attribuées et rayer les mauvaises options
Vérification avant: rayer les valeurs qui violent une contrainte lorsqu'elles sont ajoutées à l'affectation existante

3. La vérification avant (Forward checking) : contrôle uniquement les contraintes entre la variable courante et les variables futures. 
L'avantage de look ahead est qu'il détecte également les conflits entre les futures variables et permet donc d'élaguer les branches de l'arbre de recherche qui conduiront à un échec plus tôt qu'avec la vérification avant.

-----------------------------------------------------------------------------------------------------------------------------------------
#(**)-Fonctionnement :

1. Le CSP choisit la variable en fonction de l'heuristique de variable la plus contrainte, rompant les liens en utilisant l'heuristique de variable la plus contraignante. L'algorithme peut trouver plusieurs solutions viables.
2. S'il reste plus d'une variable après l'application de ces heuristiques, rompez les liens par ordre alphabétique.
3. Le CSP choisit les valeurs en fonction de l'heuristique de valeur la moins contraignante.
4. Le dossier "Cas de test" contient 3 exemples de cas de test.

-----------------------------------------------------------------------------------------------------------------------------------------
#(***)-Exécution

Arguments de ligne de commande:
1. Fichier .var contenant une liste de variables.
2. Fichier .con qui contient une liste de contraintes.
3. procédure de mise en cohérence "aucun" pour le retour arrière uniquement et "fc" pour le retour arrière avec contrôle avant.

#Exemples d'arguments:

python3 app.py Tests/ex1.var Tests/ex1.con Tests/fc

python3 app.py Tests/ex2.var Tests/ex2.con aucun
