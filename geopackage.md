## GeoPackage
<p class='note'>Voor nu staan hier alleen even wat bevindingen over GeoJSON uit de werkgroep lichtere formaten. Dit moet een uitgebreidere tekst worden, maar die moet nog geschreven worden. </p>

Een OGC standaard die gebaseerd is op SQLLite, voor uitwisseling van geodata. Het wordt wel gezien als vervanger van Shapefiles.

Bestanden worden soms erg groot, bijvoorbeeld de landelijke set van BGT wegdelen was meer dan 60gb.

GeoPackage werkt doorgaans met platte datastructuren, de vaak complexe modellen van basisregistraties moeten dus worden 'platgeslagen'.

GeoPackage werkt standaard met numerieke ID's. Dit geeft problemen met ID's van basisregistraties, die niet altijd numeriek zijn. De applicatie is aangepast om GeoPackage bestanden te kunnen doorzoeken op basis van het lokaal ID van basisregistraties in plaats van het standaard, numerieke ID.