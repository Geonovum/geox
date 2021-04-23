# Standaarden

Naast de encoding standaarden zelf zijn er een aantal andere standaarden die ook aandacht verdienen, omdat ze relevant zijn voor het representeren van geometrieën in modellen of omdat ze invloed kunnen hebben op de geschiktheid en toepasbaarheid van de encodings.

## NEN 3610

Het Nederlands Basismodel Geo-informatie [[NEN3610]] geeft regels voor het eenduidig beschrijven, uitwisselen en op het web publiceren van geo-informatie. 

Relevant voor deze handreiking is dat NEN 3610 de regels beschrijft voor het modelleren van geo-informatie. Belangrijk in de definitie van een geografisch object is dat het locatie eigenschappen heeft. Eén van die locatie eigenschappen is de directe locatie die middels coördinaten is beschreven. Door middel van attributen wordt de directe locatie en geometrie door coördinaten gerepresenteerd. De waarden van die attributen zijn coördinaten of coördinaatreeksen die een geometrie representeren. We noemen dit geometrietypen.

## ISO 19107:2019

De standaard Geographic information - Spatial Schema [[iso-19107-2019]] definieert het ruimtelijk schema: het informatiemodel van geometrieën. In ISO 19107 zijn de geometrietypen, hun eigenschappen en hun onderlinge relaties opgenomen. De geometrietypen uit deze standaard, zoals `GM_Point`, `GM_Curve`, en `GM_Surface` worden gebruikt om de geometrietypen in geo-informatiemodellen te specificeren. 

## ISO 19125:2004 
ISO 19125-1 Simple feature access [[iso-19125-1-2004]] definieert een model voor 2 dimensionale geometrietypen. De daarin opgenomen geometrietypen zijn een selectie uit ISO 19107. De term simple feature staat voor features beperkt tot **2 dimensionale geometrie** en **lineaire interpolatie** (alleen rechte lijnen tussen punten). 

De simpele geometrietypen zijn: 
- **Punt** en **multi-punt**
- **Lijn** en **multi-lijn**
- **Vlak** en **multi-vlak**
- Een generiek geometrietype **Geometry** dat één van bovenstaande kan zijn

### Nederlands profiel op ISO 19107 

Het ISO 19107 ruimtelijk schema in al zijn complexiteit is geschikt om zeer gevarieerde representaties van geometrieën te definiëren. Bij het kiezen van geometrietypen ter implementatie in een softwareomgeving is het van belang eisen ten aanzien van interoperabiliteit mee te nemen. Hiervoor is Simple Features een goed uitgangspunt: het is een selectie van de meest eenvoudige en gangbare geometrietypen, die breed worden ondersteund. In het kader van het Nederlands profiel op ISO 19107, dat jaren geleden is opgesteld, is er naast Simple Features gekeken naar GML als implementatieomgeving. Op basis daarvan is geëvalueerd welke subset van geometrietypen uit het ruimtelijke schema tot de Nederlandse basisset, het profiel, moeten behoren. 

Voor GML 3.2 zijn er drie profielen met toenemende complexiteit, de zogenaamde Simple Features "levels" 0, 1, en 2. Softwareleveranciers kunnen ervoor kiezen hun ondersteuning van GML te beperken tot een van deze levels, of uiteraard om de hele standaard te ondersteunen.

Simple Features Profile level 2 is de standaard voor informatiemodellen in Nederland. Het profiel is een subset van het complete GML 3.2. Toch is het in sommige gevallen gewenst om te werken met een nog eenvoudiger informatiemodel, dat met name voor software die de complexere zaken in SF2 niet ondersteunt, te begrijpen is -  hier is SF0 voor. Meer informatie over deze profielen is te vinden in de Handreiking Geometrie in model en GML [[gimeg]].

Het Nederlands profiel kent dezelfde geometrietypen als ISO 19125: (multi)Punt, (multi)lijn, (multi)vlak, (multi) geometry. Hierbij is voor Nederland afgesproken dat naast lineaire interpolatie, ook interpolatie door middel van cirkelbogen mag worden gebruikt. 
