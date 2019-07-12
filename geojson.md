# GeoJSON

<p class='note'>Voor nu staan hier alleen even wat bevindingen over GeoJSON uit de werkgroep lichtere formaten. Dit moet een uitgebreidere tekst worden, maar die moet nog geschreven worden. </p>

Een prima formaat voor de meeste toepassingen.

Een voordeel van dit formaat is dat het te lezen is in een tekst editor, in tegenstelling tot GeoPackage bestanden die binair zijn. Dit maakt GeoJSON wat eenvoudiger in gebruik. JSON is heel geschikt voor web toepassingen, bijvoorbeeld voor publicatie van data in een API of voor visualisatie op het web. Het maakt geodata ook bruikbaar voor niet-geo experts. Er zijn veel tools beschikbaar om ermee te werken. Het is mogelijk om GeoJSON met linked data te combineren door gebruik te maken van [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/). 

GeoJSON schrijft WGS 84 voor; dit maakt het geschikt voor visualisatie op het web.

WFS 3 kan in combinatie met GML worden gebruikt, dit is alleen nog interessant als er behoefte is aan nauwkeurigere geometrieën of aan arcs (die in GeoJSON niet worden ondersteund). Andere use cases voor GML/XML zien de PDOK ontwikkelaars niet meer.

In veel gevallen is de nauwkeurigheid van GeoJSON voldoende; op het Geoforum wordt er zelden gevraagd om data met hoge nauwkeurigheid. Belangrijker is vindbaarheid van data. De aanbeveling is om GeoJSON alleen in combinatie met WGS 84 te gebruiken. De [Spatial Data on the Web Best Practice](https://www.w3.org/TR/sdw-bp/#bp-crs-choice) raadt aan om geodata op het web in ieder geval in WGS 84 te publiceren.  

## beperkingen
- Alleen in combinatie met WGS 84 te gebruiken
- Ondersteunt geen 3D geometrieën (solids) - zie hiervoor [CityJSON](https://www.cityjson.org).

## afspraken
Er zijn afspraken nodig over het aantal decimalen in coordinaten en over het gebruikte CRS. Wanneer gebruik je WGS 84, wanneer RD en hoe wissel je die laatste uit. 