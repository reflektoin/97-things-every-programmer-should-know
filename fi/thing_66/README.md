# Estä Virheitä

Virheviestit ovat kaikista tärkeimpiä vuorovaikutuksia käyttäjän ja muun järjestelmän välillä. Ne tapahtuvat kommunikaatio käyttäjän ja järjestelmän välillä on katkeamassa.

On helppo ajatella virheen aiheutuneen käyttäjän antamasta väärästästä syötteestä. Mutta ihmiset tekevät virheitä ennustettavin, systemaattisin tavoin. Joten on mahdollista 'debugata' käyttäjän ja järjestelmän välistä kommunikaatiota, kuin debuggaisit järjestelmän muiden komponenttien välistä kommunikaatiota.

Sanotaan, että haluat käyttäjän syöttävän päivämäärän tietyltä aikaväliltä. Sen sijaan, että annat käyttäjän syöttää minkä tahansa päivämäärän, on parempi tarjota ainoastaan sallitut päivämärät näyttävä lista tai kalenteri. Tämä poistaa käyttäjän mahdollisuuden syöttää halutun alueen ulkopuolella olevan päivämäärän.

Muotoiluvirheet ovat toinen yleinen ongelma. Esimerkiksi jos käyttäjälle esitetään päivämäärä-kenttä ja hän syöttää yksiselitetisen päivämäärän, kuten "Kesäkuu 6, 2012", on kohtuutonta hylätä se väärässä muodossa olemisen takia(sen olisi esimerkiksi pitänyt olla "PP/KK/VVVV"). Sitäkin pahempaa on hylätä "29 / 07 / 2012" sen sisältämien välilyöntien takia - tämänkaltainen ongelma on erityisen hankala käyttäjien ymmärtää, koska päivämäärä vaikuttaa olevan halutussa muodossa.

Tämä virhe ilmenee, koska on helpompi hylätä päivämäärä, kuin jäsentää(parse) kolme tai neljä yleisintä päivämäärän muotoa. Tämänkaltaiset pikkumaiset virheet johtavat käyttäjän turhautumiseen, mikä taas johtaa seuraaviin virheisiin käyttäjän menettäessä keskittymistään. Kunnioita datan sijaan käyttäjien tapojan syöttää tietoa.

Toinen tapa välttää muotoiluvirheitä on tarjota vinkkejä - esimerkiksi näyttää kentässä tekstillä haluttu muoto ("PP/KK/YYYY"). Toinen vihje voisi olla jakaa kenttä kolmeen kahden, kahden ja neljän merkin pituisiin laatikkoihin.

Vihjeet ovat ohjeista poikkeavia: Vihjeet ovat yleensä vihjauksia(cues tend to be hints); ohjeet ovat monisanaisempia. Vihjeet esitetään vuorovaikutushetkellä, ohjeet esitetään ennen vuorovaikutusta. Vihjeet tarjoavat kontekstia; ohjeet määräävät käyttötapaa.

Yleisesti, ohjeet ovat tehottomia virheiden estämisessä. Käyttäjillä on tapana olettaa käyttöliittymien toimivan heidän aiempien kokemusten tavoin ("Varmastihan kaikki tietävät mitä 'Kesäkuu 6, 2012' tarkoittaa?"). Joten ohjeet jäävät lukematta. Vihjeet ohjaavat käyttäjiä välttämään virheitä.

Toinen tapa välttää virheitä on tarjota oletuksia. Esimerkiksi käyttäjät tyypillisesti syöttävät arvoja *tänään*, *huomenna*, *syntymäpäivänäni*, *deadlinena* tai *päivä, jona käytin viimeksi tätä lomaketta*. Kontekstista riippuen, jokin näistä on todennäköisesti hyvä oletusarvo.

Mikä ikinä syy onkin, järjestelmien pitäisi selvitä virheistä. Voit tehdä sen tarjoamalla *kumoa*-vaihtoehdon kaikille toiminnoille - etenkin käyttäjän tietoja tuhoaville tai muuttaville toiminnoille. Lokitus(logging) ja *kumoa*-komentojen analysointi voi myös kertoa, missä kohtaa käyttöliittymä johtaa käyttäjät alitajuisesti tekemään virheitä, kuten jatkuvasti klikkaamaan 'väärää' painiketta. Nämä virheet aiheutuvat usein harhaanjohtavista vihjeistä tai vuorovaikutusten sarjasta, jotka voidaan suunnitella uudelleen virheiden välttämiseksi.

Minkä lähestymistavan valitsetkaan, suurin osa virheistä on systemaattisia, joka aiheutuu väärinymmärryksestä käyttäjän ja ohjelmiston välillä. Ymmärrys käyttäjän tavasta ajatella, tulkita tietoa, tehdä päätöksia ja syöttää tietoa, auttaa sinua korjaamaan ohjelmasi ja käyttäjiesi vuorovaikutusta.

Kirjoittanut [Giles Colborne](http://programmer.97things.oreilly.com/wiki/index.php/Giles_Colborne)
