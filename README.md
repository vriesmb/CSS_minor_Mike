# Sanne heeft gezegd dat responsive huidige methode okey is voor mij, ik snap het principe maar kon niet meer ombouwen door hergebruik van elementen. Volgende project gewoon: klein beginnnen en hoe groter je gaat min-width gebruiken op @media.

# Bronnnen Note: Ik kan heleaas, naja positief eigenlijk, geen linkjes geven. Want heb die niet gebruikt. Kan wel zeggen dat ik veel gesproken heb met Roel, Nils en Sanne + MDN uiteraard. Maar code overnemen, hergebruiken of iets dergelijks afkomstig van een ander.. nope.

# CSS Technieken

## Geleerd
- [x] @Property custom properties
      Gebruikt op o.a. anlges/degrees, kleuren, gradients/percentages, groottes/blurs/lengths en font-weights.
      Voorheen onwennig, maar nu gebruik ik het alsof het de olie van mijn code is. 'Overal' stop ik ze waar mogelijk (en waar logisch is) om mijn workflow te verbeteren, flexibiliteit toe te voegen en de mogelijkheid te creeeren om te animeren.
- [x] @Container style queries (met custom properties)
      Super fijn om mee te werken. Scheelt je (JS) code, ontzettend bruikbaar, efficient en goed leesbaar.
- [x] @Keyframes (meer gewenning en eerder de keuze om te animeren, normaal deed ik dit amper, nu ik custom properties ken ging/gaat er een wereld voor me open)
- [x] Animate play state - wist ook niet dat dit bestond. Als je het eenmaal door hebt goed te gebruiken. Je moet goed nadenken over de default state. anders kun je dagen vastlopen op het feit dat hij niet precies doet wat jij wilt omdat je ergens een state mist of onjuist hebt.
- [x] :has selector (ook in combinatie met [value=""]) is iets waar ik niet eens het bestaan van af wist. Nu gebruik ik het met gemak en veel plezier, normaal zou ik hier JS voor inschakelen nu is dat niet meer nodig.
- [x] Transform 3D minimaal. Ik had hier graag meer van willen doen, maar enkel mee ge-expirimenteerd en door andere prioriteiten en bugs en technieken geen tijd voor gehad diep in te duiken en daadwerkelijk echt te gaan gebruiken voor grotere dingen.
- [x] transform-origin : voor soort anchor point plaatsing. kan hem vervolgens om zijn as draaien, mits de parent relative is.
- [x] Gebruik maken van &after en &before, heb ik eerder nooit echt gebruikt. 
      Begreep het nooit en nu vind ik het logisch en goed bruikbaar.
- [x] CSS Nesting 
      Echt top. Wist voorheen niet dat dit mogelijk is. Prettig voor overzicht en werkt fijn.
- [x] Experimenteren met nieuwe code, itereren en soms delen die wel lukken te gebruiken, maar ook door te ontwikkelen totdat iets werkt zoals je wilt. Klink cliché, maar ben me echt telkens gaan verdiepen in de technieken en heb ontzettend veel workshops meegedaan en ben graag met de docenten gaan zitten om het uit te pluisen.. ook omdat ik het heel graag goed wilde doen om de technieken onder de knie te krijgen.
- [x] Clamp, in tekst grootte - voor responsiveness

## Had nog willen doen
- [ ] (Custm)sliders met values en steps en die waarde dan gebruiken bij een ander element als waarde-input  
      Wél workshop voor gevolgd en meegedaan, geen tijd voor implementatie, door nette code en netjes willen uitvoeren van huidige functionaliteit(en).
- [ ] Extra interacties/knoppen op control panel en op de achtergrond wat effecten, maar heb zo de focus gelegd op het JUIST leren en begrjpen van mijn huidige code en functionaliteiten dat ik daar niet aan toe gekomen ben. Was het me eerlijkgezegd ook niet waard. Voorheen deed ik dat altijd wel, zo veel mogelijk maken. Maar ben blij dat ik het op de huidige manier heb aangepakt. Ik heb veel kwalitatieve dingen geleerd en ben super trots op de progressie.


# Conceptuitwerking

CD Speler met een herkenbaar uiterlijk.
Ik wil track id kunnen displayen op een originele manier.
Er moeten buttons komen waar je echt de diepte van ziet als je ze indrukt.
Ze moeten affordance hebben. Moet er herkenbaar uitzien als een knop en de states moeten dat ook zijn.
Bij het klikken en terugspringen van de knop moet het er mechanisch uitzien.

## Conceptuitwerking
Dus de punten van uiterlijk zijn:
- Knoppen krijgen diepte, bij indrukken.
- Knoppen krijgen een herkenbare beweging bij het indrukken en terugspringen.
- Player krijgt een herkenbaar uiterlijk & affordance

De player kan gestart worden, gestopt worden, maar ook opnemen. Alle 3 de inputs krijgen andere details.
Ook moet je tijdens het spelen kunnen opnemen zonder dat er iets verspringd. Ook moet het andersom werken: als je opneemt gaat hij meteen spelen.


# Opgeslagen experimenten
"Dit zijn tegelijkertijd ook mijn eigen notes, waar ik mezelf uitleg hoe het werkt"

![Setup](/images/1.1.png)
> Eerste :has gebruik in mijn project. 
Dit experiment is het gevolg van een mislukt experiment met SVG FIlters. Ik wilde namelij 3 knoppen met geborsteld metaal als uiterlijk. Ik heb hier lang naar zitten zoeken. Ik kreeg het voor elkaar om een knop te krijgen met een SVG met wat noise toegevoegd. Maar de genoisde achtergrond zag er niet uit als beborsteld metaal. Vandaar dat ik ben gaan kijken naar gradients combineren, maar dit gaf veel overlappen en gaf me niet de strakke structuur die ik zocht. Uiteindelijk ben ik gegaan voor een background image die de texture heeft, waar ik bovenop wat gradients stapel + een 3d transform + een background image scale zodat het er allemaal samen uitziet 'alsof' hijecht ingedrukt wordt. Daarnaast springt hij sneller terug, dan dat hij wordt ingedrukt (ook zoals in het echt - dat 'mechanische').

![Setup](/images/1.2.png)
D.m.v. de :has i.c.m. de value en :checked state kan ik zien welke 'input' is ingedrukt.. zodat ik een status kan meegeven. Later in de code kan ik dan deze status gebruiken als conditie op styling van meerdere elementen.

![Setup](/images/1.3.png)
Hier zie je dat mijn style queries worden toegepast a.d.h.v. de 'pressure' status.

![Setup](/images/1.4.png)
Hier maak ik mijn eerste @properties ooit aan.
Ik had geleerd van Sanne dat er verschillende types zijn waar je de propertie mee kunt vullen. Je geeft een syntax mee zodat de waardes van properties straks geanimeerd/veranderd kunnen worden. Dat is ook wat ik doe. In dit voorbeeld heb ik de sytax op color gezet omdat de kleur van mijn gradient, van de button waarop je klikt, moet veranderen. Want als je simpelwel enkel een gradient zou gaan toevoegen dan ziet dat er niet smooth en custom uit. Vandaar dat de gradient er dus altijd al op zit, maar dat je de kleur en/of de percentages van de gradient aanpast.

![Setup](/images/1.5.png)
Hier zie je mijn gradient experiment. Ik wilde de 'shine' op een cd naabootsen met een bewegende lichtinval. Hier ging ik dus de percentages van de color punten aanpassen.

![Setup](/images/2.png)
Met dit als resultaat.
Ik ben hier later weer vanaf gestapt en heb gekozen voor een custom cd design met paths voor de kringen van de CD en een 'static' shine, die wel ronddraait.

![Setup](/images/3.png)
Deze foto nog even tussendoor. Ik heb lang vastgelopen bij de gradients stapelen. Volgorde maakt echt uit. Bij mij gingen de gradient door elkaar heen en de een maakte de anders transparant. Dus uiteindelijk de fix gevonden door ze om te draaien. Commented graddient area was het eerst (de foutieve versie).

![Setup](/images/4.png)
Hier begint mij speler al enigszins vorm te krijgen.
Ik ben later tekst gaan toevoegen in de speler. Ik had de gedachte (zoals in mijn videobewerkings-software) om een anchor punt in te stellen zodat een element om een zelf gespicificeerde as heen kan draaien.
En toen kwam ik op transform origin. En in dat voorbeeld op MDN visualiseerde ze de box met een anchor punt. Zo wist ik zeker dat het mogelijk was. Nou, weer keframes maken, custom propertie creeeren.

![Setup](/images/4.2.png) Link afbeelding bron
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin


![Setup](/images/4.1.png)
Hier zie je de code voor 1 woord bij first of type. later heb ik een tweede toegevoegd en dus last of type gebruikt, met precies het tegenovergesteld principe op de origin, zodat ze tegenover elkaar zouden staan en samen konden roteren om de gewenste as op het middelpunt v/d CD.

![Setup](/images/5.1.png)
![Setup](/images/5.2.png)
Uiteindelijk had ik een beetje spijt dat ik geen 3D had gebruikt verder en daarom wilde ik mijn tekst gaan doen. Echter zag dit er gewoon echt niet uit! 

![Setup](/images/5.3.png)
![Setup](/images/5.4.png)

Ik ben uiteindelijk gegaan voor een blur en font-weight variable effect. Als de weight dunner wordt ziet hij er verder weg uit (zeker als ik blur toevoeg) en andersom ook.. als de weight dikker wordt ziet hij er dichterbij uit (helemaal als ik de blur er dan af haal). Samen geeft het het effect van een soort camera uit die tijd (van de CD walkman) dat beelden scherp moesten stellen. OOkwel, een letterlijk diepte effect. Ook had je op veel stereo's dat cijfers en letter een soort stroom fade in fade out hadden in het UI. Dit effect boots je dan een beetje na via het diepte effect ook doordat de opacity naar 0 gaat.

![Setup](/images/7.1.png)
![Setup](/images/7.2.png)
Ook heb ik gedacht aan een responsive layout.
En heb ik gelet op de gradient dat hij de goede kant op staat, als de rotations van het device veranderd.

![Setup](/images/8.png)
Tot slot heb ik nog om wat meer op de details te zitten.. de record button meer feedback en styling gegeven. Nu komt de recording blink echt achter de knop vandaan en heeft een blur omdat het in het echt ook als een vrij helder lichtje zou ervaren. Daarnaast heeft de button zelf ook een gegraveerde stijl gekregen met brushed metal.

![Setup](/images/9.png)
Laaste detail. de grafering wat meer darkness. 
Nu zie je beter diepte.


# Detail uitwerkingen elementen

1. Record button blink op rode lichtje.
2. Text draait in cd
3. Cd styling met path ipv png
4. Gradient draait met custom propertie en keyframes
5. heading + p element zijn geanimeerd. P op cd als een soort laser tekst en heading als een semi-digitaal fade in en out tekstje. 
6. 3 buttons zijn klikbaar en hebben feedback en feedforward. hebben een diepte effect door stapeling gradient en diepte 3d. door hele subtiele box shadows krijg je echt een soort knop omlijning en scheiden tussen elkaar. timing en snelheid spelen ook grote rol. ze worde normaal ingedrukt en springen als het waren snel terug naar hun startpositie als een andere knop ingedrukt wordt.
7. tekst op cd draait perfect rond door juist origin points. 


# Rauwe schets van idee
![Setup](/images/rauwe_schets_idee.jpg)

# Eerste knoppen ontwerp hahah
![Setup](/images/4maart.png)


# Persoonlijke Notes van gesprekken & les

### CSS & Feedback van Sanne

1. Animaties & Transities
   • Transitie heen: Duurt 10.000 seconden.
   • Terug: Start pas na een actie, maar duurt ook 10.000 seconden.
   • Workshop? Mogelijk een korte uitleg hierover.

2. Achtergrond & 3D Effecten
   • Achtergrond moet reageren op gebeurtenissen.
   • Kan er iets met mischief in 3D draaien?

3. README & Documentatie
   • Concept & gebruikte CSS-technieken toevoegen.
   • Update README: Spannender en duidelijker maken.

4. Geluid & Beeld
   • Geluid werkt niet → probleem oplossen.
   • Beeld kan beter of duidelijker.

5. Carousel met Filmakeuze
   • Keuzes in een carousel met radio buttons.
   • Scrollen & klikken bepaalt de waarde van de video.

6. Scroll-based Animaties
   • Voorbeelden:
   • Apparaat draait mee met scroll (CSS transform: rotate() etc.).
   • Gebruik :has() voor extra effecten.
   • Belangrijk:
   • Animaties moeten zinvol/logisch zijn.
   • Mag nutteloos zijn, maar denk na over “de onzin” (zoals Sanne zei).
   • Idee: een apparaat dat kleiner wordt als “gekke animatie”.

7. Workshop op 4 Maart
   • Thema: CSS
   • Inspiratiebronnen:
   • temanin afif
   • css-articles.com

### Gesprek met Roel 3 maart

1. @property gebruiken om de kleur te kunnen animeren in de gradient zodat je de button feedback kan geven.

   @property --dark-color {
   syntax: "<color>";
   inherits: true;
   initial-value: rgb(120, 120, 120);
   }

   @property --light-color {
   syntax: "<color>";
   inherits: true;
   initial-value: rgb(154, 154, 154);
   }

### intro les Sanne 4 maart

    css nesting
    button{
        :active …
        > span

}

@property —hue
syntax number
inserts true
initial value 0

@keyframes color (animeren met hue, door custom propertie)

0%
—hue: 0;

100%
—hue 180

### Workshop has: ROEL

h1 + h2 als een h1 wordt opgevolgd door een h2
doe dan het volgende

section:has(h1 + h2) h1{
marign-bottom: 50px;
color: lime;
}

bij een aantal li's doe dan het volgende
ul:has(li:nth-child(15)) li {
....
}

bij een aantal li's (maar enkel als laatste) doe dan het volgende
ul:has(li:nth-child(15):last-of-typ) li {
..
}

input:checked
kan ook standaard gehiden elementen te voorschijn halen

bij een <button> ook type="button" gebruiken anders kans op submit state en refresh pagina. bij <input> een type="name" en een type="

### Workshop 3d Sanne

anmiation 2s infinite linear pase;
animation-play-sate: running;

transform-style:preserve-3d;
op parent dan doet hij niet alsof hij 3d maar dan maakt css een 3d omgeving.

    --n: 12; voor aantal stuks.

    perspective 50em hoe groter hoe verder weg je staat
    kleiner maken voor groter effect ook scaling in midden

### 4 Maart in les

button click en gradient change.
principe animatie samen bedacht met Roel,
later heeft Sanne me geleerd en geholpen om de fadeout animatie te laten werken. We hebben de code in principe 'versimpeld' en transiton gebruikt. transition all geeft een transition op alle gewenste elementen
en daarnaast ook de custom propertie transitionen met 0.2s --pressure-color

### 10 Maart in les

- Nils Binder

wrapper max width.
Wrapper centered in the website.

.warpper{
width: min(100% - 3rem, 75rem);
margin-inline: auto;
}

3rem —wrapper-max var
custom property

padding 1.5 rem
var(2x —padding)

ipv

..wrapper{
max-width: 75rem;
margin 0 auto
padding 0 1.5rem
}

ultra wide sizing met wrapper

minmax(0, clamp (24rem, 75%, 44rem));
desired is the middel one, but at least 24rem and maximum 44rem

- Sanne
  heeft me style queries geleerd.
  ik heb values meegegeven en deze gebruik ik om dan de styling toe te passen op de juiste elementen zonder lange selectoren te gebruiken

bijv. @container style(--pressureRecord:true)

### Notes 14 Maart Sanne

svg filter heading squiggly?

gradient effects op toets als je indrukt aan zijkant

responsive design

@layer basis laag fonts colors

@layer module, state;
state is belangrijker dan module

zelf verzonnen termen achterste wint

— zelf bedacht met streepjes ervoor

keer oefenen niet nodig

button extra laag erover met kleine transparantie voor diepte effect tvanicoon . heel dun 10% zichtbaar

@property --a {
syntax: '<angle>';
inherits: false;
initial-value: 10deg;
}

angel voor type, dan kan ik degrees aanpassen van cd shine

https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas

voor layout responsive
