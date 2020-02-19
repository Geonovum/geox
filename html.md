# HTML
## Introductie
HTML is een specificatie van het W3C [[html5]] om gegevens gestructureerd aan te bieden, voor ontsluiting op het web. HTML is vooral bekend als de standaard voor webpagina's. Zoekmachines kunnen HTML goed indexeren.

Geodata in HTML kan op verschillende manieren gepubliceerd worden. Een HTML pagina van een geo-object zou vooral de niet-geo eigenschappen kunnen tonen bijvoorbeeld. Maar een HTML pagina kan ook (al dan niet verborgen) de geometrie zelf bevatten.

HTML kent geen aparte elementen voor geometrie. Als de geometrie gestructureerd opgegeven moet worden, zijn zogenaamde annotaties een mogelijkheid. Annotaties zijn vaak volgens het begrippenkader van Schema.org opgesteld. Vooral de eenvoudigere geometrietypen worden gebruikt, zoals de coordinaten in latitude en longitude (in WGS 84) of de bounding box. De geometrie wordt meestal beschouwd als een vorm van metadata van de HTML pagina. Die wordt dan opgenomen met microdata, RDFa of stukjes JSON-LD en meestal voor de gebruiker verborgen door een webbrowser.

Met behulp van (gestandaardiseerde) webtechnologie als CSS, JavaScript, SVG / web canvas, kan geometrie gevisualiseerd worden via HTML pagina's. In steeds meer API's is er ook een HTML representatie van een geo-object. Zo is in de core van OGC API Features [[OAPIF]] [HTML een aanbevolen formaat](http://docs.opengeospatial.org/is/17-069r3/17-069r3.html#_requirements_class_html) voor representatie van geodata.

In HTML kunnen eenvoudig relaties gelegd worden met andere bronnen (webpagina's van gerelateerde geo-objecten bijvoorbeeld of verwijzingen naar definities) en andere begrippenkaders.

Een nadeel van HTML is dat een dataset (meestal) niet in één webpagina wordt gepubliceerd, maar elk object een eigen pagina krijgt. Dit betekent dat verwerking van meer dan één object in een ander systeem (bijvoorbeeld in een GIS of inlezen in een database), lastiger is.

## Voordelen
- directe visualiatie / presentatie aan (eind)gebruikers van (object)informatie
- gestructureerde data in combinatie met tekst
- indexeerbaar door zoekmachines
- linken aan begrippenkaders

## Beperkingen
- geometrietypen zeer beperkt
- ondersteuning voor andere CRSen dan WGS84 is niet gangbaar
- een volledige dataset downloaden, bijvoorbeeld om te combineren met een andere dataset, is lastiger
- verwerking van de geometrie in een ander systeem (zoals een GIS desktop systeem) is lastig

## Voorbeelden
TODO
