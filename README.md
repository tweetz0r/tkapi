# tkapi
[![PyPI version](https://badge.fury.io/py/tkapi.svg)](https://badge.fury.io/py/tkapi)  
Python ORM and bindings for the [Tweede Kamer](https://tweedekamer.nl) [Open Data Portaal](https://opendata.tweedekamer.nl) OData API.

Requires Python 3.5+

You are welcome to open an issue if you have any problems, questions or suggestions.

## Installation
```
pip install tkapi
```

## Authentication
You need to whitelist your IP by registering at https://opendata.tweedekamer.nl.

## Data model
See [Open Kamer Data Model documentation](https://opendata.tweedekamer.nl/documentatie/informatiemodel-20) for the data model that is mapped to Python classes.

## Usage
A simple first example,
```python
import tkapi

api = tkapi.TKApi()
personen = api.get_personen(max_items=100)
for persoon in personen:
    print(persoon.achternaam)
```

For more examples see the `examples` directory and the tests.

## Entities

See Tweede Kamer [documentation](https://opendata.tweedekamer.nl/documentatie/informatiemodel-20) for details.

| Algemeen                   | Commissie                  | Persoon                      |
|----------------------------|----------------------------|------------------------------|
| **Activiteit**             | **Commissie**              | **Persoon**                  |
| **Zaak**                   | **CommissieZetel**         | **PersoonGeschenk**          |
| **Kamerstukdossier**       | **CommissieZetelVastPersoon**   | **PersoonLoopbaan**          |
| **Fractie**                | **CommissieZetelVervangerPersoon** | **PersoonNevenfunctie**      |
| **FractieZetel**           | **CommissieZetelVastVacature** | **PersoonNevenfunctieInkomsten** |
| **Stemming**               | **CommissieZetelVervangerVacature** | **PersoonOnderwijs**         |
| **Vergadering**            | **CommissieContactinformatie** | **PersoonReis**              |
| **Document**               |                            | **PersoonFunctie**           |
| **DocumentActor**          |                            | **PersoonContactinformatie** |
| **DocumentVersie**         |                            |                            |
| **Agendapunt**             |                            |                              |
| **Besluit**                |                            |                              |
| **Verslag**                |                            |                              |
| **FractieZetelPersoon**    |                            |                              |
| **ZaakActor**              |                            |                              |
| **Reservering**            |                            |                              |
| **Zaal**                   |                            |                              |
| **ActiviteitActor**        |                            |                              |
| **FractieZetelVacature**   |                            |                              |
| **FractieAanvullendGegeven** |                            |                              |

## Development

### Tests

Run all tests,
```bash
python -m unittest discover
```

#### Coverage report

Run all tests,
```bash
coverage run -m unittest discover
```

Create coverage report,
```bash
coverage html
```
Then visit htmlcov/index.html in your browser.
