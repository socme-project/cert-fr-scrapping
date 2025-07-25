# CERT FR Scraping

This Go package provides functionalities to scrape security alerts, CTI (Cyber
Threat Intelligence), and advisories from the official CERT-FR website from
l'ANSSI (Agence Nationale de la Sécurité des Systèmes d'Information).

---

## Features

- **Scrape Alerts**: Extracts security alerts from the CERT-FR website.
- **Scrape CTI**: Gathers Cyber Threat Intelligence information.
- **Scrape Advisories**: Collects security advisories.
- **Structured Output**: Organizes scraped data into a clear `Item` struct.
- **Pretty Printing**: Includes a utility function to display the scraped data
  in a readable format.

---

## Usage

Here's how you can use the `certfr_scraping` package in your Go application:

```go
package main

import (
	"fmt"
	"certfr_scraping" // Assuming your package is in a directory named certfr_scraping
)

func main() {
	fmt.Println("Collecting Alerts...")
	alerts := certfr_scraping.CollectAlert()
	certfr_scraping.PrettyPrint(alerts)

	fmt.Println("Collecting CTI...")
	ctis := certfr_scraping.CollectCti()
	certfr_scraping.PrettyPrint(ctis)

	fmt.Println("Collecting Advisories...")
	avis := certfr_scraping.CollectAvis()
	certfr_scraping.PrettyPrint(avis)
}
```

---

## Functions

### `CollectAlert() []Item`

This function scrapes the "Alertes" section of the CERT-FR website and returns a
slice of `Item` structs, each representing a security alert.

### `CollectCti() []Item`

This function scrapes the "CTI" (Cyber Threat Intelligence) section of the
CERT-FR website and returns a slice of `Item` structs.

### `CollectAvis() []Item`

This function scrapes the "Avis" (Advisories) section of the CERT-FR website and
returns a slice of `Item` structs, each representing a security advisory.

### `PrettyPrint(items []Item)`

This utility function takes a slice of `Item` structs and prints their details
to the console in a formatted, human-readable way.

---

## Dependencies

This package relies on the `colly` library for web scraping.

- [**colly**](https://github.com/gocolly/colly): Fast and elegant 
  framework for Go.

---

## Contributing

Feel free to open issues or submit pull requests if you have suggestions for
improvements or find any bugs.
