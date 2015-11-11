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
        ![Használati eset diagram](https://cloud.githubusercontent.com/assets/14542234/11077749/fa9bdd48-8801-11e5-8b45-cf7fd9cc970b.png)
    
    - Folyamatok pontos menete:
        + Házimunka felvitele
        + Házimunka módosítása
        + Házimunka törlése
        
        Todo felvitelének folyamata:
            ![Todo felvitelének folyamata](https://cloud.githubusercontent.com/assets/14542234/11077751/fa9d3aee-8801-11e5-8050-c21749af1272.png)


##Tervezés

1. Architektúra terv
    - Komponensdiagram
    
    - Oldaltérkép
    
        + Publikus:
        
	  - Főoldal
	  - Leírás
	  - Bejelentkezés
	  
	+ Felhasználó:
        
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
    ![Todo-k listázása](https://cloud.githubusercontent.com/assets/14542234/11077753/fab13184-8801-11e5-9cc8-f0679c6111ac.jpg)
    ![Új keresés felvétele](https://cloud.githubusercontent.com/assets/14542234/11077752/faaf8bcc-8801-11e5-8362-38a0df6569a6.jpg)

3. Osztálymodell
    - Adatmodell
    
        ![Adatmodell](https://cloud.githubusercontent.com/assets/14542234/11077748/fa99c256-8801-11e5-8c92-7c43712e8db3.png)

    - Adatbázisterv
    
        ![Adatbázisterv](https://cloud.githubusercontent.com/assets/14542234/11077746/fa995316-8801-11e5-9185-c0a73a8904d4.png)

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
