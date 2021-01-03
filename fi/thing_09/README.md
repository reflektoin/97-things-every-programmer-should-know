# Tarkasta Oma Koodisi Ennen Muiden Syyttämistä

Kehittäjien - kaikkien meistä! - on usein vaikea uskoa, että oma koodimme olisi rikki. Se on vain niin epätodennäköistä, että kerrankin sen pitää olla kääntäjän, mikä on rikki.

Kuitenkin oikeasti on erittäin epätodennäköistä, että koodi olisi rikki kääntäjässä(compiler), tulkissa(interpreter), käyttöjärjestelmässä(OS), serverissä(app server), tietokannassa(database), muistinhallinnassa(memory manager) jossakin muussa järjestelmän ohjelmistossa olevasta virheestä johtuen. Kyllä, näitä vikoja on, mutta ne ovat paljon harvinaisempia kuin haluaisimme uskoa.

Minulla oli kerran oikea ongelma kääntäjän vian kanssa, joka optimoi silmukka-muuttujan pois, mutta olen kuvitellut vian olevan kääntäjässä tai käyttöliittymässä useampia kertoja. Olen tuhlannut paljon aikaani, teknisen tuen aikaa, ja johdon aikaa korjauksessa vain tunteakseni itseni vähän tyhmäksi joka kerta, kun selvisi, että vika olikin minun aiheuttama.

Olettaen, että työkalut ovat laajalti käytössä, kypsiä ja niitä on hyödynnetty monessa teknologiapinossa (technology stack), ei ole syytä epäillä työkalujen laatua. Totta kai, jos työkalu on vasta julkaistu tai se on vähän käytetty, versio 0.1, avointa lähdekoodia, niin saattaa olla hyvä syy epäillä ohjelmistoa. (Samalla tavoin, kaupallisen ohjelmiston (commercial software) alfa-versio saattaa olla epäilyttävä.)

Kääntäjien vikojen harvinaisuuden huomioon ottaen, sinun on parempi sijoittaa aikasi ja energiasi virheiden löytämiseen omasta koodistasi, kuin todistaa kääntäjän olevan väärässä. Kaikki yleiset virheiden korjauksien neuvot pätevät, eristä ongelma, stub out calls(?); ympäröi se testeillä, tarkasta kutsumiskäytännöt, jaetut kirjastot ja versionumerot; selitä vika jollekin toiselle; tarkkaile pinon turmeltumista(corruption) ja muuttujien tyyppien yhteensopimattomuuksia; kokeile koodia eri koneille ja rakennusasetuksilla(build configurations), kuten debug ja julkaisu(release).

Kyseenalaista omat ja muiden oletukset. Eri toimittajien työkalut saattavat sisältää eri olettamuksia. Samoin saman toimittajan eri työkalut. Kun joku muu raportoi ongelman, jota et voi toistaa. Mene ja katso mitä he tekevät. He saattavat tehdä jotain, mitä et ole koskaan ajatellut, tai he tekevät jotain eri järjestyksessä.

Henkilökohtaisena sääntönä jos minulla on vika, jota en saa selvitettyä ja alan epäillä vian olevan kääntäjässä. Silloin on aika etsiä pinon turmeltumista(corruption). Tämä pätee erityisesti, jos jäljitys(trace)koodin lisäys aiheuttaa ongelman liikkumista.

Monisäikeisyyden(multi-threaded) ongelmat ovat toinen vikojen lähde, joka aiheuttaa harmaita hiuksia ja koneelle huutamista. Kaikki suositukset yksinkertaisen koodin suosimiseen moninkertaistuvat kun järjestelmä on monisäikeinen. Vikojen korjaukseen ja yksikkötesteihin ei voi luottaa vikojen johdonmukaisessa löytämisessä, joten suunnitelma yksinkertaisuus on tärkeintä.

Joten ennen kuin syöksyt syyttämään kääntäjää, muista Sherlock Holmesin neuvo "kun kaikki mahdoton on karsittu pois, niin se mitä jää jäljelle, kuinka uskomatonta se lieneekään, on väistämättä totuus." äläkä Dirk Gentlyn neuvoa "Kun kaikki epätodennäköinen on karsittu pois, niin se mitä jää jäljelle, kuinka uskomantonta se lieneekään, on väistämättä totuus."

Alkuperäinen kirjoittaja [Allan Kelly](http://programmer.97things.oreilly.com/wiki/index.php/Allan_Kelly)