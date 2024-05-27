# Afspraken voor een goede git commit message
Gelukkig voor ons zijn er al enkele afspraken gemaakt omtrent verschillende zaken. We gaan zelf niets uitvinden, maar door gebruik te maken van onderstaande acht afspraken zullen we meer consistentie in onze git commits kunnen brengen.

## 1	Maak je commit message in het Engels
Aangezien Engels de voertaal is in het programmeren zullen ook wij afspreken om onze commit messages in het Engels te schrijven.
 
## 2	Beperk de titel tot 50 karakters
Dit is geen harde limiet, maar eerder een vuistregel. De harde limiet bedraagt 72 karakters.
Hierdoor worden je commits leesbaarder voor je collega’s maar dien je wel even na te denken over je titel om duidelijk te maken wat er gebeurd in je commit.

> **TIP**
>
> Indien je te hard moet nadenken over een goeie titel heb je misschien teveel wijzigingen in je code aangebracht per commit. Het is dan verstandiger om kleine wijzigingen te committen.

Ook de UI van GitHub volgt deze afspraken en geeft je een waarschuwing wanneer je over de 50 karakters gaat:  

![Git](/images/git-02.png)

Als je titel langer is dan 72 karakters zal deze afgekapt worden in de UI. Probeer dus te mikken op 50 karakters voor je titel: 
![Git](/images/git-03.png)

Wanneer we gebruik maken van de commando’s `git log`,  `git log --oneline` of `git shortlog` geeft ons dit een mooi overzicht.

## 3	Begin de titel met een hoofdletter
Misschien wel de meest simpele afspraak: begin elke titel met een hoofdletter. 

## 4	Eindig de titel niet met een punt of ander leesteken
Nog een simpele afspraak dus. Zeker wanneer je moet mikken op 50 karakters voor je titel telt elk teken mee.

## 5	Gebruik gebiedende wijs in je titel
Schrijf of zeg zoals je een commando of een instructie zou geven aan iemand.
Bijvoorbeeld:
- Ruim je kamer op
- Sluit de deur
- Zet de vuilniszakken buiten

Alle afspraken die we hier noteren zijn ook in de gebiedende wijs geschreven. Misschien klinkt de gebiedende wijs af en toe wat grof of onbeleefd, want meestal spreken we niet in deze vorm tegen elkaar. Deze vorm is echter perfect voor git comment titels. En niemand zal zich beledigd voelen als iedereen weet dat dit een afspraak is.

Ook Git zelf gebruikt de gebiedende wijs, bijvoorbeeld:

`$ Merge branch “myFeature”`

Om verwarring te vermijden kan je volgende regel toepassen:

- If applied, this commit will *plaats de titel hier*

Bijvoorbeeld:
- If applied, this commit will <span style="color:green">***Refactor subsystem X for readability***</span>
- If applied, this commit will <span style="color:green">***Update getting started documentation***</span>
- If applied, this commit will <span style="color:green">***Remove deprecated methods***</span>
- If applied, this commit will <span style="color:green">***Release version 1.0.0***</span>
- If applied, this commit will <span style="color:green">***Merge pull request #123 from user/branch***</span>

Zie hoe dit niet werkt in de niet-gebiedende wijze:
- If applied, this commit will <span style="color:red">~~***Fixed bug with Y***~~</span>
- If applied, this commit will <span style="color:red">~~***Changing behavior of X***~~</span>
- If applied, this commit will <span style="color:red">~~***More fixes for broken stuff***~~</span>
- If applied, this commit will <span style="color:red">~~***Sweet new API methods***~~</span>

Deze gebiedende wijs gebruiken we enkel in de titel, niet in de body.

# Afspraken indien je ook gebruik maakt van de body
## 1	Onderscheid tussen titel en body
Maak gebruik van een duidelijke titel in je commit. Hoewel dit niet verplicht is, wordt het toch sterk aangeraden een beschrijvende body toe te voegen. Het onderscheid tussen de titel en de body maken we door tussen beide een lege tekstregel te plaatsen.

Verschillende Git platformen zullen alle tekst tot aan de lege tekstregel aanzien als een titel. In de body kan je dan wat meer duiding geven door een grondigere beschrijving te maken.

Uitzonderingen zijn er altijd, bijvoorbeeld: *“Fix typo in introduction to user guide”*. 
Deze commit zegt al meer dan voldoende; we hebben een typfout opgelost in de gebruikershandleiding. Hierdoor hoeven we geen titel en body te gebruiken om (nog) meer duiding te geven.

Opgepast! Indien je commits doet via Git Bash kun je een titel en body of enkel een titel. Bijvoorbeeld enkel een titel:

`$ git commit -m "Fix typo in introduction to user guide"`

Soms is het beter om toch een body mee te geven om meer duiding te geven. 
Bijvoorbeeld:
`
Remove portal to the underworld

Apply primal spells, rephrase incantations because the spawn was too powerfull
Close #666`

We kunnen dit op twee manieren doen in Bash:
- Git commit zonder flags: `$ git commit`

Hierdoor zal VS Code (of een andere ingestelde editor openen) waarin je uw commit kan schrijven. Dit commit wordt uitgevoerd nadat je de editor sluit.

- Git commit met titel en body: `$ git commit -m "Titel" -m "Body"`

We kunnen dit ook doen via de Git tools die ingebouwd zijn in Visual Code en/of Visual Studio.
![Git](/images/git-01.png)
## 2	Wrap de body op 72 karakters
Git zal de tekst nooit automatisch gaan “wrappen”. Je moet hier dus zelf rekening mee houden en je tekst manueel gaan wrappen.

Het wordt aanbevolen om dit te doen op 72 karakters, zodat Git nog ruimte genoeg heeft om tekst te laten inspringen en alles onder de 80 karakters te houden.
Een teksteditor zoals VS Code kan hier zeker bij helpen. Onderaan deze applicatie kan je aflezen op welke regel je zit en op welke kolom (het aantal karakters dus)

## 3	Gebruik de body om WAT en WAAROM uit te leggen, niet HOE
Leg in je body uit **WAT en WAAROM** je iets hebt aangepast. Maar leg niet uit **HOE** je iets hebt aangepast. Indien men wil weten hoe je iets hebt aangepast kan men in de code van deze commit gaan kijken.
