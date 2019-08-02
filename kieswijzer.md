# Kieswijzer bestandsformaten

Dit hoofdstuk geeft het overzicht: wanneer gebruik je GML, GeoJSON, GeoPackage, en RDF. Wat zijn de overwegingen en in welke situatie is welke encoding het meest geschikt. 

Dit wordt een soort consumentenbond beslisboom. Grofweg spelen de volgende keuzes een rol: 

-	Aanleverkant in ‘keten’ of tussen systemen, vs uitleverkant
-	Bekende vs onbekende gebruiker
-	Gebruiker is GIS-er of niet-geo developer
-	Grote vs kleine datahoeveelheden
-	Download vs web
-	Archiveren vs nu gebruiken
-	Puur geo vs combi met tekst 
-	Validatie belangrijk of niet
-	Nauwkeurigheid van de data belangrijk of niet
-	Behoefte aan bogen of niet
-	Is het 3D data of niet
-	Semantiek belangrijk of niet

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