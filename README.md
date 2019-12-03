# TowardBetterPython

Some ideas and guidelines for a better world !

La première recommandation générale est d'en finir avec Python 2 :Python 2 et mort, vive Python 3 ! (Dans l'idéal il faudrait vérifier que le code reste compatible avec Python2)


## Mettre en place un environnement de developpement

Un bon environnement permet d'avoir un esprit sain pour un code sain. 

* Environnement Python : pour éviter les embrouilles au niveau de la gestion des versions de Python et des différentes versions de packages en fonction des différents projet, la première chose a mettre en place est un environnement virtuel, pyenv, virtualenv ou Anaconda. Cet environnement porte le nom du projet, contient les versions de python et de package propre au projet et tous vous permettent de faire un export des modules utilisés dans ce projet pour crée par exemple un fichier de requierments.txt. L'avantage est de produire un code reproductible partout, testable sous différentes versions de python (il suffit d'exporter les requirements et de créer un autre environnement virtuel), d'avoir un management assez fin des versions de package (particulièrement utile pour les librairies Tensorflow / Keras), le tout sans pourrir l'install python de votre ordinateur.

* IDE : a moduler en fonction du projet et des besoins (travail collaboratif, travail dans le cloud...) : https://python.doctor/page-editeurs-python-gratuits-payants-ide
On est plus a l'âge du bronze, si le code a produire n'est pas un simple script de 30 lignes, on évite de coder salement dans Vim, Nano, Emacs. Si ça dépasse 50 lignes on oublie également Atom et Sublime text. 
Les utilisateurs d'Anaconda auront directement intégré Spyder dans les packages, IDE simple et efficace. Sinon la tendance est a PyCharm, Community Edition parce que gratuite. 
Il intègre toutes les features de dev d'un Eclipe ou NetBeans, adaptées a Python. Il vous souligne votre code faux, il intègre directement la gestion de version (Git, SVN) ainsi que les environnement virtuels, crée des tests, gère la doc, moyennant quelques modules il inteprète beaucoup de formats et fait un affichage sympathique (.md, .csv, images, .html, .pdf...)


* Prévoir à l'avance de créer de la doc : D'autant plus facile sous PyCharm qui intègre déjà les outils pour le faire  
https://www.jetbrains.com/help/pycharm/settings-tools-python-integrated-tools.html (choisir un format et s'y tenir tout le long du code, les dernières tendances valorisent la syntaxe "Google", plus compact et plus lisible. Pycharm intègre un visualisateur intégré, sinon pour générer la doc il faut passer par Napoleon https://sphinxcontrib-napoleon.readthedocs.io/en/latest/

* Pour la gestion de version, mettre en place un GitHub dès le début du projet (ça évite de devoir faire des fusions par la suite) https://kbroman.org/github_tutorial/pages/init.html

* Toujours dans le versionning, si on utilise un semantic versionning, il y a quelques bonnes pratiques pour se faciliter la vie : https://semver.org


## Structure de projets
On peut réflechir a l'avance a la structuration du code. Sous Python la "fléxibilité" (version lissée de foutoir) implique la difficulté de rendre le code opérationnel.

## Main guidelines for code writting 

https://www.python.org/dev/peps/pep-0008/

* Indentation : 4 espaces pas plus
* Utiliser 'import module' au lieu de 'from module import...' : améliore la lisibilité dans le code lors de l'appel 'module.fonctionxouy() ; Permet d'éviter des doublons dans les noms de fonction.




