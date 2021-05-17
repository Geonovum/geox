# HTML
## Introductie
HTML is een specificatie van het W3C [[html5]] om gegevens gestructureerd aan te bieden, voor ontsluiting op het web. HTML is vooral bekend als de standaard voor webpagina's. Zoekmachines kunnen HTML goed indexeren.

Geodata in HTML kan op verschillende manieren gepubliceerd worden. Een HTML pagina van een geo-object zou de niet-geo eigenschappen kunnen tonen. Maar een HTML pagina kan ook de geometrie zelf bevatten en visualiseren.

HTML kent geen aparte elementen voor geometrie, maar de geometrie kan wel gestructureerd opgenomen  worden in een HTML pagina, door middel van een zogenaamde annotatie. Annotaties zijn vaak volgens het begrippenkader van Schema.org opgesteld. Slechts enkele eenvoudige geometrietypen worden gebruikt: punt, bounding box, cirkel, lijn, en polygoon. Het is ook mogelijk om een hoogtegetal op te nemen. De geometrie wordt meestal beschouwd als een vorm van metadata van de HTML pagina. Die wordt dan opgenomen met microdata, RDFa of stukjes JSON-LD en voor de gebruiker verborgen door een webbrowser, maar wel geïndexeerd door zoekmachines.

Met behulp van (gestandaardiseerde) webtechnologie als CSS, JavaScript, SVG / web canvas, kan geometrie gevisualiseerd worden via HTML pagina's. In steeds meer API's is er ook een HTML representatie van een geo-object. Zo is in de core van OGC API Features [[OAPIF]] [HTML een aanbevolen formaat](http://docs.opengeospatial.org/is/17-069r3/17-069r3.html#_requirements_class_html) voor representatie van geodata.

In HTML kunnen eenvoudig relaties gelegd worden met andere bronnen (webpagina's van gerelateerde geo-objecten bijvoorbeeld of verwijzingen naar definities) en andere begrippenkaders.

## Overwegingen

| Vraag                                                                              | Antwoord | Toelichting |
|------------------------------------------------------------------------------------|----------|-------------|
| Is het format geospecifiek?                                                        | <span id="kruisje">&#10005;</span> |             |
| Is het format gebaseerd op algemene ict standaarden?                               | <span id="vinkje">&#10003;</span>  |  Ja, HTML is de standaard voor Web pagina's.           |
| Wordt het format ondersteund in GIS software?                                      | <span id="kruisje">&#10005;</span> | Wanneer we het hebben over HTML voor de uitwisseling van data wordt een dataset (meestal) niet in één webpage gepubliceerd, maar krijgt elk object een eigen pagina. Dit betekent dat verwerking van meer dan één object in een ander systeem (bijvoorbeeld in een GIS of inlezen in een database), lastig is.|
| Ondersteunt het format het uitdrukken van schema's, en validatie tegen dat schema? | <span id="kruisje">&#10005;</span> |             |
| Ondersteunt het format meerdere coordinaatsystemen?                                | <span id="kruisje">&#10005;</span> | Nee, maar voor het gestructureerd opnemen van geometrie / CRSen kunnen annotaties gebruikt worden, deze worden gedefinieerd in een begrippenkader. [Schema.org](https://schema.org/) is een gangbare begrippenkader voor HTML annotaties, en ondersteunt alleen WGS-84. Het is niet de enige mogelijkheid, maar het voordeel van Schema.org annotaties is dat zoekmachines makkelijker met deze informatie overweg kunnen.   |
| Ondersteunt het format 3D?                                                         | <span id="kruisje">&#10005;</span> | Nee, maar voor het gestructureerd opnemen van geometrie / CRSen kunnen annotaties vanuit een begrippenkader gebruikt worden. [Schema.org](https://schema.org/) is een gangbare begrippenkader, alleen ondersteunt deze geen 3D. |
| Ondersteunt het format alle simple features geometrieen?                           | <span id="tilde">&#65374;</span>   | Nee, HTML ondersteunt geen geometrietypes vanzelf. Via een begrippenkader zou je een geometrie echter wel op gestructureerde wijze kunnen opnemen. [Schema.org](https://schema.org/) ondersteunt het gebruik van coördinaten (zie [GeoCoordinates](https://schema.org/GeoCoordinates)) en een beperkt aantal geometrietypen (zie [GeoShape](https://schema.org/GeoShape)).  |
| Ondersteunt het format andere ISO 19107 geometrie types?                           | <span id="kruisje">&#10005;</span> |             |
| Is het format geschikt voor grote volumes?                                         | <span id="kruisje">&#10005;</span> |             |
| Is het format geschikt om semantiek aan te koppelen / in uit te drukken?           | <span id="vinkje">&#10003;</span>  | Het is eenvoudig om gestructureerde data te combineren met tekst en en men kan linken aan begrippenkaders (zie [RDFa Primer](https://www.w3.org/TR/rdfa-primer/) voor meer informatie) |

<!-- ## Voordelen
- directe visualiatie / presentatie aan (eind)gebruikers van (object)informatie
- gestructureerde data in combinatie met tekst
- indexeerbaar door zoekmachines
- linken aan begrippenkaders -->

<!-- ## Beperkingen
- geometrietypen zeer beperkt
- ondersteuning voor andere CRSen dan WGS84 is niet gangbaar
- een volledige dataset downloaden, bijvoorbeeld om te combineren met een andere dataset, is lastiger
- verwerking van de geometrie in een ander systeem (zoals een GIS desktop systeem) is lastig -->

## Voorbeeld

<aside class="example ds-selector-tabs" title="Voorbeelden van geometrie voor HTML" style="overflow-x: hidden;">
<div class="container--tabs">
	De voorbeelden hieronder tonen representaties van geodata zoals je het in een HTML zou tegenkomen, volgens het RDFa format. Uiteraard is het ook mogelijk om andere formats toe te passen.
  <div class="selectors">
    <ul class="nav nav-tabs">
      <li class="tabs active"><a href="#html-geocoordinates">HTML - Voorbeeld 1 </a></li>
      <li class="tabs"><a href="#html-geoshapes">HTML - Voorbeeld 2</a></li>
    </ul>
    <div class="tab-content">
      <div id="html-geocoordinates" class="tab-pane active">
        Voorbeeld van een Schema.org GeoCoordinate instance zoals je het in een HTML zou kunnen verwerken (in RDFa)
        <pre>
		&lt;div xmlns="http://www.w3.org/1999/xhtml"
		  prefix="
		    : http://schema.org/
		    rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
		    rdfs: http://www.w3.org/2000/01/rdf-schema#"
		  >
		  &lt;div typeof=":Place" about="http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155">
		    &lt;div property=":description" content="Museum house where Anne Frank & her family hid from the Nazis in a secret annex, during WWII.">&lt;/div>
		    &lt;div property=":name" content="Anne Franks House">&lt;/div>
		    &lt;div rel=":address">
		      &lt;div typeof=":PostalAddress">
		        &lt;div property=":streetAddress" content="Prinsengracht 267">&lt;/div>
		        &lt;div property=":addressLocality" content="Amsterdam">&lt;/div>
		        &lt;div property=":postalCode" content="1016GV">&lt;/div>
		      &lt;/div>
		    &lt;/div>
		    &lt;div property=":url" content="http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155">&lt;/div>
		      &lt;div property="geo" typeof=":GeoCoordinates">
		        &lt;div property=":latitude" content="52.37520">&lt;/div>
		        &lt;div property=":longitude" content="4.88399">&lt;/div>
		      &lt;/div>
		  &lt;/div>
		&lt;/div>
		</pre>         
      </div>
      <div id="html-geoshapes" class="tab-pane">
      	Voorbeeld van een Schema.org GeoShape instance zoals je het in een HTML zou kunnen verwerken (in RDFa)
        <pre>
        	<textarea>
		<div xmlns="http://www.w3.org/1999/xhtml"
		  prefix="
		    : http://schema.org/
		    rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
		    rdfs: http://www.w3.org/2000/01/rdf-schema#"
		  >
		  <div typeof=":Place" about="http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155">
		    <div property=":description" content="Museum house where Anne Frank & her family hid from the Nazis in a secret annex, during WWII."></div>
		    <div rel=":address">
		      <div typeof=":PostalAddress">
		        <div property=":postalCode" content="1016GV"></div>
		        <div property=":streetAddress" content="Prinsengracht 267"></div>
		        <div property=":addressLocality" content="Amsterdam"></div>
		      </div>
		    </div>
		    <div rel=":geo">
		      <div typeof=":GeoShape">
		      	<div property=":polygon" content="52.375108,4.884235 52.375153,4.884276 
				                  52.375159,4.884257 52.375254,4.883981 
				                  52.375109,4.883850 52.375075,4.883819 
				                  52.374979,4.884104 52.374965,4.884143 
				                  52.375035,4.884207 52.375016,4.884263 
				                  52.374996,4.884320 52.374926,4.884255 
				                  52.374901,4.884329 52.375034,4.884451 
				                  52.375108,4.884235"></div>
		      </div>
		    </div>
		    <div property=":url" content="http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155"></div>
		    <div property=":name" content="Anne Frank's House"></div>
		  </div>
		</div>
		</textarea>
		</pre>
      </div>
    </div>
  </div>
</div>
</aside>

<!-- <aside class="example ds-selector-tabs" title="Voorbeelden van geometrie voor HTML" style="overflow-x: hidden;">
<div class="container--tabs">
  <div class="selectors">
    <ul class="nav nav-tabs">
      <li class="tabs active"><a href="#html-geocoordinates">HTML + Schema.org GeoCoordinates (in RDFa) </a></li>
      <li class="tabs"><a href="#html-geoshapes">HTML + Schema.org GeoShapes</a></li>
    </ul>
    <div class="tab-content">
      <div id="html-geocoordinates" class="tab-pane active">
        (*Bron: Spatial Data on the Web Best Practice, Best Practice 2: Make your spatial data indexable by search engines*)
        <pre title="">&lt;script type="application/ld+json">
		{
		  "@context" : {
		    "@vocab" : "http://schema.org/"
		  },
		  "@type" : "Place",
		  "@id" : "http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155",
		  "url" : "http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155",
		  "geo" : {
		    "@type" : "GeoCoordinates",
		    "longitude" : "4.88399",
		    "latitude" : "52.37520"
		  },
		  "name": "Anne Franks House",
		  "description": "Museum house where Anne Frank & her family hid from the Nazis in a secret annex, during WWII.",
		  "address" : {
		    "@type" : "PostalAddress",
		    "streetAddress" : "Prinsengracht 267",
		    "addressLocality" : "Amsterdam",
		    "postalCode" : "1016GV"
		  }
		}
		&lt;/script></pre>         
      </div>
      <div id="html-geoshapes" class="tab-pane">
        <pre title="">&lt;script type="application/ld+json">
		{
		  "@context" : {
		    "@vocab" : "http://schema.org/"
		  },
		    "@type" : "Place",
		  	"@id" : "http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155",
		  	"url" : "http://www.ldproxy.net/bag/inspireadressen/inspireadressen.3329155",
		    "name" : "Anne Frank's House",
		    "geo" : {
		      "@type": "GeoShape",
		      "polygon": "52.375108,4.884235 52.375153,4.884276 
		                  52.375159,4.884257 52.375254,4.883981 
		                  52.375109,4.883850 52.375075,4.883819 
		                  52.374979,4.884104 52.374965,4.884143 
		                  52.375035,4.884207 52.375016,4.884263 
		                  52.374996,4.884320 52.374926,4.884255 
		                  52.374901,4.884329 52.375034,4.884451 
		                  52.375108,4.884235"
		  },
		  "description": "Museum house where Anne Frank & her family hid from the Nazis in a secret annex, during WWII.",
		  "address" : {
		    "@type" : "PostalAddress",
		    "streetAddress" : "Prinsengracht 267",
		    "addressLocality" : "Amsterdam",
		    "postalCode" : "1016GV"
		  }		  
		}
		&lt;/script></pre>
      </div>
    </div>
  </div>
</div>
</aside> -->