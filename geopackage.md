# GeoPackage

## Introductie
GeoPackage is een [OGC](https://www.opengeospatial.org) standaard die gebaseerd is op [SQLLite](https://www.sqlite.org/), voor de uitwisseling van geodata. Het wordt wel gezien als vervanger van Shapefiles.

GeoPackage is in 2019 [aangemeld voor de pas-toe-of-leg-uit lijst](https://www.geonovum.nl/over-geonovum/actueel/geopackage-aanmelden-voor-pas-toe-of-leg-uit-lijst). 

GeoPackage is een “licht” formaat om geografische informatie uit te wisselen. Veel geografische software ondersteunt de GeoPackage standaard al, waaronder ook een paar populaire pakketten die moeite hebben met de verwerking van GML. GeoPackage is een binair formaat, niet in een tekst editor te openen. 

Moderne datasets zoals de Basisregistratie Grootschalige Topografie zijn zó gedetailleerd, dat bestandsomvang een probleem gaat vormen bij het importeren van data in softwaresystemen. GeoPackage is een geschikt formaat voor het uitwisselen van geodatasets met een grote omvang, bijvoorbeeld wanneer gebruikers een grote dataset of subset daarvan willen downloaden om in hun lokale (GIS) systeem te gebruiken voor ruimtelijke analyses. 

Daarnaast biedt GeoPackage ook een voordeel voor nieuwe gebruikers. Doordat GeoPackage gebaseerd is op generiekere ICT-oplossingen als SQLite, wordt geografische informatie beter toegankelijk voor gebruikers buiten het geo-domein. 

Veel uitwisseling in het geo-informatiedomein verloopt nu in ketens van bronhouders naar een Landelijke Voorziening, van die Landelijke Voorziening naar een service provider en van de service provider naar een gebruiker. In de levering van bronhouder naar landelijke voorziening is het van belang dat het uitwisselformaat validatie mogelijk maakt. Zo kan je controleren of de informatiemodellen correct zijn toegepast, of de geometrie klopt etc. Daar is GML het meest geschikt voor. In de stap van serviceprovider naar gebruiker is validatie minder van belang dan zaken als performance, bestandsgrootte en ondersteuning in software. In die stap is GeoPackage, net als GeoJSON, een goed formaat om naast GML aan te bieden.

Een ander voordeel van GeoPackage is dat het formaat ook functionaliteit bevat voor visualisatie (in een extensie van de standaard), schema, tiling, metadata etc. De overstap van shapefiles naar GeoPackage is niet lastig. Je kan er ook niet-geo data in opslaan. De ETL straat van organisaties kan door gebruik van GeoPackage korter worden; er is goede ondersteuning voor GeoPackage in veel GIS software. 

Bestanden worden soms zelfs in GeoPackage wel erg groot, bijvoorbeeld de landelijke set van BGT wegdelen was in een test tijdens de WFS-3 werkweek meer dan 60GB.  

GeoPackage werkt doorgaans met platte datastructuren, de vaak complexe informatiemodellen van bijvoorbeeld basisregistraties moeten dus worden 'platgeslagen' zoals beschreven in <a href="#sf2tosf0"></a>.

GeoPackage werkt standaard met numerieke ID's. Dit geeft problemen met ID's van basisregistraties, die niet altijd numeriek zijn. Tijdens de WFS-3 werkweek bleek dat de applicatie moest worden aangepast om GeoPackage bestanden te kunnen doorzoeken op basis van het lokaal ID van basisregistraties in plaats van het standaard, numerieke ID.

## Voordelen
- Gebaseerd op SQLite, daardoor toegankelijk voor grotere doelgroep datagebruikers
- Kan grote datavolumes aan
- Ondersteunt meerdere coordinaatreferentiesystemen
- Goede ondersteuning in (GIS) software
- Extensies maken het opnemen van visualisatie, tiling, metadata etc binnen één GeoPackage bestand mogelijk

## Beperkingen
- Workaround nodig bij het gebruik van niet-numerieke ID's 
- Datastructuur moet platgeslagen worden
- Geen ondersteuning voor 3D volumes (solids) 
- Niet valideerbaar (op dit moment wordt onderzocht of dit toch mogelijk is)

## Afspraken
TODO

Er is behoefte aan afspraken over naamgeving van klassen/attributen, en hoe je visualisatie/metadata opneemt.