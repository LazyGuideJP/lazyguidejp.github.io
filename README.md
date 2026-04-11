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

Then:

pip install -r requirements.txt

to create new: mkdocs new .

to run: mkdocs serve --livereload


To Push:

git add .

git commit -m $'Put your Info here'

git push origin main

Install in linux:
sudo pacman -S python python-pip

python3 -m venv ~/jptools-env
source ~/jptools-env/bin/activate.fish

pip install -r requirements.txt
mkdocs serve --livereload