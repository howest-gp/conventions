# C# Codeerstandaarden en naamgevingsconventies


| Naam van een...         | Notatie            | Lengte | Meervoud           | Prefix             | Suffix             | Afkorting          | Karakters         | Underscores        |
|:------------------------|:-------------------|-------:|:------------------:|:------------------:|:------------------:|:------------------:|:------------------|:------------------:|
| Klasse                  | **P**ascal**C**ase |    128 | :x:                | :x:                | :white_check_mark: | :x:                | [A-z][0-9]        | :x:                |
| Constructor             | **P**ascal**C**ase |    128 | :x:                | :x:                | :white_check_mark: | :x:                | [A-z][0-9]        | :x:                |
| Methode                 | **P**ascal**C**ase |    128 | :white_check_mark: | :x:                | :x:                | :x:                | [A-z][0-9]        | :x:                |
| Parameter               | **c**amel**C**ase  |    128 | :white_check_mark: | :x:                | :x:                | :white_check_mark: | [A-z][0-9]        | :x:                |
| Lokale variabele        | **c**amel**C**ase  |     50 | :white_check_mark: | :x:                | :x:                | :white_check_mark: | [A-z][0-9]        | :x:                |
| Constante               | **P**ascal**C**ase |     50 | :x:                | :x:                | :x:                | :x:                | [A-z][0-9]        | :x:                |
| Klasse veld             | **c**amel**C**ase  |     50 | :white_check_mark: | :x:                | :x:                | :white_check_mark: | [A-z][0-9]        | :white_check_mark: |
| Property                | **P**ascal**C**ase |     50 | :white_check_mark: | :x:                | :x:                | :white_check_mark: | [A-z][0-9]        | :x:                |
| Delegate                | **P**ascal**C**ase |    128 | :x:                | :x:                | :white_check_mark: | :white_check_mark: | [A-z]             | :x:                |
| Enum                    | **P**ascal**C**ase |    128 | :white_check_mark: | :x:                | :x:                | :x:                | [A-z]             | :x:                |

### 1. Gebruik PascalCase voor namen van klassen en methoden.

```csharp
public class ClientActivity
{
  public void ClearStatistics()
  {
    //...
  }
  public void CalculateStatistics()
  {
    //...
  }
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.

### 2. Gebruik camelCase voor parameters en lokale variabelen.

```csharp
public class UserLog
{
  public void Add(LogEvent logEvent)
  {
    int itemCount = logEvent.Items.Count;
    // ...
  }
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.

### 3. Gebruik betekenisvolle namen voor variabelen.
Het onderstaande voorbeeld definieert `seattleCustomers` voor klanten die zich in Seattle bevinden:

```csharp
var seattleCustomers = from customer in customers
  where customer.City == "Seattle" 
  select customer.Name;
```

> **Waarom?**
>
> Dit maakt je code zelfbeschrijvend en leesbaarder.

### 4. Gebruik GEEN Hongaarse notatie of andere type-gerelateerde notaties in naamgeving.

```csharp
// Correct
int counter;
string name;    
// Fout
int iCounter;
string strName;
```
> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid. De type-gerelateerde informatie in de naam is redundant.

### 5. Gebruik GEEN underscores in namen. Uitzondering: private velden mogen met een underscore beginnen.

```csharp 
// Correct
public DateTime clientAppointment;
public TimeSpan timeLeft;   
private DateTime registrationDate; 
// Fout
public DateTime client_Appointment;
public TimeSpan time_Left; 
// Uitzondering (klasse veld)
private DateTime _registrationDate;
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.
> Underscores in private velden vermijden een overmatig gebruik van `this` bij aanwezigheid van gelijknamige parameters en lokale variabelen.

### 6. Gebruik GEEN schreeuwerige hoofdletters voor constanten en readonly variabelen.

```csharp
// Correct
public const string ShippingType = "DropShip";
// Fout
public const string SHIPPINGTYPE = "DropShip";
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.
> Hoofdletters eisen te veel visuele aandacht op.

### 7. Gebruik GEEN afkortingen, behalve voor vaak voorkomende afkortingen zoals Id, Xml, Ftp, Uri, enz.

```csharp    
// Correct
UserGroup userGroup;
Assignment employeeAssignment;
// Fout
UserGroup usrGrp;
Assignment empAssignment;
// Uitzonderingen
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en voorkomt inconsistente afkortingen.

### 8. Gebruik PascalCasing voor afkortingen van 3 of meer karakters.<br />Gebruik hoofdletters voor afkortingen van 2 karakters.

```csharp  
// Correct
HtmlHelper htmlHelper;
FtpTransfer ftpTransfer;
UIControl uiControl;
// Fout
HTMLHelper htmlHelper;
FTPTransfer ftpTransfer;
UiControl uiControl;
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.
> Hoofdletters eisen te veel visuele aandacht op.

### 9. Gebruik voorgedefinieerde type namen (C# aliases) zoals `int`, `float`, `string` voor declaraties.<br />Gebruik .NET Framework namen zoals `Int32`, `Single`, `String` wanneer je de statische members van dat type aanroept zoals `Int32.TryParse` of `String.Join`.

```csharp
// Correct
string firstName;
int lastIndex;
bool isSaved;
string commaSeparatedNames = String.Join(", ", names);
int index = Int32.Parse(input);
// Fout
String firstName;
Int32 lastIndex;
Boolean isSaved;
string commaSeparatedNames = string.Join(", ", names);
int index = int.Parse(input);
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en verhoogt de leesbaarheid.

### 10. Gebruik GEEN `var` keyword voor primitieve types (int, string, double, etc). 

```csharp 
// Correct
var stream = File.Create(path);
Stream stream = File.Create(path);
var customers = new Dictionary();
Dictionary customers = new Dictionary();
int index = 100;
string title = "Title";
bool isCompleted = false;
// Fout
var index = 100;
var title = "Title";
var isCompleted = false;
```

> **Waarom?**
>
> Het `var` keyword maakt lange typenamen leesbaarder. Voor primitieve types is dat niet het geval.

### 11. Gebruik zelfstandige naamwoorden of samenstellingen ervan als klassenaam. 

```csharp 
//Correct
public class Employee
{
}
public class BusinessLocation
{
}
public class DocumentCollection
{
}
//Fout
public class DoWork
{
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en maakt code leesbaarder en zelfbeschrijvend.
> Klassen worden benoemd met zelfstandige naamwoorden omdat ze geen acties zijn.

### 12. Gebruik de letter I als prefix voor de naam van een interface. Interfaces zijn zelfstandige naamwoorden of adjectieven.

```csharp    
// Voorbeelden
public interface IShape
{
}
public interface IShapeCollection
{
}
public interface IGroupable
{
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en maakt code leesbaarder en zelfbeschrijvend.
> Interface namen kunnen een adjectief zijn omdat ze geïmplementeerd worden door een klasse (zelfstandig naamwoord).

### 13. Gebruik dezelfde bestandsnaam voor codebestanden als de klassenaam die er in is gedefinieerd.

Uitzondering: bestandsnamen die partiële klassen bevatten moeten het doel of oorsprong beschrijven, b.v. designer, generated, enz.

```csharp 
// Gedefinieerd in Task.cs
public partial class Task
{
    // user code goes here
}
// Gedefinieerd in Task.generated.cs
public partial class Task
{
    // autogenerated code goes here
}
```

> **Waarom?**
>
> Bestanden worden alfabetisch gesorteerd en op deze manier blijven partiële klassen naast staan. De Solution Explorer in Visual Studio schikt deze bestandnamen in een hiërarchische structuur.

### 14. Gebruik hiërarchisch gestructureerde namespaces.

```csharp 
// Voorbeelden
namespace Company.Product.ModuleA.SubModuleOne
{
}
namespace Company.Product.ModuleA.SubModuleTwo
{
}
namespace Company.Product.ModuleB
{
}
```

> **Waarom?**
>
> Dit draagt bij tot een goed gestructureerde broncode.

### 15. Plaats accolades op hun eigen regel.

```csharp 
// Correct
class Program
{
  static void Main(string[] args)
  {
    //...
  }
}
// Fout
class Program {
  static void Main(string[] args) {
    //...
  }
}
```

> **Waarom?**
>
> Algemeen aanvaardde manier om code leesbaarder te maken.

### 16. Declareer alle klasse members bovenaan, met statische variabelen helemaal bovenaan.

```csharp 
// Correct
public class Account
{
  public static string BankName;
  public static decimal Reserves;      
  public string Number { get; set; }
  public DateTime DateOpened { get; set; }
  public DateTime DateClosed { get; set; }
  public decimal Balance { get; set; }     
  // Constructor
  public Account()
  {
    // ...
  }
}
```

> **Waarom?**
>
> Algemeen aanvaardde manier die voorkomt dat je scrollend op zoek moet gaan naar member declaraties.

### 17. Gebruik enkelvoudige namen voor enums.<br />Gebruik meervoud voor bitwise enums.

```csharp 
// Correct
public enum Color
{
  Red,
  Green,
  Blue,
  Yellow,
  Magenta,
  Cyan
} 
// Uitzondering
[Flags]
public enum Dockings
{
  None = 0,
  Top = 1,
  Right = 2, 
  Bottom = 4,
  Left = 8
}
```

> **Waarom?**
>
> Maakt de code leesbaarder. Namen van bitwise enums plaats je in meervoud omdat ze meerdere waarden kunnen bevatten (gebruik van OR).

### 18. Vermeld GEEN type van een enum of waarden van enums, behalve voor bitwise enums.

```csharp  
// Correct
public enum Direction
{
  North,
  East,
  South,
  West
}
// Fout
public enum Direction : long
{
  North = 1,
  East = 2,
  South = 3,
  West = 4
}
```

> **Waarom?**
>
> Kan verwarring veroorzaken wanneer men zich baseert op de werkelijke types of waarden.

### 19. Gebruik GEEN "Enum" suffix in de naam van een enum type:

```csharp     
// Correct
public enum Coin
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
}
// Fout
public enum CoinEnum
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
} 
```

> **Waarom?**
>
> Dit maakt de code leesbaarder. De type-gerelateerde informatie in de naam is redundant.

### 20. Gebruik GEEN "Flag" of "Flags" suffix in de naam van een enum type:

```csharp 
// Correct
[Flags]
public enum Dockings
{
  None = 0,
  Top = 1,
  Right = 2, 
  Bottom = 4,
  Left = 8
}
// Fout
[Flags]
public enum DockingsFlags
{
  None = 0,
  Top = 1,
  Right = 2, 
  Bottom = 4,
  Left = 8
}
```

> **Waarom?**
>
> Dit maakt de code leesbaarder. De type-gerelateerde informatie in de naam is redundant.

### 21. Gebruik GEEN parameternamen die enkel verschillen in hoofdletters

```csharp 
// Avoid
private void MyFunction(string name, string Name)
{
  //...
}
```

> **Waarom?**
>
> Hiermee wordt verwarring en betekenisloze naamgeving voorkomen.

### 22. Gebruik twee parameters genaamd sender en e in event handlers

De `sender` parameters vertegenwoordigen het object dat het event heeft opgeworpen en is meestal van het type object, ook al is het mogelijk om een specifieker type te declareren.

```csharp
public void ReadBarcodeEventHandler(object sender, ReadBarcodeEventArgs e)
{
  //...
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework en maakt de event handler methode herkenbaar.

### 23. Gebruik het suffix EventHandler voor delegates die je voor event handlers gebruikt.

```csharp 
public delegate void BarcodeScannedEventHandler(object sender, BarcodeScannedEventArgs e);
```

> **Waarom?**
>
> Maakt de code leesbaarder. De suffix in de naam maakt de type-karakteristieken herkenbaar.

### 24. Beëindig de naam met "EventArgs" bij het maken van klassen die de informatie van een event bevatten.

```csharp 
// Correct
public class BarcodeScannedEventArgs : System.EventArgs
{
}
// Fout
public class BarcodeScannedData : System.EventArgs
{
}
```

> **Waarom?**
>
> Maakt de code leesbaarder. De suffix in de naam maakt de type-karakteristieken herkenbaar.

### 25. Beëindig de naam met "Exception" bij het maken van klassen die de informatie van een Exception bevatten.

```csharp 
// Correct
public class BarcodeReadException : System.Exception
{
}
// Fout
public class BarcodeReadError : System.Exception
{
}
```

> **Waarom?**
>
> Dit is in lijn met Microsofts .NET Framework, is makkelijk te lezen en is herkenbaar.

## Referenties

1. [MSDN General Naming Conventions](http://msdn.microsoft.com/en-us/library/ms229045(v=vs.110).aspx)
2. [DoFactory C# Coding Standards and Naming Conventions](http://www.dofactory.com/reference/csharp-coding-standards) 
3. [MSDN Naming Guidelines](http://msdn.microsoft.com/en-us/library/xzf533w0%28v=vs.71%29.aspx)
4. [MSDN Framework Design Guidelines](http://msdn.microsoft.com/en-us/library/ms229042.aspx)
5. [C# Coding Standards and Naming Conventions](https://github.com/ktaranov/naming-convention/blob/master/C%23%20Coding%20Standards%20and%20Naming%20Conventions.md)
