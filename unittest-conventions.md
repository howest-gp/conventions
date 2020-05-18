# NAAMGEVING VAN JE UNIT TESTS

## Klasse
De testklasse krijgt de naam van de geteste klasse met suffix `Tests`.

## Testmethods
De naam van je unit tests moeten drie onderdelen bevatten:
- De naam van de methode die getest wordt
- Het scenario waaronder het getest wordt
- Het verwachte resultaat na het testen van het scenario

Het volgen van deze afspraken omtrent de naamgeving zijn belangrijk omdat zo onmiddellijk de intentie van de test duidelijk wordt.

# WAAROM?
Unit testing is meer dan alleen maar ervoor zorgen dat je code werkt, het voorziet ons ook van documentatie. Door de naamgeving van alle testen zou het duidelijk moeten worden wat het gedrag van de code is, zonder de code zelf te bekijken. Wanneer een test faalt kan men onmiddellijk zien welk scenario niet voldoet aan je verwachtingen.

# FOUTE NAAMGEVING
```csharp
[Fact]
public void Test_Single()
{
	// Code…
}
```
Bovenstaande naamgeving voor de test zegt weinig tot niks. Door middel van deze naamgeving is het totaal niet duidelijk wat er getest zal worden en wat het verwachte resultaat is.

# GOEIE NAAMGEVING
```csharp
[Fact]
public void Add_SingleNumber_ReturnsSameNumber()
{
	// Code…
}
```
Door middel van deze naamgeving is het onmiddellijk voor ons en anderen duidelijk wat deze test doet en wat we kunnen verwachten: we voegen een enkel nummer toe en verwachten hetzelfde nummer als return waarde.

## Meer info
[Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices#best-practices)
