# Carsift API Docs
All requests should be made to https://api.carsift.co.

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
        "id": 1,
        "ref": "budget",
        "title": "Chaque mois, quel montant voulez-vous consacrer \u00e0 votre auto?",
        "subtitle": null,
        "short_title": "Budget mensuel",
        "type": "options",
        "direction": null,
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-001.gif",
        "rank": null,
        "options": [{
            "id": 1,
            "ref": "200",
            "title": "200\u20ac",
            "subtitle": null,
            "short_title": "200\u20ac",
            "image": null
        }, {
            "id": 2,
            "ref": "300",
            "title": "300\u20ac",
            "subtitle": null,
            "short_title": "300\u20ac",
            "image": null
        }, {
            "id": 3,
            "ref": "400",
            "title": "400\u20ac",
            "subtitle": null,
            "short_title": "400\u20ac",
            "image": null
        }, {
            "id": 4,
            "ref": "500",
            "title": "500\u20ac",
            "subtitle": null,
            "short_title": "500\u20ac",
            "image": null
        }, {
            "id": 5,
            "ref": "600",
            "title": "600\u20ac",
            "subtitle": null,
            "short_title": "600\u20ac",
            "image": null
        }, {
            "id": 6,
            "ref": "700",
            "title": "700\u20ac",
            "subtitle": null,
            "short_title": "700\u20ac",
            "image": null
        }]
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
        "id": 3,
        "ref": "seat-height",
        "title": "Quelle est votre position de conduite pr\u00e9f\u00e9r\u00e9e?",
        "subtitle": null,
        "short_title": "Position de conduite",
        "type": "radio",
        "direction": "horizontal",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-003.gif",
        "rank": null,
        "options": [{
            "id": 10,
            "ref": "regular",
            "title": "Normale",
            "subtitle": null,
            "short_title": "Normale",
            "image": null
        }, {
            "id": 11,
            "ref": "high",
            "title": "Haute",
            "subtitle": null,
            "short_title": "Haute",
            "image": null
        }]
    }, {
        "id": 4,
        "ref": "seats",
        "title": "Vous voyagez nombreux? Combien de places avez-vous besoin?",
        "subtitle": null,
        "short_title": "Si\u00e8ges",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-004.gif",
        "rank": null,
        "options": [{
            "id": 13,
            "ref": "4-5",
            "title": "4-5",
            "subtitle": null,
            "short_title": "4-5",
            "image": null
        }, {
            "id": 14,
            "ref": "6-9",
            "title": "7",
            "subtitle": null,
            "short_title": "7",
            "image": null
        }]
    }, {
        "id": 5,
        "ref": "gearbox",
        "title": "Votre pr\u00e9f\u00e9rence pour la boite de vitesse?",
        "subtitle": null,
        "short_title": "Transmission",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-005.gif",
        "rank": null,
        "options": [{
            "id": 15,
            "ref": "manual",
            "title": "Manuelle",
            "subtitle": null,
            "short_title": "Manuelle",
            "image": null
        }, {
            "id": 16,
            "ref": "automatic",
            "title": "Automatique",
            "subtitle": null,
            "short_title": "Automatique",
            "image": null
        }, {
            "id": 17,
            "ref": "either",
            "title": "Sans avis",
            "subtitle": null,
            "short_title": "Sans avis",
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
    }, {
        "id": 7,
        "ref": "premium",
        "title": "Recherchez-vous un v\u00e9hicule Premium?",
        "subtitle": null,
        "short_title": "Premium",
        "type": "radio",
        "direction": "horizontal",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-001.gif",
        "rank": null,
        "options": [{
            "id": 24,
            "ref": "premium",
            "title": "Oui",
            "subtitle": null,
            "short_title": "Oui",
            "image": null
        }, {
            "id": 25,
            "ref": "cheap",
            "title": "Pas forc\u00e9ment",
            "subtitle": null,
            "short_title": "Pas forc\u00e9ment",
            "image": null
        }]
    }, {
        "id": 8,
        "ref": "tech",
        "title": "Appr\u00e9ciez-vous les derni\u00e8res technologies?",
        "subtitle": null,
        "short_title": "Technologie",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-002.gif",
        "rank": null,
        "options": [{
            "id": 26,
            "ref": "tech",
            "title": "Dernier cri",
            "subtitle": null,
            "short_title": "Technology",
            "image": null
        }, {
            "id": 27,
            "ref": "simple",
            "title": "Simple",
            "subtitle": null,
            "short_title": "Simple",
            "image": null
        }]
    }, {
        "id": 9,
        "ref": "performance",
        "title": "Vous vous y connaissez en motorisation? Votre prochain v\u00e9hicule doit \u00eatre plut\u00f4t?",
        "subtitle": null,
        "short_title": "Performance",
        "type": "radio",
        "direction": "horizontal",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-003.gif",
        "rank": null,
        "options": [{
            "id": 28,
            "ref": "fast",
            "title": "Puissant",
            "subtitle": null,
            "short_title": "Puissant",
            "image": null
        }, {
            "id": 29,
            "ref": "economical",
            "title": "Economique",
            "subtitle": null,
            "short_title": "Economique",
            "image": null
        }]
    }, {
        "id": 10,
        "ref": "miles",
        "title": "Grand ou petit rouleur? Quel kilom\u00e9trage parcourez-vous chaque ann\u00e9e?",
        "subtitle": null,
        "short_title": "Kilom\u00e9trage",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-004.gif",
        "rank": null,
        "options": [{
            "id": 30,
            "ref": "3107",
            "title": "< \u00e0 5 000km",
            "subtitle": null,
            "short_title": "< \u00e0 5 000km",
            "image": null
        }, {
            "id": 31,
            "ref": "6214",
            "title": "10 000 - 12 000km",
            "subtitle": null,
            "short_title": "10 000 - 12 000km",
            "image": null
        }, {
            "id": 32,
            "ref": "9321",
            "title": "15 000km",
            "subtitle": null,
            "short_title": "15 000km",
            "image": null
        }, {
            "id": 33,
            "ref": "12427",
            "title": "> \u00e0 20 000km",
            "subtitle": null,
            "short_title": "> \u00e0 20 000km",
            "image": null
        }]
    }, {
        "id": 11,
        "ref": "vehicle-age",
        "title": "Vous recherchez un v\u00e9hicule...",
        "subtitle": null,
        "short_title": "L\u2019\u00e2ge du v\u00e9hicule",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-005.gif",
        "rank": null,
        "options": [{
            "id": 34,
            "ref": "0-12",
            "title": "Quasi neuf ou moins d\u20191 an",
            "subtitle": null,
            "short_title": "Quasi neuf ou moins d\u20191 an",
            "image": null
        }, {
            "id": 35,
            "ref": "0-36",
            "title": "Moins de 3 ans",
            "subtitle": null,
            "short_title": "Moins de 3 ans",
            "image": null
        }, {
            "id": 36,
            "ref": "0-60",
            "title": "Moins de 5 ans",
            "subtitle": null,
            "short_title": "Moins de 5 ans",
            "image": null
        }, {
            "id": 37,
            "ref": "0-999",
            "title": "5 ans et plus",
            "subtitle": null,
            "short_title": "5 ans et plus",
            "image": null
        }]
    }, {
        "id": 12,
        "ref": "journey-position",
        "title": "Pr\u00eat ou curieux? Dans quel d\u00e9lai allez-vous r\u00e9aliser cet achat automobile?",
        "subtitle": null,
        "short_title": "Decision",
        "type": "radio",
        "direction": "vertical",
        "required": true,
        "default_answer": null,
        "placeholder": null,
        "aux_image": "https:\/\/cdn.widget.carsift.co\/aux_images\/carsift-gif-006.gif",
        "rank": null,
        "options": [{
            "id": 38,
            "ref": "now",
            "title": "Maintenant",
            "subtitle": null,
            "short_title": "Maintenant",
            "image": null
        }, {
            "id": 39,
            "ref": "<3m",
            "title": "Moins de 3 mois",
            "subtitle": null,
            "short_title": "Moins de 3 mois",
            "image": null
        }, {
            "id": 40,
            "ref": "this-year",
            "title": "Cette ann\u00e9e",
            "subtitle": null,
            "short_title": "Cette ann\u00e9e",
            "image": null
        }, {
            "id": 41,
            "ref": "just-looking",
            "title": "Simple curiosit\u00e9 \u00e0 ce stade",
            "subtitle": null,
            "short_title": "Simple curiosit\u00e9 \u00e0 ce stade",
            "image": null
        }]
    }],
    "search_id": 87389
}
````