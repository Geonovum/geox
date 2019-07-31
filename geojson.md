# GeoJSON

<p class='note'>Voor nu staan hier alleen even wat bevindingen over GeoJSON uit de werkgroep lichtere formaten. Dit moet een uitgebreidere tekst worden, maar die moet nog geschreven worden. </p>

JSON [[RFC8259]] is een codering voor gegevens in een op JavaScript gebaseerd formaat. Vaak wordt JSON als alternatief voor XML gebruikt om gestructureerde gegevens te coderen en uit te wisselen.

GeoJSON [[RFC7946]] gebruikt JSON om geografische gegevens te coderen. Het is bedoeld om simpele geografische objecten te representeren inclusief hun ruimtelijke en niet-ruimtelijke eigenschappen. GeoJSON ondersteunt punten, lijnen, vlakken, en de multi-varianten van deze drie. Volumes en bogen worden niet ondersteund. Een GeoJSON kan een geo-object bevatten: een Feature; of een lijst van geo-objecten: een Feature Collection met daarin meerdere Features. 

GeoJSON is ontstaan als informele community standaard, opgesteld in een internet werkgroep. Ondersteuning voor GeoJSON is er in sommige geografische databases en GIS softwarepakketten, en is breed aanwezig in web mapping libraries en APIs van bijvoorbeeld Google, Yahoo en Twitter.

GeoJSON is een prima formaat voor de meeste toepassingen - zeker in web toepassingen - bijvoorbeeld om iconen of polygonen bovenop een kaart op het web weer te geven. De browser toont dan een basiskaart, haalt de daar bovenop weer te geven geodata op, en combineert deze met de basiskaart met behulp van een JavaScript library.

Een voordeel van dit formaat is dat het te lezen is in een tekst editor, in tegenstelling tot GeoPackage bestanden die binair zijn. Dit maakt GeoJSON wat eenvoudiger in gebruik. JSON is heel geschikt voor web toepassingen, bijvoorbeeld voor publicatie van data in een API of voor visualisatie op het web. Het maakt geodata ook bruikbaar voor niet-geo experts. Er zijn veel tools beschikbaar om ermee te werken. Het is mogelijk om GeoJSON met linked data te combineren door gebruik te maken van [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/). 

GeoJSON schrijft WGS 84 voor; dit maakt het geschikt voor visualisatie op het web.

WFS 3 kan in combinatie met GML worden gebruikt, dit is alleen nog interessant als er behoefte is aan nauwkeurigere geometrieën of aan arcs (die in GeoJSON niet worden ondersteund). Andere use cases voor GML/XML zien de PDOK ontwikkelaars niet meer.

In veel gevallen is de nauwkeurigheid van GeoJSON voldoende; op het Geoforum wordt er zelden gevraagd om data met hoge nauwkeurigheid. Belangrijker is vindbaarheid van data. De aanbeveling is om GeoJSON alleen in combinatie met WGS 84 te gebruiken. De [Spatial Data on the Web Best Practice](https://www.w3.org/TR/sdw-bp/#bp-crs-choice) raadt aan om geodata op het web in ieder geval in WGS 84 te publiceren.  

## voordelen

- het is voor mensen te lezen in tekst editor
- omdat GeoJSON op JSON en JSON op Javascript is gebaseerd, is het heel eenvoudig om er native (i.e. zonder te hoeven parsen of converteren) mee te werken in web browsers en veel programmeertalen (in tegenstelling tot XML/GML)
- er zijn veel tools en bibliotheken voor beschikbaar
- er bestaat een grote community die ermee werkt
- het is mogelijk GeoJSON te combineren met linked data

## beperkingen
- Alleen in combinatie met WGS 84 te gebruiken. Dit heeft gevolgen voor de nauwkeurigheid. 
- Ondersteunt geen 3D geometrieën (solids) - zie hiervoor [CityJSON](https://www.cityjson.org). Het is wel mogelijk om een hoogtecoordinaat (altitude) op te nemen bij punten, lijnen en vlakken.

## afspraken
Er zijn afspraken nodig over het aantal decimalen in coordinaten en over het gebruikte CRS. Wanneer gebruik je WGS 84, wanneer RD en hoe wissel je die laatste uit. 

### aantal decimalen
Uit GeoJSON standaard: 

> The size of a GeoJSON text in bytes is a major interoperability consideration, and precision of coordinate values has a large impact on the size of texts. A GeoJSON text containing many detailed Polygons can be inflated almost by a factor of two by increasing coordinate precision from 6 to 15 decimal places.  For geographic coordinates with units of degrees, 6 decimal places (a default common in, e.g., sprintf) amounts to about 10 centimeters, a precision well within that of current GPS systems.  Implementations should consider the cost of using a greater precision than necessary.

> Furthermore, the WGS 84 datum is a relatively coarse approximation of the geoid, with the height varying by up to 5 m (but generally between 2 and 3 meters) higher or lower relative to a surface parallel to Earth's mean sea level.

### coordinaatreferentiesysteem
TODO - Wanneer gebruik je WGS 84, wanneer RD en hoe wissel je die laatste uit.

## how to
TODO

- hoe: geojson conneg The media type application/geo+json is used to designate that content is provided in GeoJSON format
- hoe: simplified geometries
- hoe: URI's in GeoJSON (zie Note hierover in BP 10)