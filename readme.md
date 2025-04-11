GITHUB_USERNAME=USERNAME
REPO_NAME=ExamenChetroi Nil
NUMAR_BILET=20

git clone https://github.com/$GITHUB_USERNAME/$REPO_NAME.git
cd $REPO_NAME

echo "# Proiect Examen" > README.md
echo "Număr bilet: $NUMAR_BILET" >> README.md

echo "*.exe" > .gitignore

git checkout -b development

echo "<!DOCTYPE html><html><head><title>Index</title></head><body><h1>Index Page</h1></body></html>" > index.html
echo "<!DOCTYPE html><html><head><title>About</title></head><body><h1>About Page</h1></body></html>" > about.html

git add .
git commit -m "Adăugat README.md, .gitignore, index.html și about.html"
git push origin development

git checkout main
git pull origin main
git merge development
git push origin main
