# JP Lazy Guide

Lazy Guide for Japanese Immersion

https://lazyguidejp.github.io/jp-lazy-guide/

Made in material mkdocs

Any contribution to the site is welcome


### How to install?

This is in case I stopped caring about my guide, anyone else can continue it

1. Download Python and Git
2. Download/Pull the repository
3. cd to the directory

Then go to the LazyGuideJP repository folder then install dependencies:
```
pip install -r requirements.txt
```

to run: 
```
mkdocs serve --livereload
```

### To Push:

```
git add .
```
```
git commit -m $'Put your Info here'
```
```
git push origin main
```

### Install on linux(Based on CachyOS - Arch):

Install Python:
```
sudo pacman -S python python-pip
```

Run Python Environment:
```
python3 -m venv ~/venvs/jp-lazy-guide-env
source ~/venvs/jp-lazy-guide-env/bin/activate.fish
```

Go to the LazyGuideJP repository folder then install dependencies:
```
pip install -r requirements.txt
```

Run it with:
```
mkdocs serve --livereload
```

Or copy pasta for later on:
```
python3 -m venv ~/venvs/lazy-guide-env
source ~/venvs/lazy-guide-env/bin/activate.fish
mkdocs serve --livereload
```