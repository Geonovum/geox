# GeoPackage
<p class='note'>Voor nu staan hier alleen even wat bevindingen over GeoJSON uit de werkgroep lichtere formaten. Dit moet een uitgebreidere tekst worden, maar die moet nog geschreven worden. </p>

Een OGC standaard die gebaseerd is op SQLLite, voor uitwisseling van geodata. Het wordt wel gezien als vervanger van Shapefiles.

Een groot voordeel van GeoPackage is dat het formaat ook functionaliteit bevat voor visualisatie (in een extensie van de standaard), schema, tiling, metadata etc. De overstap van shapefiles naar GeoPackage is niet lastig. Je kan er ook niet-geo data in opslaan. De ETL straat van organisaties kan door gebruik van GeoPackage korter worden; er is goede ondersteuning voor GeoPackage in veel GIS software. 

Bestanden worden soms wel erg groot, bijvoorbeeld de landelijke set van BGT wegdelen was meer dan 60gb. Maar op zich zijn grote volumes geen probleem. 

GeoPackage werkt doorgaans met platte datastructuren, de vaak complexe modellen van basisregistraties moeten dus worden 'platgeslagen'.

GeoPackage werkt standaard met numerieke ID's. Dit geeft problemen met ID's van basisregistraties, die niet altijd numeriek zijn. De applicatie is aangepast om GeoPackage bestanden te kunnen doorzoeken op basis van het lokaal ID van basisregistraties in plaats van het standaard, numerieke ID.

Het is een binair formaat, niet in een tekst editor te openen. 

GeoPackage is aangemeld voor de pas-toe-of-leg-uit lijst. 

## afspraken
Er is behoefte aan afspraken over naamgeving van klassen/attributen, en hoe je visualisatie/metadata opneemt.