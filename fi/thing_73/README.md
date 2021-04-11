# V�lt� Kiustausta K�ytt�� Singleton-mallia

Singleton malli ratkaisee monet ongelmistasi. Tied�t tarvitsevasi vain yhden ilmentym�n. Sinulla on takuu, ett� t�m� ilmentym� on alustettu ennen sen k�ytt��. Yksi k�ytt�kohta(access point) pit�� suunnittelusi yksinkertaisena. T�m� kaikki on hyv��. Mit� ep�mukavaa t�ss� klassisessa suunittelumallissa olisi?

Itse asiassa aika paljon. Niin houkuttelevia kuin ne saattaakin olla, kokemus osoittaa suurimman osan singletoineista aiheuttavan enemm�n harmia kuin hy�ty�. Ne haittaavat est�v�t testausta ja haittaavat yll�pidett�vyytt�. Valitettavasti t�m� lis�viisaus ei ole levinnyt niin laajalle, kuin se olisi pit�nyt, ja singletonit ovat edelleen vastustamattomia monille ohjelmoijille. Mutta niiden vastustaminen on sen arvoista:

- Yhden ilmentym�n vaatimus on usein mielikuvitusta. Monissa tapauksissa kyseess� on vain spekulaatio, ett� muita ilmentymi� ei tulla tarvitsemaan tulevaisuudessa. Niin spekulatiivisten ominaisuuksien k�ytt� laajasti sovelluksen suunnittelussa tulee aiheuttamaan harmia jossain vaiheessa. Vaatimukset muuttuvat. Hyv�n suunnitelman tulisi huomioida(embrace) t�m�. Singletonit eiv�t t�t� tee.

- Singletonit aiheuttavat implisiittisi� riippuvuuksia k�sitteellisesti itsen�isten koodin osien v�lill�. T�m� on ongelmallista, koska ne ovat piilossa, ja koska ne lis��v�t turhaa kytkent�� osien v�lill�. T�m� koodihajusta(code smell) tulee pist�v�, kun yrit�t kirjoittaa yksikk�testej�, jotka ovat riippuvaisia l�yh�st� kytkenn�st� ja kyvyst� muuttaa valikoivasti malli oikeaan toteutukseen. Singletonit est�v�t suorasukaisen mallien k�yt�n(singletons prevent such straight forward mocking).

- Singletonit my�s pit�v�t implisiittist� pysyv�� tilaa, mik� j�lleen h�iritsee yksikk�testausta. Yksikk�testaus riippuu testien riippumattomuudesta toisistaan, jotta testit voidaan ajaa miss� j�rjestyksess� vain, ja ohjelma voidaan asettaa haluttuun tilaan ennen jokaista yksikk�testi�. Kun olet toteuttanut singletonit muuttuvalla tilalla(mutable state), t�m� voi olla hankala saavuttaa. Lis�ksi, niin globaali pitk�kestoinen/pysyv�isluonteinen tila(persistent state) hankaloittaa koodin ymm�rt�mist�, etenkin monis�ikeisess� ymp�rist�ss�.

- Monis�ikeistys esittelee lis�� singleton-mallin sudenkuoppia. Koska suorasuokainen lukon varaaminen ei ole kovin suorituskykyist�, joten niin kutsuttu double-checked locking -malli on yleistynyt. Valitettavasti t�m� saattaa olla viel� kohtalokkaampaa. K�y ilmi, ett� monissa kieliss� DCL-malli ei ole turvallinen s�ikeill�, ja joissa se on, on edelleen mahdollisuuksia toteuttaa se v��rin.

Singletonien siivous(cleanup) saattaa olla viimeinen haaste:

- Singletonien explisiittist� tuhoamista ei ole tuettu, mik� voi aiheuttaa vakavia ongelmia joissain konteksteissa. Esimerkiksi liit�nn�is-arkkitehtuuri, jossa liit�nn�inen voidaan poistaa turvallisesti(safely unload) vasta kun kaikki sen objektit on siivottu.

- Ohjelmaa sulkiessa singletoneja ei siivota miss��n tietyss� j�rjestyksess�. T�m� voi aiheuttaa ongelmia sovelluksille, jotka sis�lt�v�t toisistaan riippuvaisia singletoneja. Ohjelmaa suljettaessa singleton saattaa yritt�� tavoittaa toista singletonia, joka on jo tuhottu.

- Joistain mainituista tilanteista voidaan p��st� eroon lis�mekanismeilla. Kuitenkin t�m� lis�� koodin monimutkaisuutta, mik� olisi voitu v�ltt�� valitsemalla vaihtoehtoinen suunnitelma.

T�ten, rajoita singleton-mallin k�ytt� luokkiin, jotka todellakin t�ytyy luoda vain kerran. �l� k�yt� singletonia globaalina liitynt�kohtana(global access point) mielivaltaisesta koodista. Sen sijaan, suora liitynt�kohta singletoniin pit�isi olla mahdollista vain muutamasta hyvin m��ritellyst� paikasta, jossa se voidaan v�litt�� sen rajapinnan kautta muulle koodille. T�m� muu koodi on tiet�m�t�n, eik� t�ten ole riippuvainen siit�, toteuttaako singleton vai mik� tahansa muu luokka kyseisen rajapinnan. T�m� rikkoo riippuvuuden, joka est�� yksikk�testausta, ja parantaa yll�pidett�vyytt�. Joten, seuraavan kerran ajatellessasi singletonin toteuttamista tai k�ytt�mist�, toivottavasti pys�hdyt ja mietit uudelleen.

Kirjoittanut [Sam Saariste](http://programmer.97things.oreilly.com/wiki/index.php/Sam_Saariste)