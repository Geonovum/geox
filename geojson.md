# GeoJSON

JSON [[RFC8259]] is een codering voor gegevens in een op JavaScript gebaseerd formaat. Vaak wordt JSON als alternatief voor XML gebruikt om gestructureerde gegevens te coderen en uit te wisselen.

GeoJSON [[RFC7946]] gebruikt JSON om geografische gegevens te coderen. Het is bedoeld om simpele geografische objecten te representeren inclusief hun ruimtelijke en niet-ruimtelijke eigenschappen. GeoJSON ondersteunt de volgende geometrische objecten: 
- punten: `Point` en `MuliPoint`
- lijnen: `LineString` en `MultiLineString`
- vlakken: `Polygon` en `MultiPolygon`
- multigeometrie: `GeometryCollection` waarin een mix van de bovenstaande geometrietypen kan voorkomen. 

Een GeoJSON object representeert ofwel een losse geometrie, een `Geometry`; ofwel een enkel geo-object, een `Feature`; of een lijst van geo-objecten, een `FeatureCollection` met daarin meerdere features. Elk `Feature` bevat een `geometry` eigenschap waarin de geometrie is opgenomen; en een `properties` eigenschap waarin de niet-geometrische eigenschappen staan.  

GeoJSON is ontstaan als informele community standaard, opgesteld in een internet werkgroep. Ondersteuning voor GeoJSON is er in sommige geografische databases en GIS softwarepakketten, en is breed aanwezig in web mapping libraries en APIs van bijvoorbeeld Google, Yahoo en Twitter.

GeoJSON is een prima formaat voor de meeste toepassingen - zeker in web toepassingen - bijvoorbeeld om iconen of polygonen bovenop een kaart op het web weer te geven. De browser toont dan een basiskaart, haalt de daar bovenop weer te geven geodata op, en combineert deze met de basiskaart met behulp van een JavaScript library.

Een voordeel van dit formaat is dat het te lezen is in een tekst editor, in tegenstelling tot GeoPackage bestanden die binair zijn. Dit maakt GeoJSON wat eenvoudiger in gebruik. JSON is heel geschikt voor web toepassingen, bijvoorbeeld voor publicatie van data in een API of voor visualisatie op het web. Omdat JSON gebaseerd is op JavaScript, is het direct te gebruiken in web toepassingen, zonder dat het eerst geparseerd of geconverteerd moet worden. Het heeft weinig overhead waardoor het goed toepasbaar is binnen een API. Er zijn bovendien veel tools beschikbaar om ermee te werken. Deze voordelen maken GeoJSON goed bruikbaar voor niet-geo experts, die JSON vaak al kennen. 

GeoJSON schrijft WGS-84 voor; dit maakt het geschikt voor visualisatie op het web. Een nadeel van WGS-84 is de lagere nauwkeurigheid in vergelijking met RD; maar voor de meeste toepassingen is data met hoge nauwkeurigheid niet nodig. 

In veel gevallen is de nauwkeurigheid van GeoJSON in combinatie met WGS-84 voldoende; op het Geoforum wordt er bijvoorbeeld zelden gevraagd om data met hoge nauwkeurigheid. Belangrijker is vindbaarheid van data. De aanbeveling is om GeoJSON alleen in combinatie met WGS-84 te gebruiken. De [Spatial Data on the Web Best Practice](https://www.w3.org/TR/sdw-bp/#bp-crs-choice) raadt aan om geodata, zodra je het aanbiedt op het web, in ieder geval altijd in WGS-84 te publiceren, en daarnaast in andere CRS als daar expliciete behoefte aan is. 

De OGC API Features kan in combinatie met zowel GeoJSON als GML worden gebruikt. Dit laatste is alleen nog interessant als er behoefte is aan nauwkeurigere geometrieën of aan bogen of volumes (die in GeoJSON niet worden ondersteund). 

## Voorbeeld

<aside class="example ds-selector-tabs" title="Voorbeelden van geometrie voor GeoJSON" style="overflow-x: hidden;">
<div class="container--tabs">
  <div class="selectors">
    <ul class="nav nav-tabs">
      <li class="tabs active"><a href="#geojson-polygoon">GeoJSON (Polygon)</a></li>
      <li class="tabs"><a href="#geojson-3d">GeoJSON (3D)</a></li>
    </ul>
    <div class="tab-content">
        <span>GeoJSON features en collections kunnen eenvoudig gebruikt worden in web toepassingen. Met Leaflet of Mapbox kun je bijvoorbeeld al snel interactieve kaarten ter beschikking stellen. Ook zijn er een meerdere visualisatie en validatie tools beschikbaar (zoals <a href="https://geojsonlint.com/">GeoJSONLint</a> en <a href="https://geojson.io">GeoJSON.io</a>).</span>
      <div id="geojson-3d" class="tab-pane">
        <pre>
<br>{
  <br>"type": "Feature",
  <br>"geometry": {
    <br>"type": "MultiPolygon",
    <br>"coordinates": [           
            <br>[
                <br>[
                    <br>[4.884067, 52.375343], [4.883980, 52.375252],
                    <br>[4.884259, 52.375159], [4.884299, 52.375205],
                    <br>[4.884336, 52.375191], [4.884375,52.3752393],
                    <br>[4.884067, 52.375343]
                <br>]
           <br>],
           <br>[
               <br>[
                   <br>[4.884196, 52.375238], [4.884169, 52.375212], 
                   <br>[4.884214, 52.375198], [4.884238, 52.375223], 
                   <br>[4.884196, 52.375238]
               <br>]
           <br>]
         <br>]
  <br>},
  <br>"properties": {
    <br>"name": "Anne Frank's House"
  <br>}
<br>}
      </pre>        
      </div>
      <div id="geojson-polygoon" class="tab-pane active">
        (*Bron: Spatial Data on the Web Best Practice, [Coordinates encoded using GeoJSON](https://www.w3.org/TR/sdw-bp/#ex-crs-geojson)*)
        <pre>
{
  "type": "Feature",
  "geometry": {
    "type": "Polygon",
    "coordinates": [
      [ [4.884235, 52.375108], [4.884276, 52.375153], 
        [4.884257, 52.375159], [4.883981, 52.375254], 
        [4.883850, 52.375109], [4.883819, 52.375075], 
        [4.884104, 52.374979], [4.884143, 52.374965], 
        [4.884207, 52.375035], [4.884263, 52.375016], 
        [4.884320, 52.374996], [4.884255, 52.374926], 
        [4.884329, 52.374901], [4.884451, 52.375034], 
        [4.884235, 52.375108] ]
      ]
  },
  "properties": {
    "name": "Anne Frank's House",
    "description": "Museum house where Anne Frank & her family hid from the Nazis in a secret annex, during WWII."
  }
}
      </pre>
      </div>
    </div>
  </div>
</div>
</aside>

## Overwegingen

| Vraag                                                                              | Antwoord | Toelichting |
|------------------------------------------------------------------------------------|----------|-------------|
| Is het format geospecifiek?                                                        |<span id="vinkje">&#10003;</span>  |             |
| Is het format gebaseerd op algemene ict standaarden?                               |<span id="vinkje">&#10003;</span>  | Gebaseerd op JSON (Javascript Object Notation), waardoor het heel eenvoudig is om er native (i.e. zonder te hoeven parsen of converteren) mee te werken in web browsers en veel programmeertalen (in tegenstelling tot XML/GML). Praktische voordelen: het is voor mensen te lezen in een tekst editor, er zijn veel tools en bibliotheken voor beschikbaar en er bestaat een grote community die ermee werkt. |
| Wordt het format ondersteund in GIS software?                                      |<span id="tilde">&#65374;</span>   | Deels, niet in alle pakketten [check nodig]           |
| Ondersteunt het format het uitdrukken van schema's, en validatie tegen dat schema? |<span id="vinkje">&#10003;</span>  | JSON heeft een eigen schema formaat, [JSON Schema](https://json-schema.org/draft/2020-12/json-schema-core.html). Daarnaast zijn er YAML definities beschikbaar.            |
| Ondersteunt het format meerdere coordinaatsystemen?                                |<span id="tilde">&#65374;</span>   |  Formeel niet, hoewel er een loophole in de standaard zit en dit in de praktijk wel door tooling ondersteund wordt. Als er door alle aanbiedende en gebruikende partijen een afspraak over is, kan GeoJSON dus in combinatie met een andere CRS gebruikt worden.|
| Ondersteunt het format 3D?                                                         |<span id="tilde">&#65374;</span>   |  Hoewel GeoJSON 3D geometrieen niet direct ondersteunt, is het wel mogelijk om een hoogtecoordinaat (altitude) op te nemen bij punten, lijnen en vlakken. Hiermee zou je 2D polygonen kunnen optrekken naar 3D. |
| Ondersteunt het format alle simple features geometrieen?                           |<span id="vinkje">&#10003;</span>  | Ja, GeoJSON ondersteunt alle 7 geometrietypes vanuit Simple Features. <!-- Echter maakt het format niet gebruik van een feature model - dit betekent dat de features verschillende hoeveelheden (en types) attributen kunnen bezitten, waardoor uitwisseling van data conform het General Feature Model lastig is. --> |
| Ondersteunt het format andere ISO 19107 geometrie types?                           |<span id="kruisje">&#10005;</span> | Geen ondersteuning voor bogen, volumes of andere niet-simpele geometrietypen.            |
| Is het format geschikt voor grote volumes?                                         |<span id="tilde">&#65374;</span>   | Het zit een beetje tussen andere formaten in, maar is beter geschikt voor kleine volumes.           |
| Is het format geschikt om semantiek aan te koppelen / in uit te drukken?           |<span id="vinkje">&#10003;</span>  |  Het is mogelijk om GeoJSON met linked data te combineren door gebruik te maken van [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/). |


## Afspraken

### 3D geometrie
Uit de GeoJSON standaard:

> A position is an array of numbers.  There MUST be two or more elements.  The first two elements are longitude and latitude, or easting and northing, precisely in that order and using decimal numbers.  Altitude or elevation MAY be included as an optional third element.

> An OPTIONAL third-position element SHALL be the height in meters above or below the WGS 84 reference ellipsoid. 

Hierboven wordt een voorbeeld gegeven van een polygoon waarbij de 3D conventie is toegepast. Het representeren van 3D geometrieën beperkt zich daarom tot gevallen waarbij het voldoende is om extrusies te gebruiken van 2D geometrieën (2.5D). Daarnaast wordt er in de praktijk wel eens afgeweken van deze conventie - zo scrhijft <a href="https://docs.mapbox.com/mapbox-gl-js/api/">MapBox GL </a> voor om een property  `height` op te nemen in GeoJSON, voor het weergeven van 3D geometrieën in interactieve kaarten. 

### Naamgeving

GeoJSON heeft geen specifieke naamgevingsconventies, echter kunnen de conventies van JSON gebruikt worden:

- Attribuut namen dienen betekenisvol te zijn, met duidelijke semantiek.
- Attribuut namen dienen camel-cased (ie, wordWordWord) ascii strings te zijn.
- Het eerste teken dien een letter, een underscore (\_) of een dollarteken ($) te zijn. Navolgende tekens kunnen letters, cijfers, underscore of dollartekens zijn. Gereserveerde JavaScript keywords moeten vermeden worden.
Bron: https://google.github.io/styleguide/jsoncstyleguide.xml

- Member namen dienen camel-cased te zijn.
- Member dienen te beginnen en te eindigen met “a-z” (U+0061 tot U+007A)
- Member dienen alleen ASCII alphanumerische tekens te zijn (i.e., “a-z”, “A-Z”, and “0-9”)
Bron: https://jsonapi.org/recommendations/

### Aantal decimalen
Uit de GeoJSON standaard: 

> The size of a GeoJSON text in bytes is a major interoperability consideration, and precision of coordinate values has a large impact on the size of texts. A GeoJSON text containing many detailed Polygons can be inflated almost by a factor of two by increasing coordinate precision from 6 to 15 decimal places.  For geographic coordinates with units of degrees, 6 decimal places (a default common in, e.g., sprintf) amounts to about 10 centimeters, a precision well within that of current GPS systems.  Implementations should consider the cost of using a greater precision than necessary.

> Furthermore, the WGS 84 datum is a relatively coarse approximation of the geoid, with the height varying by up to 5 m (but generally between 2 and 3 meters) higher or lower relative to a surface parallel to Earth's mean sea level.

<!-- TODO - Wanneer gebruik je WGS 84, wanneer RD of ETRS89 en hoe wissel je die laatste twee uit.
Gebruiken we wel of niet GeoJSON in combinatie met andere coordinaatreferentiesystemen dan WGS 84? En als we dit wel doen, hoe communiceer je dan wat het coordinaatreferentiesysteem van je data is? Hier moeten we afspraken over maken.  -->

### Gebruik in uitwisseling

De OGC heeft een set templates voor YAML schema’s die horen bij de OGC Feature API standaard, waarin ook GeoJSON geometrie beschreven is. YAML is een serialisatie format waarmee men OpenAPI definities vastlegt. Deze definities worden gebruikt om APIs op een eenduidige manier de beschrijven en te documenteren, zodat gebruikers begrijpen hoe ze de APIs kunnen bevragen. De templates van OGC zijn handig te gebruiken in API's waarmee geo-objecten gepubliceerd worden. De templates voor het definiëren van de schema's voor GeoJSON bevragingen zijn te vinden op [featureCollectionGeoJSON.yaml](http://schemas.opengis.net/ogcapi/features/part1/1.0/openapi/schemas/featureCollectionGeoJSON.yaml) en [featureGeoJSON.yaml](http://schemas.opengis.net/ogcapi/features/part1/1.0/openapi/schemas/featureGeoJSON.yaml). Uiteraard bevatten deze templates alleen de generieke informatie die van toepassing is voor het definiëren van de geometrie. Specifieke informatie over typeringen en attributen zullen aanbieders zelf moeten toevoegen. 

<!-- ## how to -->
<!-- - Content negotiation met GeoJSON: het media type `application/geo+json` wordt gebruikt om aan te geven dat data wordt aangeboden in  GeoJSON formaat. -->
### URIs in GeoJSON

JSON (en daarbij GeoJSON) staat alleen zekere primitieve datatypes toe. Om deze reden worden URIs geregistreerd als strings. Om de URIs alsnog te kunnen interpreteren zijn conventies nodig. Echter is het vanuit GeoJSON niet mogelijk om zulke conventies vast te leggen. Daarom is het belangrijk om informatie over je GeoJSON bestanden (bijvoorbeeld: details over object types, definities, etc) te registreren in de documentatie. Dit wordt verder beschreven in [[Spatial Data on the Web Best Practice] 10](https://www.w3.org/TR/sdw-bp/#entity-level-links)).

