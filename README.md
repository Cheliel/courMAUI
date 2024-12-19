
## Typologie de test 

Il ne faut pas faire des tests sur tout mais en faire des utils !! 

### Test Unitaire
*c.f. pyramide*

Les **Test unitaire** sont selon cettepyramide les moins cher et le plus fiables. Ils sont ainsi à la base d'une procédure de test.

Les **Test fonctionnel** s'assure que les fonctionalité métier sont bine implémenté. A l'inverse du test unitaire qui vérifie pas l'utilisation du code mais des petite fonctionalité bine préscise. 
Les test fonctionnel peuvent être écrit initalement en text parlé pour plus de compréhension de la fonctionalité métier. Ils devrons après être codé. 
Ils se placent au plus loin dans l'intéraction entre deux service, pour tester le maximum de fonctionlaité possible. Ils permettent d'ajouter réelement un utilisateur dans le client / formulaire / BBD avec des mocks. 

Les **Test d'intégrartion** peuvent être fait avec un contrat de test et un faux server. Le principe est de jouer sont code face à un faux serveur. Ils sont assez fastidieux et couteux et peuvent perdre en fiabilité (de nouveau bug apparaîssents).

Les **Test E2E** ou **E**nd to **E**nd. Il a les test **Horizontaux** qui test l'intéraction entre les différents service : connexion à un profil, utilisation des fx de recherche, achat d'article. Les test **Verticaux** sont a effectuer étapes par étapes de manière chronologique. 

### Ecriture d'un test 

**A**rrrange => **A**cte => **A**ssert 

Crée un *Project XUnit*

**[Fact]** => cette attribue au début de la classe permet à notre test d'être référencé dans la liste des tests

*Le package fluentAssertion est pratique pour la lisibilité des assertions.*

