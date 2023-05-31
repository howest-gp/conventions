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
    *  :white_check_mark: AuthorsBooks is correct  
    * :x: BooksAndAuthors is NIET correct    
    * :x: AuthorsInBooks is NIET correct    
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
  
    **Speciale aandacht voor PK kolommen**  *(Omwille van agosische redenen (1° semester) wordt afgeweken van wat later traditioneel gebruikt wordt binnen Entity Framework)*     
    * Wanneer een kolom dienst moet doen als PK en een identity of uniqueIdentifier kolom is, dan gebruik je als prefix de naam van de tabel in enkelvoud, gevolgd door de tekst "Id" of "Number"     
      * :white_check_mark: orderId is correct (in de veronderstelling dat dit de PK van de tabel Orders zou zijn)    
      * :white_check_mark: orderNumber is correct (in de veronderstelling dat dit de PK van de tabel Orders zou zijn)          
      * :x: id is NIET correct (in de veronderstelling dat dit de PK van de tabel zou zijn)               
      * :x: number is NIET correct (in de veronderstelling dat dit de PK van de tabel zou zijn)   
    
    **Speciale aandacht voor FK kolommen**   
    * Wanneer een kolom dienst moet doen als FK dan gebruik je als naam dezelfde naam als de kolom uit de andere tabel waar de FK naar toe verwijst.  
    * Stel : 
      * tabel Authors heeft als PK **authorId**  
      * in tabel Books komt een FK kolom die naar deze PK (in Authors) verwijst, dan gebruik je in Books eveneens **authorId**  
  
## Constraints
  Dien je zelf een naam te geven aan een constraint, dan zijn dit de afspraken :    
  * voor PK :  
    * gebruik prefix **pk_** gevolgd door de tabelnaam
    * Bijvoorbeeld : constraint **pk_Students** primary key(studentId)
  * voor FK : 
    * gebruik prefix **fk_**
      *  indien de enige FK in de tabel, dan kan je dit laten volgen door de tabelnaam    
         Bijvoorbeeld een FK in de tabel Students  : constraint **fk_Students** foreign key(departmentId) references Departments(departmentId)    
       * indien er meerder FK's in de tabel zijn, dan laat je dit volgen door de tabelnaam + underscore + naam van de betrokken kolom
         Bijvoorbeeld 2 FK's in de tabel Books : 
           * constraint **fk_Books_authorId** foreign key(authorId) references Authors(authorId)  
           * constraint **fk_Books_publisherId** foreign key(publisherId) references Publishers(publisherId)  
  * voor Unique constraints : 
    * gebruik de prefix **uq_** plus de naam van de kolom waarop dit slaat  
    * voorbeeld : ... constraint uq_socialSecurity UNIQUE (socialSecurity) 
  * voor Check constraints :   
    * gebruik de prefix **chk_** plus de naam van de kolom waarop dit slaat     
    * voorbeeld : ... constraint chk_tuitionFees CHECK (tuitionFees between 0 and 500)  
  * voor Default constraints :   
    * gebruik de prefix **df_** plus de naam van de kolom waarop dit slaat  
    * voorbeeld : ... constraint df_tuitionFees DEFAULT 550 for tuitionFees    

