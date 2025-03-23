# SAE Réseau

## Etapes à suivre pour compiler et convertir 

1. Ouvrir un terminal et effectuer le commandes suivantes en étant dans le dossier du fichier en .md .

2. Conversion en html

`pandoc rapport.md --template=../templates/templateRapport.html -o rapport.html --toc --toc-depth=2`

3. Conversion en pdf

`pandoc rapport.md -t latex -o rapport.html --toc --toc-depth=2`
