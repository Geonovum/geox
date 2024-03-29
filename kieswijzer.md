# Keuzehulp bestandsformaten

Stel, je bent een overheidsorganisatie, en je bezit geo-data die je wilt publiceren als open data, of die je wilt uitwisselen met andere partijen. Welk formaat moet je dan kiezen? Vroeger was het antwoord van Geonovum altijd: "GML". Maar tegenwoordig zijn er meerdere formaten waaruit je kunt kiezen.

Bij de keuze voor het juiste uitwisselformaat speelt de beoogde toepassing, of toepassingen, een belangrijke rol. Wat willen gebruikers ermee: willen ze de data kunnen visualiseren in een webapplicatie, of gaan ze de data bijvoordbeeld gebruiken voor GIS analyses? Wordt de data gepubliceerd op het web, of rechtstreeks uitgewisseld tussen systemen waarbij validatie van toepassing is? 

Aspecten van de geometrische data zelf spelen ook een rol bij de keuze voor een formaat. Is 3D data nodig? Is nauwkeurigheid van belang? Worden complexe geometrietypes gebruikt? 
Daarnaast is het belangrijk om te kijken naar de voorkeuren, behoeftes en de tools die gebruikt worden door afnemers - ondersteunen deze de formaten ook? Er is niet één enkel uitwisselformaat voor geometrische data dat het antwoord op alles is. Dit betekent dat de beste oplossing kan variëren, en afhankelijk is van overwegingen die de data-eigenaar zal moeten maken. 

De belangrijkste aspecten, die invloed kunnen hebben op de keuze voor een format, lichten we hieronder kort toe. Na deze toelichting vatten we de aspecten samen en brengen ze met elkaar in verband. 

## Aspecten die een rol spelen bij de keuze

### Aanleveren versus uitleveren van data
Bij het kiezen van het juiste formaat, maakt het veel verschil of de data wordt uitgewisseld tussen softwaresystemen in een keten, bijvoorbeeld bij het aanleveren aan een landelijke voorziening voor data; of dat de data wordt aangeboden aan gebruikers. In een keten heb je altijd te maken met bekende gebruikers, en vaste afspraken die binnen de keten voor gegevensuitwisseling zijn gemaakt. Een partij die binnen een keten acteert heeft doorgaans een langdurig belang en zal dus meer bereid zijn tot het doen van een investering in tijd en/of geld om de data te kunnen uitwisselen. Het kan dan gerechtvaardigd zijn om een wat moeilijker te hanteren formaat te kiezen, als dat opweegt tegen voordelen die dat specifieke formaat heeft. Bij het aanbieden van data aan gebruikers, vaak als open data, is dit veel minder het geval. Datagebruikers hebben vaak beperkt tijd om met een bestand aan de slag te gaan. 

### Bekende versus onbekende gebruiker
Bij het aanleveren van data aan een landelijke voorziening heb je per definitie een bekende gebruiker: er zijn afspraken tussen verzender en ontvanger van de data. Bij het uitleveren van data is dit niet per definitie het geval. Er kan sprake zijn van bekende gebruikers: partijen die bijvoorbeeld een abonnement op de data hebben of waarvan bekend is dat ze de data afnemen. Maar het kan ook zijn dat de data voor iedereen beschikbaar is zonder verder contact met de data aanbieder. In dat geval kunnen er gebruikers zijn met allerlei verschillende kennisniveau's, applicaties en behoeftes. Denk hierbij bijvoorbeeld aan web developers (applicatiebouwers), data scientists en data journalisten. Om breed gebruik van data te bevorderen is het dan verstandig om de data zo laagdrempelig mogelijk aan te bieden, dus in algemeen gangbare dataformaten waarvoor brede ondersteuning in tooling bestaat.

### GIS-gebruikers of andere gebruikers
Nog een aspect dat met gebruikers te maken heeft, is de vraag of het om GIS gebruikers gaat. De huidige GIS systemen kunnen niet alle lichte formaten, die we in deze handreiking beschrijven, aan. Als (een deel van) het publiek van de gepubliceerde data wel de behoefte heeft om data in een GIS in te lezen, om bijvoorbeeld ruimtelijke analyses te kunnen doen, moet hier rekening mee gehouden worden. 

### Archivering versus direct gebruik
Bij archivering is een belangrijk basisconcept dat vorm, inhoud en structuur van archiefbescheiden behouden moeten blijven of tenminste reproduceerbaar zijn. Voor data die gearchiveerd moeten worden zijn daarom afwegingen zoals langdurige ondersteuning, gedocumenteerde standaarden en open formaten van extra belang. Mogelijk moet er ook voldaan worden aan de Archiefwet.

### Ondersteuning in algemene tooling
Als het gaat om de aanleverkant in een keten, is er meestal specifieke ondersteuning voor het gekozen uitwisselformaat in de keten geïmplementeerd. Soms kan er echter toch behoefte zijn aan ondersteuning in tooling, die niet onderdeel van de keten is maar wel toegevoegde waarde heeft in het werkproces van de zender of de ontvanger van de data. 

### Validatie
Validatie, het controleren van de datastructuur en -inhoud tegen vooraf afgesproken regels, is vooral belangrijk bij het direct uitwisselen tussen systemen, bijvoorbeeld aan de aanleverkant van landelijke datavoorzieningen of bij het leveren van data van een uitvoerder aan een opdrachtgever. Men wil immers de kwaliteit borgen van de aangeleverde data, en zorgen dat alleen correcte data wordt ingelezen in het ontvangende systeem. Maar er zijn ook andere situaties denkbaar waarin validatie belangrijk is. 

Validatie kan zich richten op verschillende aspecten:
- Validatie van een vooraf afgesproken datastructuur (dat meestal is vastgelegd in een informatiemodel)
- Validatie van business rules (regels over de inhoud en afhankelijkheden tussen onderdelen van de data)
- Validatie van geometrieën 

Al deze validatie-aspecten worden in wisselende mate ondersteund door de verschillende formaten. Als je een dataset wilt valideren kun je dit altijd uitprogrammeren, maar vaak biedt het voordelen om zonder programmeerwerk te kunnen valideren. Dit is bijvoorbeeld bij op XML gebaseerde formaten mogelijk omdat het uitdrukken van dataschema's een goed geïmplementeerd onderdeel van de standaard is. 

### Uitleveren van schema's
In sommige situaties is het gewenst om de afspraken over datastructuur en -inhoud (ook wel: *schema's*) vast te leggen in machine-leesbare vorm en dit machine-leesbare schema te delen met de ontvangers van data. Dit is niet bij alle lichte formaten mogelijk. 

### Nauwkeurige data
Als er sprake is van nauwkeurige geometrische data, kan dit gevolgen hebben voor de formaatkeuze. Dit hangt samen met coördinaatreferentiesystemen. Sommige formaten ondersteunen alleen het WGS-84 coördinaatstelsel, waarmee het niet mogelijk is om coördinaten in Nederland net zo nauwkeurig uit te drukken als bijvoorbeeld in het Rijksdriehoekstelsel. 

<aside class="note">De data aanbieder zou goed moeten nadenken of het ook nodig is om de data zo nauwkeurig als mogelijk te publiceren. Dit hangt af van de gebruikersbehoefte. Ontwikkelaars die met de data in web viewers aan de slag gaan, werken over het algemeen met Web Mercator (een projectie van WGS84). Bezoekers van hun websites willen bijvoorbeeld weten 'of er een pinautomaat in de buurt is' en hebben daarbij geen last van een afwijking van een paar meter. Niet-geo-experts weten vaak niet eens dat er verschillende coördinaatreferentiesystemen zijn en waarom. Voor de meeste use cases hebben zij deze kennis - en nauwkeurige geodata - ook niet nodig.</aside>

### Simpele geometrie
GIS standaarden en (in mindere mate) -tooling ondersteunen niet alleen rechttoe rechtaan 0, 1 of 2 dimensionale geometrie in de vorm van punten, lijnen en vlakken maar soms ook exotischere vormen zoals kromme lijnen (splines, cirkels, bogen, ellipses), driehoeken, 3D volumes, etc. In Nederland hanteren we het Simple Feature profiel plus een eenvoudige vorm van bogen, (zie [[gimeg]] hoofdstuk 3), maar ondersteuning van andere kromme lijnen en 3D volumes is voor sommige use cases wel nodig. In lichte formaten is over het algemeen beperkte ondersteuning: soms alleen punten, soms ook lijnen en vlakken, en in een enkel geval ook bogen en/of volumes. 

### Bogen en volumes
Als de toepassing het nodig maakt om bogen en/of 3D volumes in de data uit te wisselen, moet er extra gelet worden op ondersteuning hiervoor bij de keuze van het uitwisselformaat. 

<aside class="note">Bij de ondersteuning van 3D geometrie zijn er meerdere aspecten die aandacht vergen - en andere formaten die van toepassing zijn. Deze aspecten worden niet uitgewerkt in de handreiking, zoals vermeld in [de scope](#scope-en-doelgroep). Wel wordt een indicatie gegeven van de mogelijkheden wat betreft het representeren van 3D volumes (in de formaten die hier behandeld worden). </aside>

### Datavolume
Bij geodata kan men te maken hebben met grote datavolumes. Het woord "groot" is hierbij lastig te kwantificeren, en wat een groot bestand gevonden wordt kan ook veranderen in de loop der jaren. Maar een bestand van bijvoorbeeld 500MB of 1GB kan momenteel toch wel 'groot' genoemd worden en in de keuze van het meest geschikte uitwisselformaat speelt dit een rol.

<aside class="example">Een BGT GML bestand van één gemeente kan al gauw 1 of 2 GB groot zijn. Zie bijvoorbeeld het [voorbeeldbestand Amersfoort](https://www.geonovum.nl/uploads/documents/Amersfoort_GML_20132211.zip).</aside>

Het ene formaat is geschikter voor grote datavolumes dan het andere. Het tegenovergestelde geldt ook: sommige formaten hebben relatief veel overhead en zijn daarom minder geschikt voor het uitwisselen van een klein bestandje via een API. 

### Semantiek
Het vastleggen en uitwisselen van informatie over de betekenis (semantiek) van de data wordt in wisselende mate ondersteund door de verschillende formaten. Of het van belang is hangt af van de situatie; bij data uitwisseling tussen partijen die elkaar kennen speelt dit niet zo, omdat deze kennis bij de ontvanger op de een of andere manier al aanwezig is. Voor onbekende gebruikers is het vaak belangrijker om de betekenis te kunnen achterhalen. Afkortingen of jargon zijn voor hen lastig te doorgronden. Ook voor vindbaarheid in zoekmachines is semantiek belangrijk: zoekmachines nemen dit mee in hun indexering zodat zoektermen die gebruikers invoeren betekenisvolle resultaten opleveren.

### Gestructureerde semantiek
Informatie over de betekenis, ofwel semantiek, kan op verschillende manieren worden vastgelegd. Dit kan een simpel PDF document of excel bestand zijn, of een website met uitleg; er zijn ook machineleesbare formaten zoals RDFS, OWL en SKOS. In de meeste lichte formaten is er weinig of geen ondersteuning voor het gestructureerd vastleggen van semantiek.

### Samenvatting: de aspecten in samenhang
De hierboven uitgelegde aspecten zijn samen te vatten in de volgende vragen, waarbij ook de afhankelijkheden tussen de vragen zijn meegenomen:

<div id="keuze-vragen">
**1. Gaat het om het aanleveren van data (in ‘keten of tussen systemen), of het uitleveren van data aan eindgebruikers?**
- In geval van uitleveren:
-- 	**Is de gebruiker bekend of onbekend?** 
--		In geval van bekend:
--	-		**Gaat het om GISers of niet-geo developers?**

- In geval van aanleveren:
--	**Wordt de data (door de andere partij) gearchiveerd of direct gebruikt?**
--		In geval van direct gebruikt:
--	-		**Heeft de partij behoefte aan ondersteuning in algemenere tooling?**

**2. Is validatie erg belangrijk?**
- Zo ja:
--	**Is het belangrijk om schema’s te kunnen leveren aan partijen / gebruikers?**
--	**Is het belangrijk om out-of-the-box te kunnen valideren tegen het schema?**

**3. Is de nauwkeurigheid van de data belangrijk?**

**4. Welke geometriesoorten worden uitgewisseld – alleen simple features of ook andere ISO 19107 types?**
- In geval andere ISO 19107 types: 
--	**Zijn bogen of 3D geometrieën aanwezig?**

**5. Gaat het om grote of kleine datahoeveelheden?**

**6. Is semantiek belangrijk (gaat het om meer dan de uitwisseling van geometrieën)?**
- Zo ja:
--	**Moet de semantiek op gestructureerde wijze worden vastgelegd?**
</div>

Welk formaat, of welke formaten, de beste keuze zijn, hangt af van de antwoorden op deze vragen. Ze geven inzicht in welke aspecten een belangrijke rol spelen voor de beoogde toepassing. Met deze informatie kan de lezer de tabellen in hoofdstuk 4-8 nagaan, en op basis daarvan een afweging maken over welke formaten het beste aansluiten op de behoeften die uit de antwoorden naar voren zijn gekomen. 

Let wel op dat dit geen allesomvattende vragenlijst is. In een praktische situatie kunnen er zaken een rol spelen die niet in de vragenlijst zijn meegenomen. Maar met behulp van de vragenlijst krijgt de lezer in ieder geval een goede indicatie.

## Keuzehulp voor generieke toepassingen
Hoewel elke toepassing tot andere antwoorden kan leiden (en dus andere keuzes), zijn er een aantal generieke toepassingen waarvoor een specifiek uitwisselformaat het meest geschikt is. Om de lezer te helpen bieden we een visuele keuzehulp aan die voor een aantal generieke toepassingen laat zien welk uitwisselformaat daar het beste bij past, aan de hand van de daarbij relevante aspecten.

De generieke toepassingen zijn:

- Web pagina's waarop mensen informatie kunnen vinden over geo-objecten
- Kaarten of andere visualisaties van geodata die gepubliceerd worden op het web
- Data integratie - het combineren van geodata met andere data
- Ruimtelijke analyses - het ontdekken van betekenisvolle patronen in geodata
- Uitwisselen van geodata tussen systemen

<div style="position: relative;" >
  <img src="media/diagram-keuzehulp.png" style="width: 100%; height: auto;" /><a class="image-link" href="#html" title="HTML-keuze"><div style="position: absolute; left: 6.7%; top: 59%; width: 14%; height: 19%; background-color: transparent;" target="_self"></div></a><a class="image-link" href="#geojson" title="GeoJSON-keuze"><div style="position: absolute; left: 24%; top: 59%; width: 14%; height: 10%; background-color: transparent;"></div></a><a class="image-link" href="#rdf" title="RDF-keuze"><div style="position: absolute; left: 49%; top: 59%; width: 14%; height: 21%; background-color: transparent;"></div></a><a class="image-link" href="#geopackage" title="GeoPackage-keuze"><div style="position: absolute; left: 65%; top: 59%; width: 13.5%; height: 29%; background-color: transparent;"></div></a><a class="image-link" href="#gml" title="GML-keuze"><div style="position: absolute; left: 80%; top: 59%; width: 14%; height: 27%; background-color: transparent;"></div></a>  
</div>

<!-- <aside class="note">
Om de lezer te helpen willen we het mogelijk maken om de vragenlijst in te vullen en, gebaseerd op het resultaat, een bepaalde view op de tabellen in hoofdstuk 4-8 te activeren. Hiermee zou lezer in een oogopslag kunnen zien wat de voordelen en nadelen zijn van elke encoding, gericht op de toepassing(en).  Wanneer de lezer op een van de generieke toepassingen in het diagram klikt is de view op de generieke toepassing gebaseerd. </aside> -->
