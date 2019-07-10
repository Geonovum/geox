## GeoJSON

<p class='note'>Voor nu staan hier alleen even wat bevindingen over GeoJSON uit de werkgroep lichtere formaten. Dit moet een uitgebreidere tekst worden, maar die moet nog geschreven worden. </p>

Een prima formaat voor de meeste toepassingen.

Een voordeel van dit formaat is dat het te lezen is in een tekst ditor, in tegenstelling tot GeoPackage bestanden die binair zijn. Dit maakt GeoJSON wat eenvoudiger in gebruik.

GeoJSON schrijft WGS 84 voor; dit maakt het geschikt voor visualisatie op het web.

WFS 3 kan in combinatie met GML worden gebruikt, dit is alleen nog interessant als er behoefte is aan nauwkeurigere geometrieën of aan arcs (die in GeoJSON niet worden ondersteund). Andere use cases voor GML/XML zien de PDOK ontwikkelaars niet meer.

In veel gevallen is de nauwkeurigheid van GeoJSON voldoende; op het Geoforum wordt er zelden naar gevraagd. Belangrijker is vindbaarheid van data. De aanbeveling is om GeoJSON alleen in combinatie met WGS 84 te gebruiken.