#Családi ToDo

##Követelményanalízis

1. Követelmények összegyűjtése

    - Funkcionális elvárások
        + Az otthoni házimunkák összegyűjtését, illetve feljegyzését segíti elő ez a webes alkalmazás
        + A házimunkák listáját meg lehet tekinteni
        + Az egyes házimunkákat lehet módisítani 
        + Az egyes házimunkákat lehet törölni is, ha azok már nem aktuálisak 
    
    - Nem funkcionális követelmények
        + Felhasználóbarát, ergonomikus elrendezés és kinézet
        + Biztonságos működés: jelszavak tárolása, funkciókhoz való hozzáférés.

2. Használatieset-modell
    - Szerepkörök:
        + Vendég: Kezdőoldalt és a leírást megnézheti, tud regisztrálni
        + Felhasználó: A vendég szerepkörén túl tud új házimunkát hozzáadni, illetve megnézheti az eddigi listát, ahol a feladatokat törölheti és módosíthatja is
    
    - Használati eset diagram:
        ![Használati eset diagram](public/használatiesetdiagram.png)
    
    - Folyamatok pontos menete:
        + Házimunka felvitele
        + Házimunka módosítása
        + Házimunka törlése
        
        Keresés felvitelének folyamata:
            ![Keresés felvitelének folyamata](public/AddnewTodo.png)


##Tervezés

1. Architektúra terv
    - Komponensdiagram
    
    - Oldaltérkép
    
        + Publikus:
        
	  - Főoldal
	  - Leírás
	  - Bejelentkezés
        
        + Felhasználó
        
            - Főoldal
	    - Leírás
            - Bejelentkezés/Kijelentkezés
            - Házimunkák listája
                + új házimunka felvétele
                + Házimunka módosítása
                + Házimunka törlése

    - Végpontok
        GET /: főoldal
		
		GET /about: leíró oldal
        
        GET /login: bejelentkező oldal
        
        POST /login: bejelentkezési adatok felküldése
        
        GET /login/signup: regisztáló oldal
        
        POST /login/signup: regisztrálási adatok felküldése
        
        GET /errors/list: házimunka lista oldal
        
        GET /errors/new: új házimunka felvitele
        
        POST /errors/new: új házimunka felvitele, adatok küldése
        
        GET /errors/:id: házimunka adatait megváltoztató oldal
        
        POST /errors/:id: megváltoztatott adatok felküldése
        
        GET /delete/:id: házimunka törlése
        

2. Felhasználóifelület-modell
    - Oldalvázlatok
    ![Todo-k listázása](public/todolist.jpg)
    ![Új keresés felvétele](public/newtodov2.jpg)

3. Osztálymodell
    - Adatmodell
    
        ![Adatmodell](public/adatmodell.png)

    - Adatbázisterv
    
        ![Adatbázisterv](public/idadat.png)

##Implementáció
1. Fejlesztői környezet bemutatása
    Cloud 9 webes IDE, ahova Github accounttal való belépés után új workspacet hozhatunk létre (new workspace). Itt egy fájlt futtathatunk például a webes terminálablakból, a node fájlnév paranccsal. 
    
2. Könyvtárstruktúrában lévő mappák funkiójának bemutatása
    - config: A Waterline konfigurációja (Waterline adatbázis absztrakciós réteg, gyűjteményeket, modelleket, adaptereket tartalmaz)
    - controllers: A vezérlő. Folyamatirányítás, kérés fogadása, feldolgozása 
    - models: Modellek definiálása, adatok és feldolgozási logika
    - node_modules: 
    - public: 
    - viewmodels: Nézetmodel
    - views: A kimenetért felelős rész, vagyis az egyes oldalak szerkezetét, kinézetét adja meg

##Felhasználói dokumentáció
1. Környezet
    - A weboldal futtatásához ajánlott telepített Internet Explorer, Mozilla Firefox, Google Chrome böngésző, ha van rá mód a legfrisebb verzióban.
    - Fontos, hogy NoScript vagy hasonló plugint mely blokkolná az oldalon megjelenő scripteket, kapcsoljuk ki vagy az oldalt adjuk hozzá a kivételek listájához. Enélkül nem használható az oldal(mivel nagyrésze javascriptből épül fel).
2. Minimális gépigény
    - CPU: Intel Core 2 Duo 2,16 GHz , AMD Athlon2 340 X2 
    - Memória: 2 GB DDR3
    - HDD: 1 GB

##Tesztelés
- A tesztelést Windows 8.1 operációs rendszeren, Google Chrome-ban végeztem Selenium IDE használatával végeztem
- Hozzáadtam a listához egy új todot, leírását módosítottam, majd töröltem
- A tesztelés sikeres volt
