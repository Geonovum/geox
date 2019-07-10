## Geography Markup Language (GML)

<p class='note'>Dit hoofdstuk gaat integraal de tekt bevatten uit hfd 3 en 4 uit de [Handreiking Geometrie in model en GML](https://www.geonovum.nl/uploads/documents/Geometrieinmodelengml_1.0.pdf). </p>

 Het Nederlands Basismodel Geo-informatie (NEN 3610) specificeert in overeenstemming met de ISO-geo-informatiestandaarden GML (Geography Markup Language) als uitwisselingsformaat voor geo-informatie. De actuele standaard voor GML wordt gehanteerd. Op dit moment is dat GML 3.2.1, waarbij ook GML 3.1.1 nog ondersteund wordt. Omdat GML
3.2.1 een zeer uitgebreide standaard is wordt er een profiel, een subset gehanteerd.
GML 3.2.1 is een uitgebreide standaard, ontwikkeld door het Open Geospatial Consortium (OGC) en biedt
oplossingen voor een groot aantal situaties en variaties voor het uitwisselen van geo-informatie. Variaties zijn er in geometrietypen maar ook in complexiteit van datastructuren. Om verschillende niveaus van toepassing van GML 3.2.1 mogelijk te maken zijn er door OGC zogenaamde profielen gemaakt. De
ontwikkeling van de profielen is voortgekomen uit een behoefte van onder meer softwareleveranciers om
verschillende niveaus van complexiteit te ondersteunen. Operabiliteit kan daarmee beter gegarandeerd
worden. De profielen omvatten elk een subset van de totale GML 3.2.1 standaard. De standaardprofielen
zijn Simple Features Profile 0, Simple Features Profile 1 en Simple Features Profile 2 (afgekort tot
respectievelijk SF0, SF1, en SF2). Deze profielen hebben een toenemende complexiteit en bieden ook een
toenemende functionaliteit. SF0 is dus het eenvoudigst, en SF2 het meest uitgebreid. Het OGC Simple
Features profile moet niet verward worden met de ISO 19125 - Simple feature access standaard. De
eerste gaat over implementatie van geometrie in GML de tweede over definities van 2 dimensionale
geometrietypen.

Een profiel dat meer complexiteit en functionaliteit toestaat, biedt meer mogelijkheden voor
datamodellering of geometriebeschrijvingen, maar is ook moeilijker toe te passen in software. Deze
complexiteit kan de uitwisseling tussen verschillende softwareplatforms bemoeilijken. Een eenvoudig
profiel daarentegen biedt minder mogelijkheden voor datamodellering maar is wel eenvoudiger toe te
passen in generieke software. Het is daarom van belang voor- en nadelen tegen elkaar af te wegen.
In Nederland is het SF2 profiel op GML van toepassing verklaard.

### Totstandkoming SF2 als Nederlands profiel op GML
Bij het tot stand komen van het Nederlandse GML profiel zijn een aantal beginselen leidend geweest:
- het profiel moet de eisen van het geo-informatie werkveld weerspiegelen;
- het profiel is gekoppeld aan (toepassingen van) NEN 3610;
- het profiel is een basisprofiel dat basiseisen die door de sectorale informatiemodellen gesteld
worden omvat;
- een sectoraal informatiemodel kan uitbreidingen op het basisprofiel formuleren;
- het profiel moet afgestemd zijn op de actuele technische mogelijkheden die software biedt.

Door deze beginselen geeft het profiel voldoende richting voor standaardisering van algemene
functionaliteit maar ook flexibiliteit voor toepassingen die specifieke oplossingen nodig hebben. Het profiel
geeft richting aan de aanbodkant van geo-informatie en aan de modelleurs van informatiemodellen voor
de oplossingen en mogelijkheden voor datamodellering. Voor softwaretoepassingen biedt het profiel een
basis waar functionaliteit en toepassingen op afgestemd kunnen worden.

[...]