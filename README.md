# TowardBetterPython

Some ideas and guidelines for a better world !

La première recommandation générale est d'en finir avec Python 2 :Python 2 et mort, vive Python 3 ! (Dans l'idéal il faudrait vérifier que le code reste compatible avec Python2)


## Mettre en place un environnement de developpement

Un bon environnement permet d'avoir un esprit sain pour un code sain. 

* Environnement Python : pour éviter les embrouilles au niveau de la gestion des versions de Python et des différentes versions de packages en fonction des différents projet, la première chose a mettre en place est un environnement virtuel, pyenv, virtualenv ou Anaconda. Cet environnement porte le nom du projet, contient les versions de python et de package propre au projet et tous vous permettent de faire un export des modules utilisés dans ce projet pour crée par exemple un fichier de requierments.txt. L'avantage est de produire un code reproductible partout, testable sous différentes versions de python (il suffit d'exporter les requirements et de créer un autre environnement virtuel), d'avoir un management assez fin des versions de package (particulièrement utile pour les librairies Tensorflow / Keras), le tout sans pourrir l'install python de votre ordinateur.

* IDE : a moduler en fonction du projet et des besoins (travail collaboratif, travail dans le cloud...) : https://python.doctor/page-editeurs-python-gratuits-payants-ide
On est plus a l'âge du bronze, si le code a produire n'est pas un simple script de 30 lignes, on évite de coder salement dans Vim, Nano, Emacs. Si ça dépasse 50 lignes on oublie également Atom et Sublime text. 
Les utilisateurs d'Anaconda auront directement intégré Spyder dans les packages, IDE simple et efficace. Sinon la tendance est a PyCharm, Community Edition parce que gratuite. 
Il intègre toutes les features de dev d'un Eclipe ou NetBeans, adaptées a Python. Il vous souligne votre code faux, il intègre directement la gestion de version (Git, SVN) ainsi que les environnement virtuels, crée des tests, gère la doc, moyennant quelques modules il inteprète beaucoup de formats et fait un affichage sympathique (.md, .csv, images, .html, .pdf...). Il intègre également une version d'affichage "scientifique" permettant de voir tout un tas d'infos plus ou moins utiles


* Prévoir à l'avance de créer de la doc : D'autant plus facile sous PyCharm qui intègre déjà les outils pour le faire  
https://www.jetbrains.com/help/pycharm/settings-tools-python-integrated-tools.html (choisir un format et s'y tenir tout le long du code, les dernières tendances valorisent la syntaxe "Google", plus compact et plus lisible. Pycharm intègre un visualisateur intégré, sinon pour générer la doc il faut passer par Napoleon https://sphinxcontrib-napoleon.readthedocs.io/en/latest/

* Pour la gestion de version, mettre en place un GitHub dès le début du projet (ça évite de devoir faire des fusions par la suite) https://kbroman.org/github_tutorial/pages/init.html

* Toujours dans le versionning, si on utilise un semantic versionning, il y a quelques bonnes pratiques pour se faciliter la vie : https://semver.org


## Structure de projets
On peut réflechir a l'avance a la structuration du code. Sous Python la "fléxibilité" (version lissée de foutoir) implique la difficulté de rendre le code opérationnel.
Il faut garder en tête la programmation objet pour éviter de faire des doublons, des répétitions de code...

https://docs.python-guide.org/writing/structure/
Les guidelines sont un peu velues au début, mais il est possible de parametrer tout ça avec PyCharm, et surtout surtout, suivre ces recommandations permet a la fin d'en faire un beau package distribuable.
#TODO : extraire les infos principales

## Main guidelines for code writting 
[La doc complète est ici](https://www.python.org/dev/peps/pep-0008/)

Ci dessous les principales recommandations

* Indentation : 4 espaces pas plus
* Utiliser 'import module' au lieu de 'from module import...' : améliore la lisibilité dans le code lors de l'appel 'module.fonctionxouy() ; Permet d'éviter des doublons dans les noms de fonction.

* Les règles de nommage peuvent être importée depuis d'autres langages :
une_variable
une_fonction()
un_module
En revanche
UneClasse
UneException

> Evidemment, un nom est aussi explicite que possible.

* Les espaces : recommandation PEP8,
  * On colle des espaces avant et après  + - / * != >= <= not in or and
  * Pas d'espaces a l'intérieur {} [] () 
  * Un espace après : et , mais pas avant
  * Un espace dans les listes après , [1, 2] mais pas après : [1:2]

* Utiliser le \ lorsque la ligne dépasse 79 (?) caractères (sauf si l'on est dans une parenthèse, \ n'est pas nécessaire, comme dans le cas d'un loooong appel de fonction

* Les lignes vides :
  * Deux lignes vides avant la définition d'une fonction ou d'une classe, une seule avant la définition d'une méthode
  * Eventuellement une ligne pour séparer des sections logiques d'une fonction

* Les commentaires :
  * Toujours en anglais
  * Au même niveau d'indentation que le code qu'il commente
  * Chaque modification du code entraine la modification du commentaire concerné
 
  > Les docstrings expliquent comment utiliser le code, les commentaires expliquent pourquoi le code fonctionne

* Les docstrings (""" """) : 
  * [La PEP 257](https://www.python.org/dev/peps/pep-0257/) recommande d'écrire des docstrings avec des triples doubles guillemets
  * De manière générale, écrivez des docstrings pour les modules, les fonctions, les classes et les méthodes. Lorsque l'explication est courte et compacte comme dans certaines fonctions ou méthodes simples, utilisez des docstrings d'une ligne
  * Lorsque vous avez besoin de décrire plus en détail un module, une fonction, une classe ou une méthode, utilisez une docstring sur plusieurs lignes.
  * Formattez le contenu en fonction de la doc que vous utilisez (Numpy, Google, ...), le contenu essentiel pour les fonctions et les méthodes  sont : 
    * Ce que fait la fonction ou méthode
    * Ce qu'elle prend en argument
    * Ce qu'elle renvoie
    
> INUTILE DE TOUT FAIRE VOUS MEME, PyCharm s'en charge pour vous, moyennant de savoir utiliser un raccourci clavier.

> La syntaxe peut être validée par différents moyens, pep8online, pycodestyle, pydocstyle, pylint... PyCharm intègre un outils de validation du code qui vous affiche toutes les erreurs, les warnings et même des typos... Il est également possible de configurer Git avec Git Hooks pour executer des linter avant de faire le commit et bloquer le code qui ne repond pas aux normes

* Dans le cas d'un script il est important de respecter une structuration du script, d'une part cela atteste de votre travail, le rend plus facilement montrable, d'autre part cela vous facilitera la vie le jour ou il faudra reprendre le code, et cela facilitera la vie d'un autre dev qui reprendra un jour le code. __exemple dans structure_script.md__


# Developper avec la fonctionnalité et les tests 

2 acronymes a retenir : 
* BDD : Behavior Driven Development 
* TDD : Test Driven Development

Le BDD sert a répondre a la question du comportement que l'on souhaite
Ex : Etant donné une liste de gène, Quand un nouveau gène est ajouté, Alors il doit se trouver a la fin de la liste.

Le TDD sert a tester votre BDD, c'est clair ? Quelques règles pour se faire : 
* On doit écrire un test qui rate avant d'écrire le code
* On ne complique pas le test pour rien
* On écrit pas plus de code que ce dont il y a besoin pour passer le test qui échoue


https://radon.readthedocs.io/en/latest/index.html

