# Carsift API Docs
All requests should be made to the carsift end point - this should be requested from the team help@carsift.co

# Sessions
Sessions are managed via cookies. All requests to the API must include cookies (see [withCredentials](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials)).

# Connection Test
## Request
````
GET /ping
````
## Response:
````
HTTP/1.1 200 OK
Pong
````

# Get Questions
Note: the returned search_id is required when returning answers and retrieving results
## Request
````
GET /questions
    ?company_id={company_id}
````
## Response:
````json
{
    "data": [{
        "id": 13,
        "ref": "price",
        "title": "What is your budget?",
        "subtitle": null,
        "short_title": "Price",
        "type": "string",
        "direction": null,
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https://cdn.widget.carsift.co/aux_images/carsift-gif-001.gif",
        "rank": null,
        "options": []
    }, {
        "id": 2,
        "ref": "length",
        "title": "Vous recherchez un v\u00e9hicule de quel gabarit?",
        "subtitle": null,
        "short_title": "Taille",
        "type": "radio",
        "direction": "horizontal",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-002.gif",
        "rank": null,
        "options": [{
            "id": 8,
            "ref": "small",
            "title": "Petit",
            "subtitle": null,
            "short_title": "Petit",
            "image": null
        }, {
            "id": 9,
            "ref": "large",
            "title": "Grand",
            "subtitle": null,
            "short_title": "Grand",
            "image": null
        }]
    }, {
        "id": 6,
        "ref": "req-equipment",
        "title": "Et vos \u00e9quipements?",
        "subtitle": "Ou indiquez un autre budget",
        "short_title": "Incontournables",
        "type": "options-multi",
        "direction": null,
        "required": false,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-006.gif",
        "rank": null,
        "options": [{
            "id": 18,
            "ref": "leather-seats",
            "title": "Sellerie cuir",
            "subtitle": null,
            "short_title": "Sellerie cuir",
            "image": null
        }, {
            "id": 19,
            "ref": "climate-control",
            "title": "Climatisation",
            "subtitle": null,
            "short_title": "Climatisation",
            "image": null
        }, {
            "id": 20,
            "ref": "gps",
            "title": "GPS",
            "subtitle": null,
            "short_title": "GPS",
            "image": null
        }, {
            "id": 22,
            "ref": "bluetooth",
            "title": "Bluetooth",
            "subtitle": null,
            "short_title": "Bluetooth",
            "image": null
        }, {
            "id": 23,
            "ref": "parking-sensors",
            "title": "Radars de recul",
            "subtitle": null,
            "short_title": "Radars de recul",
            "image": null
        }]
    }],
    "search_id": 87389
}
````

# Search
This endpoint is used to:
- retrieve the number of results available 
- retrieve the top results (optional)
- provide answers (optional)
Company ID and Seach ID must be provided.

Previous answers can be overwritten by simply providing a new answer for that question ID.

New answers and the retrieval of answers are optional, so the request can be used to just retrieve a result count for the current search. This can be done before providing any answers for the initial vehicle count.

## Fields
| Fields        | Info          |
| ------------- | ------------- |
| answers       | an array of answer objects (see below)            |
| search_id     | returned from Get Questions                       |
| results       | number of results you want to have returned (0-20)  |

## Answer Objects
| Fields        | Info          |
| ------------- | ------------- |
| id            | The ID of the question being answered.                                         |
| answers       | An array of answers, generally an option ID from Get Questions or a string. An array is required for both single answers and multi option answers |

## Example Request
````
POST /results
    ?company_id={company_id}
````
JSON Body:
````json
{
    "answers":[
        {
            "id":13,
            "answers":[40000]
        },
        {
            "id":2,
            "answers":[8]
        },
        {
            "id":6,
            "answers":[18,20,22]
        }
    ],
    "search_id":123456,
    "results":1
}
````
## Example Response:
````json
{
    "data": [
        {
            "id": 3039,
            "unique_id": "DFB_28244",
            "url": "http://www.autobonplan.com/volkswagen-tiguan-ii-2-0-tdi-150ch-confortline-refdfb_28244.html?utm_medium=carsift",
            "manufacturer": {
                "id": 6,
                "ref": "VOLKSWAGEN",
                "name": "VOLKSWAGEN",
                "title": "Volkswagen"
            },
            "range_name": "TIGUAN II",
            "model_name": "TIGUAN II 2.0 TDI 150CH CONFORTLINE",
            "der_name": "2.0 TDI 150CH CONFORTLINE",
            "manufactured_year": 2017,
            "manufactured_at": "2017-07-01",
            "spec": {
                "fuel_economy": {
                    "urban": "5.7 L/100Km",
                    "extra": "4.2 L/100Km",
                    "combined": "4.7 L/100Km"
                },
                "fuel_type": "Diesel",
                "fuel_capacity": "--",
                "transmission": "BVM6",
                "body_style": "BREAK",
                "volume": "--",
                "power1": "8 cv",
                "power2": "150 ch",
                "discount": "-15%",
                "guarantee": "--",
                "wheelbase": "--",
                "doors": 5,
                "seats": 5,
                "dimensions": {
                    "width": "1839mm",
                    "height": "1632mm",
                    "length": "4486mm"
                },
                "co2": "123 g/km",
                "colour": "Blanc Pur"
            },
            "features": [
                "Phares à LED avec feux de jour à LED",
                "Système Navigation Discover Media",
                "JA 18\" Kingston 235/55R18",
                "Blanc Pur",
                "Prise auxiliaire de connexion audio",
                "Prise 12V",
                "Préparation Isofix",
                "Pré-équipement Kit Bluetooth",
                "Porte-gobelets arrière",
                "Pommeau de levier vitesse en cuir",
                "Poignées ton carrosserie",
            ],
            "mileage": {
                "miles": "6m",
                "km": "10km"
            },
            "images": [
                {
                    "id": 19344,
                    "url": "https://tpimg.carsift.co/1/media/catalog/product/placeholder/default/vehicule_en_arrivage_2.png",
                    "type": ""
                }
            ],
            "price": {
                "outright": {
                    "total": 32298.2
                },
                "monthly": {
                    "total": 367.94,
                    "monthly": 367.94,
                    "deposit": 0,
                    "term": 0
                }
            },
            "legal": {
                "rows": {
                    "Pour un véhicule de": "32 298.00 €",
                    "Apport": "9 689.40 €",
                    "Montant emprunté": "22 608.60 €",
                    "Durée": "72 mois",
                    "Mensualité": "367.94 €",
                    "Coût total du crédit": "3 883.08 €",
                    "Dont frais de dossier": "452.17 €",
                    "Dont intérêts": "3 430.91 €",
                    "Taux débiteur fixe": "4.68 %",
                    "TAEG fixe": "5.49 %",
                    "Montant total dû": "26 491.68 €"
                },
                "legal": "Offre pour un achat et un crédit accessoire à une vente à partir de 1 500€ empruntés remboursable sur une durée de 12 à 84 mois, pour l'achat d'un véhicule neuf. <strong>Le Taux Annuel Effectif Global fixe est compris entre 4,54% à 6,39%.</strong> Sous réserve d'acceptation du dossier par BNP Paribas Personal Finance, établissement de crédit : 1 bd Haussmann 75 009 Paris, SA au capital de 529 548 810€, 542 097 902 RCS Paris, N°ORIAS : 07 023 128 (www.orias.fr). Cetelem est une marque de BNP Paribas Personal Finance. Vous disposez d'un droit de rétractation. Conditions en vigueur au 26/07/2017. ",
                "example": "<strong>Exemple (hors assurances facultatives)</strong> : Pour un achat de 15 000€ avec un apport de 4 500€ et un crédit accessoire à une vente de 10 500 € sur 49 mois au <strong>Taux Annuel Effectif Global Fixe de 5,49%</strong> (taux débiteur fixe : 4,37%), vous remboursez 49<strong> mensualités de 239,05€</strong>, intérêts : 1 003,45€, frais de dossier : 210,00€. <strong>Montant total dû : 11 713,45€</strong>. Coût mensuel de l’assurance facultative* : 14,18€. Coût total de cette assurance facultative : 694,58€. Taux Annuel Effectif de cette Assurance : 3,05%. *Le coût mensuel de l’assurance facultative Décès, Perte Totale et Irréversible d’Autonomie, Incapacité Temporaire Totale de Travail (souscrite auprès de Cardif Assurance Vie et Cardif Assurances Risques Divers) s’ajoute au montant de la mensualité ci-dessus."
            },
            "new": true,
            "score": {
                "total": 100
            }
        }
    ],
    "search_id": 23,
    "result_set_id": 177,
    "result_count": 27
}
````
