
# Inleiding
Dit document is een handreiking over het modelleren en uitwisselen van geometrie. Wanneer we het over geometrie hebben, hebben we het dus over Simple Features en vector data. En wat is er (niet) speciaal aan vector data, waarom moet je nadenken als je dit wil modelleren en uitwisselen?

Dan over het modelleren van deze geometrie: In een informatiemodel (conceptueel/logisch?) geef je aan welke geometrieen aan bod komen. In de X standaard wordt dit beschreven. Het is belangrijk om te herinneren dat je bij het modelleren ook een paradigma kiest: vaak o-o, maar je zou ook eav kunnen gebruiken. Hoe heeft de keuze voor zo'n paradigma impact op de modellering/uitwisseling van geometrieen? Je hebt bij bepaalde keuzes in het model dan ''extra'' encoding rules nodig om het conform de regels van de uitwisselstandaard te kunnen encoden. Ook kan een bepaalde paradigma interessanter zijn, afhankelijk van je applicatie. Meer over datamodellen en de uitwisseling vind je in hoofdstuk X.

Op basis van één informatiemodel is het dan mogelijk om meerdere "encodings" te definiëren, oftewel implementaties in uitwisselingsformaten. Zoals eerder gezegd, heb je daar soms extra encoding rules voor nodig - hoewel je het liefst wil dat je je model 'out of the box' kunt vertalen in een applicatie schema. Een applicatieschema gebruik je om de data in je database te storen/uit te wisselen. In dit document focussen we op de uitwisseling, echter is het ook belangrijk om je data behoeftes te analyseren om tot een goede oplossing te komen wat betreft je opslag. Soms hoef je die keuzes ook niet apart te maken - als een uitgangspunt is om iets te hebben waarmee je kunt opslaan/uitwisselen, zou je bv kunnen kiezen voor GeoPackage. 

Maar het uiteindelijke doel is de uitwisseling van data, waarbij het belangrijk is om te weten waarvoor/waarom je uitwisselt: voor een bepaalde applicatie, om te voldoen aan eisen, om interne zaken te regelen, etc. Als dit helder is, kun je een betere keuze maken, aangezien de applicatie vaak bepaalde aspecten highlight. Ook kan het zo zijn dat je achteraf beseft dat je een ander format nodig wil, dan is het ook van belang om te kijken naar wrappers/het schakkelen tussen formats.

Al deze consideraties zullen in dit document worden besproken, met het idee om mensen op weg te helpen bij het kiezen van een format voor de uitwisseling van geodata. Deze handreiking geeft daarom handvaten voor het kiezen van het juiste formaat voor de juiste situatie, en geeft in afzonderlijke hoofdstukken gedetaileerde informatie over het uitwisselen van geometrie in GML, JSON, GeoPackage en RDF.

## Doel en doelgroep
Dit document betreft een handreiking voor het gebruiken van lichtere formaten voor de uitwisseling van geodata. De informatie is daarom gericht op aanbieders van geo-informatie die graag:

- Meer willen weten over de afwegingen die je moet maken bij het kiezen van een format


De handreiking beperkt zich tot vectordata.

## Leeswijzer
De handreiking is vormgegeven met het idee dat mensen hun weg erin moeten kunnen vinden ongeacht hun kennis. Daarom worden aspecten die van belang zijn voor de uitwisseling toegelicht met voorbeelden, en worden use cases gebruikt om de te illustreren hoe je keuzes kunt onderbouwen. 

## Terminologie

Dit hoofdstuk beschrijft de definitie van termen die vaak voorkomen in dit document. 

<dl class="termenlijst" data-sort>
  <dt><dfn data-cite="#uitwisselformat" class="preserve">uitwisselformat</dfn></dt>
    <dd>
    Def
    </dd>
  <dt><dfn data-cite="#datamodel" class="preserve">datamodel</dfn></dt>
    <dd>
    Def2
    </dd>    