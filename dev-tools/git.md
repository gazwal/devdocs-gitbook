# Git

## .gitignore

Exemples pour la rédaction d'un .gitignore

{% embed url="https://stackoverflow.com/questions/10712555/gitignore-all-files-of-extension-in-directory" %}



## GITHUB

**Adding an existing project to GitHub using the command line :**  
[https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line](https://help.github.com/en/github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line)

```text
// push an existing repository from the command line
git remote add origin https://github.com/gazwal/xxs-evc.git
git push -u origin master

```

## Commandes

```text
//
$ git status

//
$ git add .
$ git commit -am "mise à jour"
$ git push origin master


// A good way to have a synthetic view of what's going on "origin"
$ git remote show origin


// créer un tag
$ git tag 2020.04.28

// pousser un tag
$ git push origin 2020.04.28

// lister les tags
$ git tag
2020.04.28
```

[https://gist.github.com/bdlangton/b47be9dc85992b99d5fa1d83e93a94f8](https://gist.github.com/bdlangton/b47be9dc85992b99d5fa1d83e93a94f8) :

{% embed url="https://gist.github.com/bdlangton/b47be9dc85992b99d5fa1d83e93a94f8" %}



