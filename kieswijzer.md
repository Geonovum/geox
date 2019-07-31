# Kieswijzer bestandsformaten

Dit hoofdstuk geeft het overzicht: wanneer gebruik je GML, GeoJSON, GeoPackage, en RDF. Wat zijn de overwegingen en in welke situatie is welke encoding het meest geschikt. 

Dit wordt een soort consumentenbond beslisboom. 

## GeoJSON
Positionering: 
- Aan de uitleverkant
- In Web visualisaties en APIs
- Voor de onbekende gebruiker
- Voor kleine aanleveringen (bv terugmelden)
- Niet als authentieke bron
- Als er geen ander coordinaaterferentiesysteem dan WGS 84 noodzakelijk is

## GeoPackage
Positionering: 
- Overzetten van data van systeem a naar systeem b
- Archivering
- Grote volumes
- Download voor gebruikers

## GML
Positionering: 
- Archivering van data
- In combinatie met tekstgerichte uitwisseling (dan is XML nl geschikter dan JSON)
- In gevallen waar nauwkeurige validatie van de bestandsstructuur en -inhoud heel belangrijk is