# Keuzehulp bestandsformaten
Dit hoofdstuk geeft het overzicht: wanneer gebruik je HTML, GML, GeoJSON, GeoPackage, en RDF. Wat zijn de overwegingen en in welke situatie is welke encoding het meest geschikt.

Bij de keuze voor de juiste encoding speelt de beoogde toepassing een belangrijke rol. Hieronder een lijst met veelvoorkomende toepassingen:

- Web pagina's waarop mensen informatie kunnen vinden over geo-objecten
- Kaarten of andere visualisaties van geodata die gepubliceerd worden op het web
- Data integratie - het combineren van geodata met andere data
- Ruimtelijke analyses - het ontdekken van betekenisvolle patronen in geodata
- Uitwisselen van geodata tussen systemen

Elk van deze toepassingen schept andere behoeften: vaak zal het mogelijk en ook nodig zijn om meerdere toepassingen te ondersteunen met een publicatie van geodata. Hierbij is de keuze van de meest geschikte encoding van groot belang. Het kan in sommige gevallen nodig of handig zijn om de data in verschillende encodings aan te bieden.

Het hoofddoel moet zijn om de geodata te publiceren op een manier die voor gebruikers gemakkelijk te ontcijferen en te gebruiken is. Daarbij is het belangrijk om in je achterhoofd te houden op welke doelgroepen de datapublicatie gericht is en welk doel zij hebben met hun gebruik van de data. Uit het beoogd gebruik valt af te leiden wat voor kenmerken de data moet hebben. Bijvoorbeeld:

- het volume (bestandsgrootte) van de data
- hoe veel ruimtelijke dimensies het bestrijkt (punten, lijnen, vlakken, 3D)
- wat voor gebied het bestrijkt (één gebouw, een stad, een heel land)
- hoe vaak de data verandert
- de nauwkeurigheid die de dataset heeft én de nauwkeurigheid die gebruikers nodig hebben

Bron: <a href ="https://www.w3.org/TR/sdw-bp/#semantic-thing">Spatial Data on the Web Best Practice 4: Use spatial data encodings that match your target audience</a> [[sdw-bp]].

<aside class="note">
Om de lezer te helpen maken we een visuele keuzehulp, bijvoorbeeld een soort beslisboom (de vorm is nog niet bepaald). Samenvatting van de input voor de keuzehulp staat voorlopig in [deze excel sheet](./docs/tabel_uitwisselformaten.xlsx).</aside>

Grofweg spelen de volgende keuzes een rol:

-	Aanleverkant in ‘keten’ of tussen systemen, vs uitleverkant
-	Bekende vs onbekende gebruiker
-	Gebruiker is GIS-er of niet-geo developer
-	Grote vs kleine datahoeveelheden
-	Download vs web
-	Archiveren vs nu gebruiken
-	Puur geo vs combinatie met tekst
-	Validatie belangrijk of niet
-	Nauwkeurigheid van de data belangrijk of niet
-	Behoefte aan bogen of niet
-	Is het 3D data of niet
-	Semantiek belangrijk of niet

## HTML
Positionering:
- Web publicatie en directe visualiatie
- Indexeerbaar door zoekmachines
- Combinatie met tekst
- Mogelijk om begrippenkaders te linken

## GeoJSON
Positionering:
- Aan de uitleverkant
- In Web visualisaties en APIs
- Voor de onbekende gebruiker
- Voor kleine aanleveringen (bijvoorbeeld terugmelden)
- Niet als authentieke bron
- Als er geen ander coördinaatreferentiesysteem dan WGS 84 noodzakelijk is

## GeoPackage
Positionering:
- Overzetten van data van systeem a naar systeem b
- Archivering
- Grote volumes
- Download voor gebruikers

## GML
Positionering:
- Archivering van data
- In combinatie met tekstgerichte uitwisseling (dan is XML namelijk geschikter dan JSON)
- In gevallen waar nauwkeurige validatie van de bestandstructuur en -inhoud heel belangrijk is

## RDF (linked data)
Positionering:
- Publiceren van data op het web, in de meest rijke vorm
- Inclusief semantiek
- Voor integratie van data uit meerdere verschillende bronnen
- Voor slim bevragen van data, waarbij geo en niet-geo aspecten een rol kunnen spelen
