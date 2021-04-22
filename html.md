# HTML
## Introductie
HTML is een specificatie van het W3C [[html5]] om gegevens gestructureerd aan te bieden, voor ontsluiting op het web. HTML is vooral bekend als de standaard voor webpagina's. Zoekmachines kunnen HTML goed indexeren.

Geodata in HTML kan op verschillende manieren gepubliceerd worden. Een HTML pagina van een geo-object zou de niet-geo eigenschappen kunnen tonen. Maar een HTML pagina kan ook de geometrie zelf bevatten en visualiseren.

HTML kent geen aparte elementen voor geometrie, maar de geometrie kan wel gestructureerd opgenomen  worden in een HTML pagina, door middel van een zogenaamde annotatie. Annotaties zijn vaak volgens het begrippenkader van Schema.org opgesteld. Slechts enkele eenvoudige geometrietypen worden gebruikt: punt, bounding box, cirkel, lijn, en polygoon. Het is ook mogelijk om een hoogtegetal op te nemen. De geometrie wordt meestal beschouwd als een vorm van metadata van de HTML pagina. Die wordt dan opgenomen met microdata, RDFa of stukjes JSON-LD en voor de gebruiker verborgen door een webbrowser, maar wel geïndexeerd door zoekmachines

Met behulp van (gestandaardiseerde) webtechnologie als CSS, JavaScript, SVG / web canvas, kan geometrie gevisualiseerd worden via HTML pagina's. In steeds meer API's is er ook een HTML representatie van een geo-object. Zo is in de core van OGC API Features [[OAPIF]] [HTML een aanbevolen formaat](http://docs.opengeospatial.org/is/17-069r3/17-069r3.html#_requirements_class_html) voor representatie van geodata.

In HTML kunnen eenvoudig relaties gelegd worden met andere bronnen (webpagina's van gerelateerde geo-objecten bijvoorbeeld of verwijzingen naar definities) en andere begrippenkaders.

Een nadeel van HTML is dat een dataset (meestal) niet in één webpagina wordt gepubliceerd, maar elk object een eigen pagina krijgt. Dit betekent dat verwerking van meer dan één object in een ander systeem (bijvoorbeeld in een GIS of inlezen in een database), lastig is.

<!-- &#9744; (☐) for [ ] and &#9745; (☑) of:
<span id="vinkje">&#10003;</span>  <span id="kruisje">&#10005;</span>  <span id="tilde">&#65374;</span> 
 -->

## Overwegingen

| Vraag                                                                              | Antwoord | Toelichting |
|------------------------------------------------------------------------------------|----------|-------------|
| Is het format geospecifiek?                                                        | <span id="kruisje">&#10005;</span> |             |
| Is het format gebaseerd op algemene ict standaarden?                               | <span id="vinkje">&#10003;</span>  |  Ja, HTML is de standaard voor Web pagina's.           |
| Wordt het format ondersteund in GIS software?                                      | <span id="kruisje">&#10005;</span> |            |
| Ondersteunt het format het uitdrukken van schema's, en validatie tegen dat schema? | <span id="kruisje">&#10005;</span> |             |
| Ondersteunt het format meerdere coordinaatsystemen?                                | <span id="kruisje">&#10005;</span> | Ondersteuning voor andere CRSen dan WGS-84 is niet gangbaar  |
| Ondersteunt het format 3D?                                                         | <span id="kruisje">&#10005;</span> |             |
| Ondersteunt het format alle simple features geometrieen?                           | <span id="tilde">&#65374;</span>   | Ondersteunde geometrietypen zijn zeer beperkt |
| Ondersteunt het format andere ISO 19107 geometrie types?                           | <span id="kruisje">&#10005;</span> |             |
| Is het format geschikt voor grote volumes?                                         | <span id="kruisje">&#10005;</span> |             |
| Is het format geschikt om semantiek aan te koppelen / in uit te drukken?           | <span id="vinkje">&#10003;</span>  | Het is eenvoudig om gestructureerde data te combineren met tekst en en men kan linken aan begrippenkaders |

<!-- ## Voordelen
- directe visualiatie / presentatie aan (eind)gebruikers van (object)informatie
- gestructureerde data in combinatie met tekst
- indexeerbaar door zoekmachines
- linken aan begrippenkaders -->

<!-- ## Beperkingen
- geometrietypen zeer beperkt
- ondersteuning voor andere CRSen dan WGS84 is niet gangbaar
- een volledige dataset downloaden, bijvoorbeeld om te combineren met een andere dataset, is lastiger
- verwerking van de geometrie in een ander systeem (zoals een GIS desktop systeem) is lastig -->

## Voorbeelden
TODO
