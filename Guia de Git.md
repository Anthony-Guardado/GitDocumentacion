# Como crear mi repositorio 
## 1. Inicializa Git en tu carpeta local
git init

## 2. Agrega todos tus archivos al "stage"
git add .

## 3. Haz tu primer commit
git commit -m "First commit"

## 4. Asegúrate de estar en la rama principal (main)
git branch -M main

## 5. Vincula tu carpeta local con el repositorio de GitHub
(Cambia la URL por la de tu repositorio)
git remote add origin https://github.com/tu-usuario/tu-repositorio.git

# 6. Sube tu código a GitHub
git push -u origin main