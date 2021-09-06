# HyperText Markup Language (HTML) codeerstandaarden en naamgevingsconventies

## 1. Gebruik kleine letters voor de naamgeving van elementen en attributen hun naam of value.
```html
<!--correct-->
<p class="nice">This looks nice and neat</p>

<!--fout-->
<P CLASS="WHOA-THERE">Why is my markup shouting?</P>
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid doordat het niet schreeuwerig overkomt. Bovendien kan je sneller typen wanneer je het gebruik van hoofdletters vermijdt.

## 2. Attributen hun values wordt altijd tussen `" "` geplaatst.
```html
<!--correct-->
<img src="images/logo.jpg" alt="A circular globe icon" class="no-border">

<!--fout-->
<img src=images/logo.jpg alt=A circular globe icon class=no-border>
```
> **Waarom?**
>
> In HTML5 is het gebruik van deze quotes niet verplicht, maar op deze manier vermijd je problemen wanneer values spaties bevatten (zoals in het voorbeeld hierboven).

## 3. Gebruik dubbele quotes in plaats van single quotes.
```html
<!--correct-->
<p class="important">Yes</p>

<!--fout-->
<p class='important'>Nope</p>
```

## 4. Gebruik betekenisvolle `class` of `id` namen die bij voorkeur in kebab-case genoteerd worden.
```html
<!--correct-->
<p class="editorial-summary">...</p>

<!--fout-->
<p class="bigRedBox">Blah blah blah</p>
```
> **Waarom?**
>
> Dit is in lijn met de Mozilla Developer Network's (MDN) documentatie en verhoogt de leesbaarheid.


# Referenties
* https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Code_guidelines/HTML#Class_and_ID_names