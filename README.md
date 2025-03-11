# CSS Technieken

- [x] :has()
- [ ] Style (container queries)

  > /_ styling .card based on the value of --theme on .card-container _/
  > @container style(--theme: warm) {
  > .card {
  > background-color: wheat;
  > border-color: brown;
  > ...
  > }
  > }

- [x] Custom Properties
- [x] 3D Transforms

# Conceptuitwerking

Video/Audio player met customizable visualiser op de achtergrond.

Ik wil met het uiterlijk van de player op detail ingaan.

- Knoppen krijgen diepte, bij indrukken.
- Knoppen krijgen een herkenbare beweging bij het indrukken en terugspringen.
- Player krijgt een herkenbaar uiterlijk & affordance

De player kan gestart worden, gestopt worden, maar ook opnemen. Alle 3 de inputs krijgen andere details.

Mocht ik tijd hebben wil ik de achtergrond customizable maken met sliders.

# Notes

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
