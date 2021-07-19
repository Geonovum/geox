# Geography Markup Language (GML)

## Introductie
Geography Markup Language [[gml]] is een uitwisselingsformaat voor geografische bestanden met een omvangrijke verzameling XML elementen voor het beschrijven van geografische data. Deze standaard is opgenomen in de [pas-toe-of-leg-uit lijst van het Forum Standaardisatie](https://www.forumstandaardisatie.nl/open-standaarden/geo-standaarden). Het definieert XML-codering voor het overbrengen en opslaan van allerlei geo-informatie, zoals geometrie, topografie, coverages en sensordata. GML kan worden gebruikt voor bestandsuitwisseling tussen systemen maar ook binnen webservices zoals WFS.

GML is een uitgebreide standaard die oplossingen biedt voor uiteenlopende situaties en variaties in het uitwisselen van geo-informatie. Variaties zijn er bijvoorbeeld in geometrietypen, maar ook in complexiteit van datastructuren. Om op verschillende complexiteitsniveaus met GML te werken, heeft het OGC profielen gemaakt. Deze profielen omschrijven elk een subset van de totale GML-set. De standaardprofielen zijn GML Simple Feature Profile level 0, 1 en 2. Hoe hoger het level, hoe meer je ermee kan. Maar ook: hoe complexer en minder generiek het model wordt. Het is daarom altijd van belang voor- en nadelen van het te gebruiken profiel tegen elkaar af te wegen. De Handreiking Geometrie in model en GML beschrijft de [toegestane geometrieen voor elk profiel](https://docs.geostandaarden.nl/nen3610/gimeg/#inhoud-sf-niveau-s) in detail. 

GML is gestandaardiseerd bij het OGC en, omdat OGC en ISO met elkaar samenwerken, ook gestandaardiseerd als ISO 19136:2007 [[iso-19136-2007]]. Inhoudelijk is dit dezelfde standaard. De ISO variant is opgenomen als nationale standaard in de Pas-toe-of-leg-uit-lijst van het Forum Standaardisatie. In Nederland wordt dus GML 3.2.2 gehanteerd, en GML 3.3 (dit is een uitbreiding op GML 3.2). De diverse onderdelen uit de 3.3 versie zijn modulair toe te passen en backwards compatible met versie 3.2. In Nederland wordt GML 3.1.1 ook nog ondersteund, omdat CityGML 2.0 [[CityGML20]] er gebruik van maakt en daarmee het BGT|IMGeo model. Omdat GML 3.2 een zeer uitgebreide standaard is wordt in Nederland met het [Simple Feature Profile level 2](https://docs.geostandaarden.nl/nen3610/gimeg/#simple-features-profile-2-sf2) gewerkt. 

GML is een uitgebreide standaard, die veel use cases aan kan:
- Ondersteunt 3D geometrieën, inclusief volumes (solids).
- Ondersteunt bogen (ook in het simple features profiel).
- Zeer uitgebreide mogelijkheden voor validatie.
- Geen beperking wat betreft coordinaatreferentiesystemen.

Juist de uitgebreidheid van GML geeft problemen bij de toepassing; het is een flinke taak om een goede en volledige implementatie van de standaard te maken. Ook het feit dat GML gebaseerd is op XML is soms een handicap. Tijdens de implementatie kan men tegen de volgende zaken aanlopen:
- Hoewel complexe datastructuren mogelijk zijn in GML, is het in de praktijk, vanwege gebrekkige support hiervoor, vaak toch nodig om de structuur 'plat te slaan' zoals beschreven in <a href="https://docs.geostandaarden.nl/nen3610/gimeg/#sf2tosf0">Basisregels voor transformatie van een SF2 naar een SF0 model</a>. 
- De support voor GML in (GIS en andere) software is beperkt. Meestal is een conversiestraat (ETL) nodig om GML in te kunnen lezen.
- Bij grote datavolumes niet geschikt vanwege de verbositeit van XML.
- Minder geschikt voor publicatie op het web vanwege de complexiteit van XML.

## Voorbeelden
<aside class="example ds-selector-tabs" title="Voorbeelden van geometrie voor GeoJSON" style="overflow-x: hidden;">
<div class="container--tabs">
  <div class="selectors">
    <ul class="nav nav-tabs">
      <li class="tabs active"><a href="#gml-polygoon">GML - Voorbeeld 1</a></li>
      <li class="tabs"><a href="#gml-punt">GML - Voorbeeld 2</a></li>
    </ul>
    <div class="tab-content">
      <div id="gml-punt" class="tab-pane">
        Dit voorbeeld toont een fragment GML data in 3D, conform het [[CityGML20]] model.
      	<pre>
(*Bron: [Open datasets created with 3dfier](https://3d.bk.tudelft.nl/opendata/3dfier/)*)
<br>&lt;CityModel xmlns="http://www.opengis.net/citygml/2.0"
<br>xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
<br>xmlns:gml="http://www.opengis.net/gml"
<br>xmlns:wtr="http://www.opengis.net/citygml/waterbody/2.0"
<br>xsi:schemaLocation="http://www.opengis.net/citygml/2.0 ./CityGML_2.0/CityGML.xsd">
<br>&lt;gml:name>my 3dfied map&lt;/gml:name>
<br>&lt;gml:boundedBy>
  <br>&lt;gml:Envelope srsDimension="3" srsName="urn:ogc:def:crs:EPSG::7415">
      <br>&lt;gml:lowerCorner>84122.824 446278.566 0&lt;/gml:lowerCorner>
      <br>&lt;gml:upperCorner>85999.614 447862.988 100&lt;/gml:upperCorner>
  <br>&lt;/gml:Envelope>
<br>&lt;/gml:boundedBy>
<br>&lt;cityObjectMember>
    <br>&lt;wtr:WaterBody gml:id="be551d510-0324-11e6-b420-2bdcc4ab5d7f">
        <br>&lt;wtr:lod1MultiSurface>
            <br>&lt;gml:MultiSurface>
                <br>&lt;gml:surfaceMember>
                    <br>&lt;gml:Polygon>
                        <br>&lt;gml:exterior>
                            <br>&lt;gml:LinearRing>
                                <br>&lt;gml:pos>85530.000 446588.709 -0.010&lt;/gml:pos>
                                <br>&lt;gml:pos>85531.832 446605.616 -0.010&lt;/gml:pos>
                                <br>&lt;gml:pos>85478.851 446567.507 -0.010&lt;/gml:pos>
                                <br>&lt;gml:pos>85530.000 446588.709 -0.010&lt;/gml:pos>
                            <br>&lt;/gml:LinearRing>
                        <br>&lt;/gml:exterior>
                    <br>&lt;/gml:Polygon>
                <br>&lt;/gml:surfaceMember>
              <br>&lt;/gml:MultiSurface>
            <br>&lt;/wtr:lod1MultiSurface>
        <br>&lt;/wtr:WaterBody>
      <br>&lt;/cityObjectMember>
<br>&lt;/CityModel>
		</pre>        
      </div>
      <div id="gml-polygoon" class="tab-pane active">
      Een fragment GML voor het voorbeeld uit de andere secties ([HTML](#HTML), [GeoJSON](#GeoJSON), [RDF](#RDF)), conform model 'ex'.
    	<pre>
&lt;FeatureCollection xmlns:gml="http://www.opengis.net/gml/3.2"
xmlns="http://www.geonovum.nl/IMVoorbeeld"
xmlns:ex="http://www.example.com/ex"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
&lt;gml:boundedBy>
  &lt;gml:EnvelopesrsDimension="2"srsName="urn:opengis:def:crs:EPSG::4326">
    &lt;gml:lowerCorner>4.884235 52.375108&lt;/gml:lowerCorner>
    &lt;gml:upperCorner>4.884451 52.375034 4.884235&lt;/gml:upperCorner>
  &lt;/gml:Envelope>
&lt;/gml:boundedBy>
  &lt;featureMember>
    &lt;ex:Gebouw gml:id="H10">
     &lt;ex:naam>Anne Frank's Huis&lt;/ex:naam>
     &lt;ex:geometrie>
        &lt;gml:Polygon gml:id="geom2">
            &lt;gml:exterior>
                &lt;gml:LinearRing>
                    &lt;gml:posList>4.884235 52.375108 4.884276 52.375153 4.884257 52.375159 4.883981 52.375254 4.883850 52.375109 4.883819 52.375075 4.884104 52.374979 4.884143 52.374965 4.884207 52.375035 4.884263 52.375016 4.884320 52.374996 4.884255 52.374926 4.884329 52.374901 4.884451 52.375034 4.884235 52.375108&lt;/gml:posList>
                &lt;/gml:LinearRing>
            &lt;/gml:exterior>
        &lt;/gml:Polygon>
     &lt;/ex:geometrie>     
    &lt;/ex:Gebouw>
  &lt;/featureMember>
&lt;/FeatureCollection>
      </pre>
      </div>
    </div>
  </div>
</div>
</aside>

## Keuze-aspecten
De volgende tabel geeft aan hoe GML scoort op de aspecten die een rol spelen bij de keuze voor een bestandsformaat.

| Vraag                                                                              | Antwoord | Toelichting |
|------------------------------------------------------------------------------------|----------|-------------|
| Is het format geospecifiek?                                                        | <span id="vinkje">&#10003;</span>  | Ja, maar de uitgebreidheid van GML geeft problemen bij de toepassing; het is een flinke taak om een goede en volledige implementatie van de standaard te maken. |           |
| Is het format gebaseerd op algemene ict standaarden?                               | <span id="vinkje">&#10003;</span>  |  Ja, GML is gebaseerd op XML (wat ook een nadeel kan zijn vanwege de complexiteit van XML)           |
| Wordt het format ondersteund in GIS software?                                      | <span id="tilde">&#65374;</span>   |  De support voor GML in (GIS en andere) software is beperkt. Over het algemeen is een conversiestraat (ETL) nodig om GML in te kunnen lezen.           |
| Ondersteunt het format het uitdrukken van schema's, en validatie tegen dat schema? | <span id="vinkje">&#10003;</span>  |Er zijn zeer uitgebreide mogelijkheden voor validatie vanwege de XML basis.           |
| Ondersteunt het format meerdere coordinaatsystemen?                                | <span id="vinkje">&#10003;</span>  | In GML kan de definitie van een CRS via een URI worden meegegeven, als waarde van het attribuut `srsName`. Er is dus geen beperking wat betreft coordinaatreferentiesystemen.             |
| Ondersteunt het format 3D?                                                         | <span id="vinkje">&#10003;</span>  | GML ondersteunt 3D geometrieën, inclusief volumes (solids). |
| Ondersteunt het format alle simple features geometrieen?                           | <span id="vinkje">&#10003;</span>  | Het format ondersteunt alle simple features geometrieën, inclusief bogen. |
| Ondersteunt het format andere ISO 19107 geometrie types?                           | <span id="vinkje">&#10003;</span>  |             |
| Is het format geschikt voor grote volumes?                                         | <span id="kruisje">&#10005;</span>  | Bij grote datavolumes niet geschikt vanwege de verbositeit van XML.            |
| Is het format geschikt om semantiek aan te koppelen / in uit te drukken?           | <span id="kruisje">&#10005;</span>  | Semantiek kan op impliciete wijze worden toegevoegd door het schema af te leiden uit een informatiemodel en eventueel door in annotaties te linken naar een begrippenkader of tekstuele definities in het schema op te nemen.            |

## Afspraken

### Naamgeving

Voor XML elementen geldt dat de naam moet beginnen met een letter of underscore, en dat deze naam nooit mag beginnen met 'xml'. Element namen zijn hoofdlettergevoelig en mogen geen spaties bevatten. Voor GML geldt daarnaast dat UpperCamelCase wordt gebruikt voor XML element namen die betrekking hebben op Objects of Feature Types, en lowerCamelCase voor XML element namen die attributen of relaties representeren.  Verder zijn er ook conventies voor GML schema's met als doel de leesbaarheid van deze documenten te verbeteren: 
- abstracte elementen hebben een prefix 'Abstract' (voor Objects) of 'abstract' (voor attributen) gekoppeld aan hun naam.
- de namen van XML Schema complex types zijn in UpperCamelCase, en eindigen op het woord 'Type'. Daarnaast begint een abstracte XML Schema complex type met de prefix 'Abstract'.