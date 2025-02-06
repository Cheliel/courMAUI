## Structure de données 

=> **Array** taille fix 

=> **List** taile modulable, recherche par index, typé à l'*init*

## SOLID 

### Single Responsability

Une classe a une seul responsabilité => faire du découpage 

- rendre plus facilement extensible 

### Dependance injection 

Retirer du couplage fort entre le jeu et nos module de haut niveau. Un module de haut niveau ne doit pas dépendre de l'inplémentation d'un lmodule de bas niveau. 
Il faut donc remplacer la dépendance par une interface.

### Open / Close 

En ajoutant Iplayer cela n'a pas d'impacte sur la calss Game. 


### Substitution de Liskov 

Principe de compatibilité, si je met des FakePLayer à la place des HumainPlayer cela doit continuer de fonctionner.


### Ségrégation de dépendance 

Si on crée une grosse interface qui a bcp de responsabilité dans certaines implémentations 
la classe ne pourra pafrois pas exécuter tout le code. il faut alors se pposer la question de la division de cette interface en deux pour simplifier sont implémentation.
En bref il faut le moins possible de **if(player is FakePlayer) => do**

## Typologie de test 

Il ne faut pas faire des tests sur tout mais en faire des utils !! 

### Test Unitaire
*c.f. pyramide*

Les **Test unitaire** sont selon cette pyramide les moins cher et le plus fiables. Ils sont ainsi à la base d'une procédure de test. e.g. player.GetNextMove()

Les **Test fonctionnel** s'assure que les fonctionalité métier sont bine implémenté. A l'inverse du test unitaire qui vérifie pas l'utilisation du code mais des petite fonctionalité bine préscise. 
Les test fonctionnel peuvent être écrit initalement en text parlé pour plus de compréhension de la fonctionalité métier. Ils devrons après être codé. 
Ils se placent au plus loin dans l'intéraction entre deux service, pour tester le maximum de fonctionlaité possible. Ils permettent d'ajouter réelement un utilisateur dans le client / formulaire / BBD avec des mocks. 
e.g. Game.play() 


Les **Test d'intégration** peuvent être fait avec un contrat de test et un faux server. 
Le principe est de jouer sont code face à un faux serveur. 
Ils sont assez fastidieux et couteux et peuvent perdre en fiabilité (de nouveau bug apparaîssents).


Les **Test E2E** ou **E**nd to **E**nd. Il a les test **Horizontaux** qui test l'intéraction entre les différents service : connexion à un profil, utilisation des fx de recherche, achat d'article. Les test **Verticaux** sont a effectuer étapes par étapes de manière chronologique. 
e.g. test graphique qui clique au bon endroit.

### Ecriture d'un test 

#### F.I.R.S.T

**Fast** => rapide à exécuter sinon flemme si ça prend 10s

**Independante** => le test doit avoir une seul raison d"échouer 

**Repeatable** => le test ne doit pas avoir 1/1000 chance d'échouer


**A**rrrange => **A**cte => **A**ssert 

**Given** => **When** => **Then** : pour des personnes qui ne sont pas du métier

Crée un *Project XUnit*

**[Fact]** => cette attribue au début de la classe permet à notre test d'être référencé dans la liste des tests. Il est à mettre devant chaque méthode 

**[Theorie]** => voir pour plus

*Le package fluentAssertion est pratique pour la lisibilité des assertions.*

## Test Driven Developpement

- Le principe est d'écrire le test en premier pour qu'il ne passe pas. 

- En principe, si le test est correcte tout de suite il n'y a pas de code a implémenter. 

### Ecriture 

**RED** => **GREEN** => **REFACTOR**

#### Création du BORD  

##### Ajouter un mouvement 

*// RED //*

    - Crée Board.playMove(1, 1, 'O') *(sans joueur)*

        - Rien dedans 

    - Dans le test vérifier que le move a été ajouter dans le liste

*// GREEN //*

    - Crée l'objet Cell  => record Cell(int Row, int Column) {public char Value {get;} }

    - Remplir la list avec des Cell 

    - Modifier PlayMove pour modifier une Cell de la liste

*// REFACTOR //*

    - Amélioration du Record Cell 

    - Extract la création du board en une fonction 


##### Mouvement Invalide 


*// RED //*

    - Jouer un mouvement invalide board.playMove(666, -666 666 666, 'X')
        - Modifier Play move pour avoir un résultat [bool]

    - Vérifier si playMove Renvoie True 


*// GREEN //*

    - Modifier playMove() => .firstOrDefault()

    - Modifier playMove() => pour vérifier la nullité de targetCell 

    - Modifier PlayMove pour modifier une Cell de la liste

*// REFACTOR //*

    - *none*

##### Cellule déjà prise 


*// RED //*

    - Jouer deux fois le même coup 

    - Vérifier si playMove Renvoie False 


*// GREEN //*

    - Modifier playMove() => targetCell.Value != vide => Return false 

*// REFACTOR //*

    - *none*

###### Grid empty return FALSE 

###### First column same value return TRUE

**/!\\**
**Lorsqu'un bug est repéré crée un test qui sera faux pour toujours le re-repéré /!\\** 

## Task / Async 

Il est possible de rendre une fonction asynchrone avec le type de retour avec **async Task**


## Commit 

@see => <a href="https://www.conventionalcommits.org/en/v1.0.0/"> conventionnal commit </a>

## Project

- 1 plateforme mini 

- CICD - azure 

=> formation de group 31 Janvier 

- Avril => première présention de l'app 

- Juin => soutenance de projet 

- 




