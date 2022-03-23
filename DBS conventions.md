# Naamgevingsconventies van toepassing vanaf schooljaar 2022-2023

## Databasenamen
  Gebruik  
  * een Engelstalige naam  
  * een duidelijke naam die aangeeft waarover het gaat : Library, MyBooks, Beers  
  * de **PascalNotatie** :   
    * :white_check_mark: **M**y**B**ooks is correct  
    * :x: **m**y**B**ooks is NIET correct  
  
## Tabelnamen  
  Gebruik
  * een Engelstalige naam
  * een duidelijke naam die aangeeft waarover het gaat : Books, Authors, Publishers ...
  * de **PascalNotatie** :
    * :white_check_mark: **O**rder**I**tems is correct
    * :x: **o**rder**I**tems is NIET correct 
  * (bij voorkeur) de meervoudsvorm  
    *  :white_check_mark: Book**s** is correct  
    * :x: Book is NIET correct  
  * voor zogenaamde "tussentabellen" de namen van de betrokken tabellen samengevoegd     
    *  :white_check_mark: BooksAuthors is correct  
    * :x: BooksAndAuthors is NIET correct    

## Kolomnamen   
  Gebruik
  * een Engelstalige naam
  * een duidelijke naam die aangeeft waarover het gaat : employeeName, salary, orderNumber ...
  * de **camelCaseNotatie** :
    * :white_check_mark: order**I**tems is correct
    * :x: **O**rder**I**tems is NIET correct   
    * :x: **o**rder**i**tems is NIET correct 
  * (bij voorkeur) de enkelvoudsvorm  
    *  :white_check_mark: location is correct  
    * :x: location**s** is NIET correct  
  
  **Speciale aandacht voor volgende**  
    * Primaire sleutels  
      * Wanneer als PK een identity of uniqueIdentifier kolommen dan gebruik je als prefix de naam van de tabel in enkelvoud, gevolgd door de tekst Id of Number of ...  
        * :white_check_mark: OrderItems is correct
        * :x: orderItems is NIET correct       
