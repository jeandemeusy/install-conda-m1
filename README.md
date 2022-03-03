# Guide d'installation de Python pour Apple Silicon

## Installer HomeBrew
On pourrait aller sur Miniforge GitHub et suivre les instructions en lançant des commandes shell. Mais il y plus simple, en utilisant Homebrew.
Pour l'installer (si il n'est pas déjà présent sur votre Mac), exécutez la commande suivante dans le Terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Une fois que c'est fait, vous êtes prêt à utiliser [Homebrew](https://brew.sh/).

## Installer Miniforge

Une fois Homebre installé, tapez la commande suivate dans le Terminal:
```bash
brew install miniforge
```

Une fois l'installation terminée, il faut encore lié les fichiers `.bashrc` et `.zshrc` à conda. Pour cela, lancez la commande `conda init zsh` dans le Terminal. Redémarrez le Terminal, et c'est fini ! 🎉

## Miniforge

Miniforme se comporte comme la conda dans le Terminal, vous avez accès aux mêmes commandes.

Voici une liste non-exhaustive des commandes couramment utilisées:

### Création d'en environment virtuel

Créer un environnement virtuel:
```bash
conda create --name <ENV-NAME>
```

Créer un environnement virtuel avec une version spécifique de Python:
```bash
conda create -n <ENV-NAME> python=<VERSION>
```

Activer un environnement virtuel:
```bash
conda activate <ENV-NAME>
```


Naturellement, `conda` va stocker l'envrionnement virtuel dans un dossier perdu. Il est possible de spécifier le dossier parent où enregistrer l'envrionnement. Pour cela:
```bash
conda create --prefix <PATH/TO/PARENT>/<ENV-NAME>
```

Pour activer un envrionment virtuel généré avec la commande précédente (aka dans un dossier spécifié):
```bash
conda activate <PATH/TO/PARENT>/<ENV-NAME>
```

### Informations liés au environnement conda

Pour obtenir une liste des environnements accessibles par conda:
```bash
conda info --envs
```
ou
```bash
conda env list
```

Une fois un environnement activé, pour obtenir la liste des packages inclus:
```bash
conda list
```
### Désactivation d'un environnement

Pour désactiver l'environnement:
```bash
conda deactivate
```

### Installer des packages dans un environnement conda
Une fois l'envrionnement activé !!

Pour installer un package disponible sur conda:
```bash
conda install <PACKAGE>
```

Pour installer une version spécifique d'un package:
```bash
conda install <PACKAGE>=<PACKAGE-VERSION>
```

Si l'envrionnement n'est pas activé:

```bash
conda install <PACKAGE>=<PACKAGE-VERSION> -n <ENV-NAME>
```

ou

```bash
conda install <PACKAGE>=<PACKAGE-VERSION> -n <PATH/TO/PARENT>/<ENV-NAME>
```
