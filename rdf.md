## RDF

### Introductie
<p class='note'>Over geometrie in RDF hebben we eigenlijk nog helemaal geen tekst maar wel wat inzichten die we zouden kunnen opschrijven. Toevoegen van een hfd over RDF maakt deze handreiking compleet. </p>

RDF wordt steeds meer gebruikt als uitwissel- en publicatiemechanisme voor geo-informatie op basis van Linked Data. De afkorting RDF [[rdf11-concepts]] staat voor Resource Description Framework en is een standaard voor het representeren van informatie op het web als linked data, zodanig dat deze beschikbaar gemaakt kunnen worden in machineleesbare vorm op het web, niet als download maar als web pagina's, en daardoor ook beter bruikbaar zijn over sectorale grenzen heen. De data kunnen worden hergebruikt bij de bron door ze te koppelen via persistente URI’s. Er zijn meerdere technische RDF encodings zoals bijvoorbeeld RDF-XML [[rdf-syntax-grammar]] en [[turtle]]. 
[todo misschien nog aanvullen met basic linked data uitleg]

Hoe  geometrie in RDF moet worden uitgedrukt is beschreven in de OGC GeoSPARQL standaard, die een kleine vocabulaire voor geo-objecten en geometrie bevat. Deze geometrie kan op twee manieren worden worden geserialiseerd:
- Als WKT waarbij de Simple Feature geometrietypen uit ISO 19125 gebruikt kunnen worden (daardoor beperkt: geen 3D, geen bogen etc);
- Als GML waarbij de ISO 19107 geometrietypen gebruikt kunnen worden. 

[TODO voorbeeld opnemen]

### Voordelen

- data integratie: Gebruik van RDF voor het publiceren van gestructureerde gegevens op het web maakt het mogelijk dat data over de grenzen van sectoren heen gekoppeld en geïntegreerd worden.
- verschillende CRS mogelijk
- 3D mogelijk
- semantisch rijke data, integreren van vocabulaires

### Beperkingen
- GIS systemen ondersteunen (nog) geen RDF

### Afspraken
- nen3610-linkeddata > Het Linked Data profiel op NEN 3610 beschrijft hoe een linked data model van een NEN 3610 conform informatiemodel kan worden afgeleid.
- Voor het uitdrukken van geometrie in RDF verbinden we het NEN 3610 model met de OGC GeoSPARQL Linked Data vocabulaire. 
- De URI strategie