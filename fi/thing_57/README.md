# Viestien Välitys Johtaa Rinnakkaisten Järjestelmien Parempaan Skaalautuvuuteen

Ohjelmoijille opetataan opintojen alusta lähtien, että yhtäaikaisuus(concurrency) - ja erityisesti rinnakkaisuus(palallellism), yhtäaikaisuuden erityinen osajoukko - on vaikeaa, että ainoastaan parhaat voivat edes toivoa onnistuvansa siinä, ja jopa epäonnistuvat siinä. Siinä keskitytään paljon säikeisiin, semaforiin, monitoreihin ja kuina vaikea on saada yhtäaikainen pääsy muuttujiin turvalliseksi säikeille.

Totta, on monia vaikeita ongelmia ja ne voi olla hankala ratkaista. Mutta, mikä on ongelman perusta? Jaettu muisti. Lähes kaikki yhtäaikaisuuden ongelmat, joista ihmiset puhuvat liittyvät jaettuun muokattavaan muistiin(shared mutable memory): kilpailutilanne(race condition), lukkiutuminen(deadlock), livelock jne. Vastaus vaikuttaa ilmiselvältä: Joko luovu yhtäaikaisuudesta tai vältä jaettua muistia!

Yhtäaikaisuudesta luopuminen ei lähes varmastikaan ole vaihtoehto. Tietokoneiden ytimet lisääntyvät lähes joka kvartlaasi, joten rinnakkaisuuden hyödyntämisen tärkeys kasvaa jatkuvasti. Emme voi enää luottaa prosessorin kellotaajuuden nopeutumisen parantavan sovelluksien suorituskykyä. Vain rinnakkaisuutta hyödyntämällä sovellusten suorituskyky paranee. Selvästikin suorituskyvyn parantamatta jättäminen on vaihtoehto, mutta käyttäjät eivät sitä todennäköisesti hyväksy.

Joten voimmeko luopua jaetusta muistista? Ehdottomasti.

Säikeiden ja jaetun muistin ohjelmointimallina(programming model) käyttämisen sijaan voimme käyttää prosesseja ja viestien välittämistä. Prosessi tässä tarkoittaa vain suojattua itsenäistä tilaa ajettavalla koodilla, ei välttämättä käyttäjärjestlmän prosessia. Kielet kuten Erlan (ja occam ennen sitä) ovat todistaneet, että prosessit ovat menestyksekäs mekanismi yhtäaikaisten ja rinnakkaisten järjestelmien ohjelmointiin. Sellaisilla järjestelmillä ei ole synkronisoinnin rasitteita, joita jaetun muistin ja monisäikeisillä järjestelmillä on. Lisäksi on formaali malli - Communicating Sequential Prosesses (CSP) - jota voidaan käyttää osana sellaisten järjestelmien tekemiseen.

Voimme mennä pidemmälle ja esitellä tietovuo-järjestelmät(dataflow systems) laskennan tapana(way of computing). Tietovuo-järjestelmässä ei ole eksplisiittisesti ohjelmoitua ohjelman kulkua(control flow). Sen sijaan operaattoreiden suunnattu graafi(directed graph of operators), yhdistettynä data-polkuihin(data paths), järjestetään ja sitten dataa syötetään järjestelmään. Evaluintia hallitsee järjestelmässä olevan datan valmius. Ei varmastikaan synkronisointiongelmia.

Kaiken tämän sanottuani, kielet kuten C, C++, Java, Python ja Groovy ovat pääasiallisia järjestelmien kehityskieliä ja kaikki nämä esitetään ohjelmoijille kielinä, joilla kehitetään monisäikeisiä jaetun muistin järjestelmiä. Joten mitä on tehtävissä? Vastaus on käyttää - tai jos niitä ei ole, luoda - kirjastoja ja ohjelmistokehyksiä, jotka tarjoavat prosessimalleja ja viestien välityksen, välttäen kokonaan jaetun muistin käyttämisen.

Kaiken kaikkiaan, jaetun muistin sijaan viestien välittämisellä ohjelmoiminen on todennäköisesti menestyksekkäämpi tapa toteuttaa järjestelmiä, jotka hyödyntävät rinnakkaisuutta, joka on nyt endeemistä tietokoneissa. Ehkä kummallisesti, vaikka prosessit edeltävät säikeita yhtäaikaisuuden yksikkönä, tulevaisuussa tunnutaan käyttävän säikeitä prosessien toteuttamiseen.

Kirjoittanut [Russel Winder](http://programmer.97things.oreilly.com/wiki/index.php/Russel_Winder)