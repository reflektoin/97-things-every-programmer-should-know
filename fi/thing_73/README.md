# Vältä Kiustausta Käyttää Singleton-mallia

Singleton malli ratkaisee monet ongelmistasi. Tiedät tarvitsevasi vain yhden ilmentymän. Sinulla on takuu, että tämä ilmentymä on alustettu ennen sen käyttöä. Yksi käyttökohta(access point) pitää suunnittelusi yksinkertaisena. Tämä kaikki on hyvää. Mitä epämukavaa tässä klassisessa suunittelumallissa olisi?

Itse asiassa aika paljon. Niin houkuttelevia kuin ne saattaakin olla, kokemus osoittaa suurimman osan singletoineista aiheuttavan enemmän harmia kuin hyötyä. Ne haittaavat estävät testausta ja haittaavat ylläpidettävyyttä. Valitettavasti tämä lisäviisaus ei ole levinnyt niin laajalle, kuin se olisi pitänyt, ja singletonit ovat edelleen vastustamattomia monille ohjelmoijille. Mutta niiden vastustaminen on sen arvoista:

- Yhden ilmentymän vaatimus on usein mielikuvitusta. Monissa tapauksissa kyseessä on vain spekulaatio, että muita ilmentymiä ei tulla tarvitsemaan tulevaisuudessa. Niin spekulatiivisten ominaisuuksien käyttö laajasti sovelluksen suunnittelussa tulee aiheuttamaan harmia jossain vaiheessa. Vaatimukset muuttuvat. Hyvän suunnitelman tulisi huomioida(embrace) tämä. Singletonit eivät tätä tee.

- Singletonit aiheuttavat implisiittisiä riippuvuuksia käsitteellisesti itsenäisten koodin osien välillä. Tämä on ongelmallista, koska ne ovat piilossa, ja koska ne lisäävät turhaa kytkentää osien välillä. Tämä koodihajusta(code smell) tulee pistävä, kun yrität kirjoittaa yksikkötestejä, jotka ovat riippuvaisia löyhästä kytkennästä ja kyvystä muuttaa valikoivasti malli oikeaan toteutukseen. Singletonit estävät suorasukaisen mallien käytön(singletons prevent such straight forward mocking).

- Singletonit myös pitävät implisiittistä pysyvää tilaa, mikä jälleen häiritsee yksikkötestausta. Yksikkötestaus riippuu testien riippumattomuudesta toisistaan, jotta testit voidaan ajaa missä järjestyksessä vain, ja ohjelma voidaan asettaa haluttuun tilaan ennen jokaista yksikkötestiä. Kun olet toteuttanut singletonit muuttuvalla tilalla(mutable state), tämä voi olla hankala saavuttaa. Lisäksi, niin globaali pitkäkestoinen/pysyväisluonteinen tila(persistent state) hankaloittaa koodin ymmärtämistä, etenkin monisäikeisessä ympäristössä.

- Monisäikeistys esittelee lisää singleton-mallin sudenkuoppia. Koska suorasuokainen lukon varaaminen ei ole kovin suorituskykyistä, joten niin kutsuttu double-checked locking -malli on yleistynyt. Valitettavasti tämä saattaa olla vielä kohtalokkaampaa. Käy ilmi, että monissa kielissä DCL-malli ei ole turvallinen säikeillä, ja joissa se on, on edelleen mahdollisuuksia toteuttaa se väärin.

Singletonien siivous(cleanup) saattaa olla viimeinen haaste:

- Singletonien explisiittistä tuhoamista ei ole tuettu, mikä voi aiheuttaa vakavia ongelmia joissain konteksteissa. Esimerkiksi liitännäis-arkkitehtuuri, jossa liitännäinen voidaan poistaa turvallisesti(safely unload) vasta kun kaikki sen objektit on siivottu.

- Ohjelmaa sulkiessa singletoneja ei siivota missään tietyssä järjestyksessä. Tämä voi aiheuttaa ongelmia sovelluksille, jotka sisältävät toisistaan riippuvaisia singletoneja. Ohjelmaa suljettaessa singleton saattaa yrittää tavoittaa toista singletonia, joka on jo tuhottu.

- Joistain mainituista tilanteista voidaan päästä eroon lisämekanismeilla. Kuitenkin tämä lisää koodin monimutkaisuutta, mikä olisi voitu välttää valitsemalla vaihtoehtoinen suunnitelma.

Täten, rajoita singleton-mallin käyttä luokkiin, jotka todellakin täytyy luoda vain kerran. Älä käytä singletonia globaalina liityntäkohtana(global access point) mielivaltaisesta koodista. Sen sijaan, suora liityntäkohta singletoniin pitäisi olla mahdollista vain muutamasta hyvin määritellystä paikasta, jossa se voidaan välittää sen rajapinnan kautta muulle koodille. Tämä muu koodi on tietämätön, eikä täten ole riippuvainen siitä, toteuttaako singleton vai mikä tahansa muu luokka kyseisen rajapinnan. Tämä rikkoo riippuvuuden, joka estää yksikkötestausta, ja parantaa ylläpidettävyyttä. Joten, seuraavan kerran ajatellessasi singletonin toteuttamista tai käyttämistä, toivottavasti pysähdyt ja mietit uudelleen.

Kirjoittanut [Sam Saariste](http://programmer.97things.oreilly.com/wiki/index.php/Sam_Saariste)