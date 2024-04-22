# Exercice de Scrapping avec Python et BeautifulSoup 🕸️🐍

Bienvenue dans cet exercice simple de scraping avec Python et BeautifulSoup ! Dans cet exercice, nous allons scraper la page d'accueil du site "https://webscraper.io/test-sites" pour récupérer les titres et les prix des produits.

## Consignes 📋

1. **Analyse de la page** : Avant de commencer à scraper, examinez la structure de la page d'accueil du site pour identifier les informations que vous souhaitez récupérer.

2. **Installation des dépendances** : Assurez-vous d'avoir installé BeautifulSoup, ainsi que toute autre bibliothèque nécessaire. Vous pouvez installer BeautifulSoup en exécutant `pip install beautifulsoup4`.

3. **Écriture du script de scraping** : Utilisez Python pour écrire un script qui récupère les titres et les prix des produits sur la page d'accueil du site.

4. **Exécution du script** : Enregistrez votre script dans un fichier Python (par exemple `scraper.py`) et exécutez-le. Vous devriez voir les titres et les prix des produits affichés dans votre console.

5. **Personnalisation du scraping** : Vous pouvez personnaliser votre script pour scraper d'autres informations à partir de la page, comme les descriptions des produits, les images, etc. Explorez le HTML de la page pour identifier les balises et les classes nécessaires.

## Exemple de Script Python 🖥️

Voici un exemple de script Python pour scraper les titres et les prix des produits sur la page d'accueil :

```python
import requests
from bs4 import BeautifulSoup

# URL de la page d'accueil du site à scraper
url = "https://webscraper.io/test-sites"

# Faire une requête HTTP GET pour récupérer le contenu de la page
response = requests.get(url)

# Utiliser BeautifulSoup pour analyser le contenu HTML de la page
soup = BeautifulSoup(response.content, "html.parser")

# Trouver tous les éléments de la classe "thumbnail"
products = soup.find_all(class_="thumbnail")

# Parcourir chaque produit et extraire son titre et son prix
for product in products:
    # Extraire le titre du produit
    title = product.find(class_="title").text.strip()
    # Extraire le prix du produit
    price = product.find(class_="price").text.strip()
    # Afficher le titre et le prix du produit
    print(f"Titre : {title}, Prix : {price}")
```
Cet exercice vous permettra de vous familiariser avec le scraping de données à l'aide de Python et de BeautifulSoup. Amusez-vous bien ! 😊
