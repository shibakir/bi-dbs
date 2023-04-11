Semestrální práce "**Pražský svaz studentů**". 

**Popis:**

Pražský svaz studentů se zabývá poskytováním možnosti využití **heren** pro volný čas studentů, které jsou poskytovány formou Game Pass. Každá taková místnost muze obsahovat nejake vybavení, má vlastní *název* a muze, ale nemusi, mit osobnosti, ktere jsou student-administrátorem, ktere maji na starosti jeji správu, a *kapacitu* . 
Omezení:
* Kapacita je nezáporné číslo menší než 20. 

**Vybavením** má *ID* může být **nábytek**, **konzole** a **hry**. 
Omezení:
* Jedno vybavení nemůže patřit do několika heren najednou.

**Nábytkem** je nějaká věc, která má *název* a *stav*.
Omezení:
Stav hodnotíme číslem od 1 do 5, kde 1 je nejlepší.

**Konzole** mají *model*, coz je kombinace cislice a pismena (napr. "7X"). 

**Hry** mají *název* a *žánr*.

Pražská unie studentů má **externího vedoucí**, který ke klubu formálně nepatří a není studentem. 
Má *unikátní ID*, *jméno* a *příjmení* a *datum narození* ve formátu DD.MM.RRRR.

**Osobnost** má *unikátní ID*, *jméno* a *příjmení*, *datum narození* ve formátu DD.MM.RRRR, *počet vlastních porušení*, typ členství ve studentskem svazu.
Omezení:
* Osobnost nemůže být v studentském svazu a mít více než 0 porušení současně. 
* Počet vlastních porušení  nemůže být menší než 0 a větší než 3. 

**Game Pass** má unikátní *ID*, *od* a *do* ve formátu DD.MM.RRRR, patří konkrétní osobnosti. 
Omezení:
* Game Pass se eviduje pro každou hernu konkrétně. (Tedy herna může mít registrováno více Game Passu.)
* Osobnost může mít několik Game Pass stejné herny, ale nesmí se překrývat.

**Členství ve studentském svazu** má unikatní *ID* a může byt rozsireno o roli student-administrátor.

**Student-administrátor** je nějaká osobnost, který spravuje právě jednu hernu, která může, ale nemusí mít stáž, tj. počet let, kdy má tuto povinnost na starosti.
Omezení:
* Osobnost nemůže být Student-administrátorem ve více místnostech současně, ale spravuje alespon jednu. 
* Ovšem herna muže mít několik student-administrátorů. 
* Student-administrátor automatický má Game Pass.
* Stáž je nezáporné číslo, které nemůže být vyšší než věk příslušného studenta.

**Koleje** mají unikatní *ID* a vlastní *název* . Kazda kolej ma adresu na ktere je umistena.
Omezení:
* Pocet heren, ktere patri do nejake koleji, nemuze byt vetsi nez 4.

**Adresa** má unikátní *ID*, *mesto*, *ulici* a *cislo orientacni*. Poznamka: Budeme předpokládat, že na stejné adrese se může nacházet několik kolejí (to znamená, že "Strahov 3" a "Strahov 8" musí být různé koleje, i když mají stejnou adresu (v mém světě)). 
Muzeme mit v databazi adresy, do kterych nepatri zadna kolej. 

Předpokládáné entity:  Herna, Vybavení, Nábytek, Konzole, Hra, Externí vedoucí, Osobnost,  Game Pass, Členství ve studentském svazu, Student-administrátor, Kolej apod.

_______________________


**Diskuse smyček:**


Mam smycku **Osobnost** - **Clenstvi_ve_studentskem_svazu** - **Student_administrator** - **Herna** - **Game_pass** - **Osobnost** .

To znamena, ze **Osobnost** muze mit **Clenstvi_ve_studentskem_svazu**, ktere navic predpoklada **Student_administrator**a v nejake **Herne**, ve ktere jsou zaregistrovane **Game Pass**y vcetne jeho. Ale my vime, ze **Student_administrator** nejake **Herny**  automaticky ma **Game Pass** v te **Herne** (to vime z popisu).

Navic k tomu reknu, ze **Osobnost** nemusi mit **Clenstvi_ve_studentskem_svazu**, aby mela **Game Pass**.

