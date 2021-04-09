# Standaarden

Naast de encoding standaarden zelf zijn er een aantal andere standaarden die ook aandacht verdienen, omdat ze relevant zijn voor het representeren van geometrieën in modellen of omdat ze invloed kunnen hebben op de geschiktheid en toepasbaarheid van de encodings.

## NEN3610

Het Nederlands Basismodel Geo-informatie (NEN 3610) geeft regels voor het eenduidig beschrijven, uitwisselen en op het web publiceren van geo-informatie. 

## ISO 19107:2019

NEN 3610 beschrijft de regels voor het modelleren van geo-informatie. Belangrijk in de definitie van een geografisch object is dat het locatie eigenschappen heeft. Eén van die locatie eigenschappen is de directe locatie die middels coördinaten is beschreven. Door middel van attributen wordt de directe locatie en geometrie door coördinaten gerepresenteerd. De waarden van die attributen zijn coördinaten of coördinaatreeksen die een geometrie representeren. We noemen dit geometrietypen. In ISO 19107 is een klassediagram, het ruimtelijk schema, opgenomen met de geometrietypen en hun onderlinge relaties. De geometrietypen uit dit diagram worden gebruikt om de geometrietypen in geo-informatiemodellen te specificeren. 

### Nederlands profiel op ISO 19107 

Het ruimtelijk schema in al zijn complexiteit is geschikt om zeer gevarieerde representaties van geometrieën te definiëren. Bij het kiezen van geometrietypen ter implementatie in een softwareomgeving is het van belang eisen ten aanzien van interoperabiliteit mee te nemen. In het kader van het Nederlands profiel op ISO 19107 is er gekeken naar GML als implementatieomgeving. Daarin is geëvalueerd welke subset van geometrietypen uit het ruimtelijke schema tot een basisset, een profiel, moeten behoren. Er is daarmee een directe link tussen het Nederlandse profiel op GML en het profiel op ISO 19107.

## ISO 19125:2004 

Het ISO 19107 ruimtelijk schema is geconstrueerd rond de twee criteria van data complexiteit en dimensionaliteit. Er is nog een derde criterium, functionaliteit (operaties), dat echter voor de indeling van de geometrietypen in het ruimtelijk schema geen gevolgen heeft. ISO 19125-1 Simple feature access [iso-19125-1-2004] definieert een model voor 2 dimensionale geometrietypen. In dit 2D geometriemodel zijn restricties opgenomen die van een algemene geometrie een simpele geometrie maken. De term simple feature staat daarin voor features beperkt tot 2 dimensionale geometrie.

### Simple Features Profiel (GML)

De GML standaard is een omvangrijke verzameling van XML elementen en attributen waarmee van alles mogelijk is. De GML standaard bevat bijvoorbeeld definities voor dynamische (voortdurend veranderende) objecten, topologie, complexe geometrische typen, en rasters. Dit maakt GML tot een rijke standaard die veel te bieden heeft, maar maakt het ook moeilijker voor software aanbieders om de hele standaard te ondersteunen.

Om dit probleem te adresseren zijn er verschillende profielen op GML gedefinieerd door de OGC. Een GML profiel is een subset van de complete GML set. De subset is wel zodanig dat het profiel niet in tegenspraak is met de complete set. Voor GML 3.2.1 zijn er drie profielen met toenemende complexiteit, de zogenaamde Simple Features profielen. Softwareleveranciers kunnen ervoor kiezen hun ondersteuning van GML te beperken tot een van deze profielen, of uiteraard om de hele standaard te ondersteunen.

Simple Features Profile 2 is de standaard voor informatiemodellen in Nederland. Het profiel is een subset van het complete GML 3.2. Toch is het in sommige gevallen gewenst om te werken met een nog eenvoudiger informatiemodel, dat met name voor software die de complexere zaken in SF2 niet ondersteunt, te begrijpen is -  hier is SF0 voor. Meer informatie over deze profielen is te vinden in de [Handreiking Geometrie in model en GML](https://www.geonovum.nl/uploads/documents/Geometrieinmodelengml_1.0.pdf) en is op dit moment alleen geschreven vanuit GML perspectief.

Het OGC Simple Features profile moet niet verward worden met de ISO 19125 - Simple feature access standaard. De eerste gaat over implementatie van geometrie in GML de tweede over definities van 2 dimensionale geometrietypen.