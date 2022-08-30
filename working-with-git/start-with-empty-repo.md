# How to start with an empty repository?

This is copied out from an empty BitBucket repository. The commands below help starting with a new project.

## To get started you will need to run these commands in your terminal

### Configure Git for the first time

``` bash
git config --global user.name "{Your name: e.g. Elfen,Benjamin (IT EDS) BIP-DE-I}"
git config --global user.email "benjamin.elfen@boehringer-ingelheim.com"
```

### Working with your repository

I just want to clone this repository.  
If you want to simply clone this empty repository then run this command in your terminal.

``` bash
git clone ssh://git@bitbucket.biscrum.com:7999/~{firstname.lastname}_boehringer-ingelheim.com/{repository_name}.git
```

### My code is ready to be pushed

If you already have code ready to be pushed to this repository then run this in your terminal.

``` bash
cd existing-project
git init
git add --all
git commit -m "Initial Commit"
git remote add origin ssh://git@bitbucket.biscrum.com:7999/~benjamin.elfen_boehringer-ingelheim.com/portableapps.git
git push -u origin HEAD:main
```

### My code is already tracked by Git

If your code is already tracked by Git then set this repository as your "origin" to push to.

``` bash
cd existing-project
git remote set-url origin ssh://git@bitbucket.biscrum.com:7999/~benjamin.elfen_boehringer-ingelheim.com/portableapps.git
git push -u origin --all
git push origin --tags
```
