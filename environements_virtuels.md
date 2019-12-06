# Environements Virtuels

## Conda
Anaconda est un gestionnaire de paquet doublé d'une plateforme de développement. Il intègre a la fois la gestion d'environnements virtuels et la possibilité d'utiliser les outils tels que Spyder ou Jupyter. La documentation officielle est ici : https://docs.anaconda.com/anaconda/

### Installation
Télécharger la version correspondant a vos besoins depuis : https://www.anaconda.com/distribution/
Sous linux, mettre a jour les packages necessaires puis exécutez l'installeur précédemment téléchargé :

``` 
apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
bash Anaconda3-versionxx.sh
```
### Usage
L'exemple suivant permet de créer et installer des paquets pour python 3.7 depuis un terminal :
``` 
conda create -n myEnv python=3.7
conda activate myEnv
conda install packagexx
conda install --file requirements.txt
```
### Configuration PyCharm

Depuis votre projet existant ou au démarrage d'un projet, allez dans "Project interpreter" 
(File > Settings > Project: myProject > Project interpreter) or (ctrl+maj+s > Project interpreter)

Cliquez sur l'icone paramètres puis add > Conda Environment 
Choisissez ensuite de créer un nouvel environnement ou d'utiliser un environnement existant



## Virtualenv et virtualenvwrapper

Virtualenv est une librairie permettant de créer des environements virtuels python, cependant, la semantique de cette
librairie n'est pas très pratique, virtualenvwrapper à donc été crée pour simplifier l'usage de la librairie.

### Installation
```shell script
pip3 install virtualenv 
pip3 install virtualenvwrapper 
```

Ajouter ces lignes à la fin du fichier ~/.bashrc : 
```
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/Devel
source /usr/local/bin/virtualenvwrapper.sh
```

Et : 
```shell script
source ~/.bashrc
```

Si après le source une erreur no such file or directory apparait : 
```shell script
sudo find / -name virtualenvwrapper.sh
```
Recopier le path du ficher dans le bashrc à la place de `/usr/local/bin/virtualenvwrapper.sh`

### Usage
```shell script
mkvirtualenv env_name # create env
workon env_name # activate env (autocompletion with tab, allow to see all availiable envs) 
deactivate # quit env
```
Une fois l'environement activé, le nom apparaît entre parenthèse en début de ligne dans le terminal : 

`(env_name) user@machine :~$`

## Pycharm

Lors de la création d'un nouveau projet dans PyCharm, cette fenêtre s'ouvre.

![VenvPycharm](imgs/venv/venv.png "virtual env pycharm")

`Il faut surtout être attentif à la version de python selectionnée (Base Interpreter).`

L'IDE laisse également la possibilité d'utiliser un environement virtuel déjà existant.  
