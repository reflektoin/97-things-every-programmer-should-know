# Ohjelmointia järjellä

Ohjelman toimivuuden ymmärtäminen muodollisen todistuksen avulla on pidempi kuin itse ohjelma ja todennäköisesti sisältää enemmän virheitä kuin itse ohjelma. Auotmaattiset työkalut ovat parempia, mutta eivät aina mahdollisia. Seuraava kuvaa keskitietä: puolimuodollista ymmärtämistä ohjelman oikeellisuudesta.

Perimmäinen lähestymistapa on jakaa kaikki tutkittava koodi pieniin osiin - yhdestä rivistä, kuten funktiokutsusta alle kymmenen rivin lohkoihin - ja arvioimalla niiden oikeellisuutta. Argumenttien pitää olla vain riittävän vahvoja vakuuttaaksesi sinun paholaisen asiananaja -vertaiskoodarin.

Osio tulisi valita niin, että jokainen jokainen loppupiste, *ohjelman tila* (ohjelmalaskuri ja kaikkien "elävien" olioiden arvot) täyttää helposti kuvatun ominaisuuden ja että osion toiminnallisuus (tilan muutos) on helppo kuvata yhtenä tehtävänä - nämä tekee järkeilystä(reasoning) helpompaa. Sellaiset päätepisteen(endpoint) ominaisuudet yleistävät konseptit kuten *ennakkoehto* ja *jälkiehto* funktioille ja *invariantti* silmukoille ja luokille (niiden olioihin verrattuna). Pyrkimuys pitää osiot mahdollisimman itsenäisinä toisistaan yksinkertaistaa järkeilyä ja on välttämätöntä, kun osioita tullaan muokkaamaan.

Monet tunnetut (vaikkakin ehkä harvemmin noudatetut) ja hyväksi havaitut ohjelmointikäytännöt helpottavat järkeilyä. Siten, jo aikomaalla järkeillä ohjelmaasi alat miettimään parempaa tyyliä ja rakennetta. Ei ole yllättävää, että monet näistä käytännöistä voidaan tarkastaa staattisilla koodin analysaattoreilla:

1. Vältä goto-lauseita, ne tekevät osista riippuvaisia keskenään.
- Vältä muokattavia globaaleja muuttujia, koska ne tekevät kaikista niitä käyttävistä osista riippuvaisia keskenään
- Jokaisella muuttujalle pitäisi olla pienin mahdollinen soveltamisala(scope). Esimerkiksi paikallinen olio voidaan julistaa juuri ennen ensimmäistä käyttöä.
- Tee olioista *muuttumattomia* aina kun relevanttia.
- Tee koodista luettavaa käyttäen rivivälejä, sekä horisontaalisesti että vertikaalisesti. Esimerkiksi yhteenkuuluvat rakenteet ja erottamalla tyhjällä rivillä kaksi osiota.
- Tee koodista itsensä dokumentoivaa valitsemalla kuvaavat (mutta suhteellisen lyhyet) nimet olioille, tyypeille, funktioilla jne.
- Jos tarvitset sisäkkäisiä osioita, tee siitä funktio.
- Tee funktioistasi lyhyitä ja yhden asian tekeviä. Vanha *24 rivin raja* pitää edelleen paikkansa. Vaikka näyttöjen koko ja resoluutio on muuttunut, mikään ei ole muuttunut ihmisen kognitiossa 1960-luvun jälkeen.
- Funktioilla tulisi olla vain muutama parametri (neljä on hyvä yläraja). Tämä ei rajoita funktioilla kommunikoitua dataa: Yhteen liittyvien parametrien ryhmittely yhteen olioon hyötyy *olio invarianteista* ja vähentää järkeilyä, kuten niiden johdonmukaisuutta(coherence) ja yhtäpitävyyttä(consistency).
- Yleisesti, jokaisella koodin yksiköllä, lohkosta kirjastoon, pitäisi olla *suppea rajapinta*. Vähempi kommunikaatio vähentää tarvittavaa järkeilyä. Tämä tarkoittaa *gettereitä*, jotka palauttavat sisäisen tilan ovat riesa - älä kysy objektilta tietoa käsittelyä varten. Pyydä sen sijaan objektia tekemään jotain tiedolle joka sillä on jo. Toisin sanoin, *kapselointi* on kaikki - ja ainut - *suppeista rajapinnoista*.
- Ylläpitääksesi luokan *invariantit*, *settereiden* käyttöä pitäisi estää, koska *setterit* tuppaavat sallimaan invariantit jotka vaativat olion tilan olemaan rikki.

Oikeellisuuden järkeilyn lisäksi, väittely koodistasi lisää ymmärrystäsi siitä. Kommunikoi oivalluksesi kaikkien hyödyksi.

Alkuperäinen kirjoittaja [Yechiel Kimchi](http://programmer.97things.oreilly.com/wiki/index.php/Yechiel_Kimchi)