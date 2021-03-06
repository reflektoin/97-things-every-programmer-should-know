# Kuinka Käyttää Virheenseurantaohjelmaa

Kutsut niitä sitten *bugeiksi*, *vioiksi*, tai jopa *suunnittelun sivuvaikutukseksi*, et pääse niistä eroon. Hyvän bugiraportin tekeminen ja niistä asioiden etsiminen ovat avaintaitoja projektin pitämisessä liikkeessä.

Hyvä bugiraportti tarvitsee kolme asiaa:

- Miten toistaa bugi, mahdollisimman tarkasti, ja kuinka usein tämä aiheuttaa bugin ilmenemisen.
- Mitä olisi pitänyt tapahtua, ainakin sinun mielestäsi.
- Mitä oikeasti tapahtui, tai ainakin kaikki tieto, mitä sinä ollet tallentanut.

Bugiraportin tiedon määrä ja laatu kertoo yhtä paljon itse raportoijasta kuin itse bugista. Vihaiset, lyhyet bugit ("Tämä funktio on syvältä!") kertoo kehittäjille, että sinulla oli huono päivä, mutta ei pajona muuta. Bugi ja laaja konteksti tekee helpommaksi sen toistamisen ja ansaitsee kaikkien kunioituksen, vaikka se pysäyttäisi julkaisun.

Bugit ovat kuin keskustelu, kaikki historia kaikkien nähtävillä(with all the history right there in front of everyone). Älä syytä muita tai kiellä bugin olemassaoloa. Pyydä sen sijaan lisää tietoa tai mieti, mitä sinulta olisi voinut jäädä huomaamatta.

Bugin statuksen muuttaminen *Avoimesta* *Suljetuksi* on julkinen kannanotto mitä ajattelet bugista. Ajan käyttäminen selostamiseen, miksi bugi pitäisi sulkea tulee säästämään monia tunteja myöhemmin kun päätös pitää oikeuttaa turhautuneille managereille ja asiakkaille. Bugin prioriteetin muuttaminen on samankaltainen julkinen kannanotto ja vain koska se on triviaalia sinulle, ei tarkoita, ettei se estäisi jotakuta muuta käyttämästä tuotetta.

Älä ylikuormita(overload) bugin kenttiä omiin tarkoituksiisi. Lisäämällä "ELINTÄRKEÄ:" bugin otsikkokenttään saattaa helpottaa sinua järjestelemään tulokset jossain raportissa, mutta lopulta muut kopioivat ja kirjoittavat sen väärin, tai heidän tarvitseee poistaa se jostain raportista. Käytä sen sijaan uutta arvoa tai kenttää ja dokumentoi miten kenttää pitäisi käyttää, jotta muiden ei tarvitse toistaa itseään.

Varmista, että kaikki tietävät miten löytää bugit, joita tiimin on tarkoitus tällä hetkellä korjata. Tämän saa yleensä tehtyä julkisellä kyselyllä, jolla on itsestäänselvä nimi. Varmista että kaikki käyttävät samaa kyselyä, äläkä muuta tätä kyselyä ilman tiimin tiedottamista, että muutat kaikkien tehtäviä.

Lopuksi, muista, että bugi ei ole standardoitu työmäärän yksikkö sen enempää kuin yksi rivi koodia on tarkka vaivannäön määrä.

Alkuperäinen kirjoittaja [Matt Doar](http://programmer.97things.oreilly.com/wiki/index.php/Matt_Doar)