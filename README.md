# Scraping CERT FR

Ce package Go offre des fonctionnalités pour récupérer les
alertes de sécurité, les CTI (Cyber Threat Intelligence), 
et les avis du site officiel du CERT-FR de l'ANSSI
(Agence Nationale de la Sécurité des Systèmes d'Information).

---

## Fonctionnalités

- **Récupération des alertes** : Extrait les alertes de sécurité
du site web du CERT-FR.
- **Récupération des CTI** : Rassemble les informations de Cyber
Threat Intelligence.
- **Récupération des avis** : Collecte les avis de sécurité.
- **Sortie structurée** : Organise les données récupérées dans
une structure `Item` claire.
- **Affichage formaté** : Inclut une fonction utilitaire pour
afficher les données récupérées dans un format lisible.

---

## Utilisation

Voici comment vous pouvez utiliser le package `certfr_scraping` dans
votre application Go :

```go
package main

import (
	"fmt"
	"certfr_scraping" // Supposons que votre package se trouve dans un répertoire nommé certfr_scraping
)

func main() {
	fmt.Println("Collecte des alertes...")
	alerts := certfr_scraping.CollectAlert()
	certfr_scraping.PrettyPrint(alerts)

	fmt.Println("Collecte des CTI...")
	ctis := certfr_scraping.CollectCti()
	certfr_scraping.PrettyPrint(ctis)

	fmt.Println("Collecte des avis...")
	avis := certfr_scraping.CollectAvis()
	certfr_scraping.PrettyPrint(avis)
}
```

---

## Fonctions

### `CollectAlert() []Item`

Cette fonction récupère la section "Alertes" du site web du CERT-FR et renvoie
un slice de structures `Item`, chacune représentant une alerte de sécurité.

### `CollectCti() []Item`

Cette fonction récupère la section "CTI" (Cyber Threat Intelligence) du site web
du CERT-FR et renvoie un slice de structures `Item`.

### `CollectAvis() []Item`

Cette fonction récupère la section "Avis" du site web du CERT-FR et renvoie un slice
de structures `Item`, chacune représentant un avis de sécurité.

### `PrettyPrint(items []Item)`

Cette fonction utilitaire prend un slice de structures `Item` et affiche leurs détails
dans la console de manière formatée et lisible.

---

### Dépendances

Ce package s'appuie sur la bibliothèque `colly` pour le scraping web.

- [**colly**](https://github.com/gocolly/colly) : Cadre de scraping
rapide et élégant pour Go.

## Contribution

N'hésitez pas à ouvrir des issues ou à soumettre des PR si vous avez 
des suggestions d'améliorations ou si vous trouvez des bugs.
