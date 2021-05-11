## RDF

### Introductie

RDF wordt steeds meer gebruikt als uitwissel- en publicatiemechanisme voor geo-informatie op basis van Linked Data. RDF vormt de basis voor een set standaarden die bijdragen aan het gebruik en de publicatie van Linked Data - zoals de OWL Web Ontology Language en de SPARQL protocol and RDF query language. De afkorting RDF [[rdf11-concepts]] staat voor Resource Description Framework en is een standaard voor het representeren van informatie op het web als linked data, zodanig dat deze beschikbaar gemaakt kunnen worden in machineleesbare vorm op het web, niet als download maar als web pagina's, en daardoor ook beter bruikbaar zijn over sectorale grenzen heen. De data kunnen worden hergebruikt bij de bron door ze te koppelen via persistente URI’s. Er zijn meerdere technische RDF encodings zoals bijvoorbeeld RDF-XML [[rdf-syntax-grammar]] en [[turtle]]. 

Hoe geometrie in RDF moet worden uitgedrukt is beschreven in de OGC GeoSPARQL standaard. Zoals de naam al doet vermoeden specificeert deze standaard een extensie op de SPARQL query language, zodat gebruikers geodata in RDF kunnen bevragen. Het bevat dus ook een kleine vocabulaire voor geo-objecten en geometrie. Deze geometrie kan volgens GeoSPARQL op twee manieren worden geserialiseerd:
- Als WKT, waarbij de Simple Feature geometrietypen uit ISO 19125 gebruikt kunnen worden (daardoor beperkt: geen 3D, geen bogen etc);
- Als GML, waarbij de ISO 19107 geometrietypen gebruikt kunnen worden. 

[TODO voorbeelden opnemen]

<!-- <span id="vinkje">&#10003;</span>  <span id="kruisje">&#10005;</span>  <span id="tilde">&#65374;</span> 
 --> -->

## Overwegingen 

| Vraag                                                                              | Antwoord | Toelichting |
|------------------------------------------------------------------------------------|----------|-------------|
| Is het format geospecifiek?                                                        | <span id="kruisje">&#10005;</span>  | Het is een algemene Webstandaard. In combinatie met de GeoSPARQL vocabulaire is er wel ondersteuning voor geo-informatie.            |
| Is het format gebaseerd op algemene ict standaarden?                               | <span id="vinkje">&#10003;</span>  | Ja, het is gebaseerd op W3C Linked Data standaarden            |
| Wordt het format ondersteund in GIS software?                                      | <span id="kruisje">&#10005;</span> |             |
| Ondersteunt het format het uitdrukken van schema's, en validatie tegen dat schema? | <span id="vinkje">&#10003;</span>  | Ja, via [[shacl]] shape expressions            |
| Ondersteunt het format meerdere coordinaatsystemen?                                | <span id="vinkje">&#10003;</span>  |             |
| Ondersteunt het format 3D?                                                         | <span id="kruisje">&#10005;</span> | Je kunt op zich 3D geometrie opnemen in de data, maar GeoSPARQL ondersteunt geen 3D bij ruimtelijke vragen.         |
| Ondersteunt het format alle simple features geometrieen?                           | <span id="vinkje">&#10003;</span>  |             |
| Ondersteunt het format andere ISO 19107 geometrie types?                           | <span id="vinkje">&#10003;</span>  | Ja, als je de GeoSPARQL GML serialisatie gebruikt            |
| Is het format geschikt voor grote volumes?                                         | <span id="tilde">&#65374;</span>   | In triple stores is goede ondersteuning voor grote hoeveelheden geometrieën in de data, maar bij het uitwisselen is een RDF bestand geen heel geschikt format vanwege verbositeit            |
| Is het format geschikt om semantiek aan te koppelen / in uit te drukken?           | <span id="vinkje">&#10003;</span>  | Bij uitstek geschikt. Gebruik van RDF voor het publiceren van gestructureerde gegevens op het web maakt het mogelijk dat data over de grenzen van sectoren heen gekoppeld en geïntegreerd worden.             |

<!-- ### Voordelen

- data integratie: Gebruik van RDF voor het publiceren van gestructureerde gegevens op het web maakt het mogelijk dat data over de grenzen van sectoren heen gekoppeld en geïntegreerd worden.
- verschillende CRS mogelijk
- 3D mogelijk
- semantisch rijke data, integreren van vocabulaires

### Beperkingen
- GIS systemen ondersteunen (nog) geen RDF
 -->
### Afspraken
In Nederland zijn er geen normatieve regels over het gebruik van RDF voor het uitwisselen van geometrie. 

Wel zijn er de volgende handvaten:
- RDF staat op de lijst met [aanbevolen standaarden](https://forumstandaardisatie.nl/open-standaarden/aanbevolen).
- De Aanzet tot een Nationale  URI-strategie [[NLURIStrategie]] beschrijft het in Nederland gehanteerde URI patroon.
- Het Linked Data profiel op NEN 3610 [[nen3610-linkeddata]] beschrijft hoe een linked data model van een NEN 3610 conf
- Voor het uitdrukken van geometrie in RDF gebruiken we de OGC GeoSPARQL Linked Data vocabulaire [[geosparql]]. orm informatiemodel kan worden afgeleid.