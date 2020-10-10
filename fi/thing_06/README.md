# Ennen Kuin Refaktoroit

Jossain vaiheessa jokaisen ohjelmoijan täytyy refaktoroida koodia. Mutta ennen kuin refaktoroit, mieti seuraavaa asiaa, koska tämä se voi säästää paljon sinun ja muiden aikaa (ja tuskaa):

- *Paras lähestymistapa rakennemuutokseen alkaa ymmärtämällä olemassaoleva koodi ja sille tehdyt testit.* Tämä auttaa sinua ymmärtämään koodin nykyiset vahvuudet ja heikkoudet. Täten voit varmistaa, että säilytät vahvuudet ja vältät virheet. Me kaikki ajattelemme voivamme tehdä nykyistä paremman järjestelmän... kunnes saamme aikaan jotain ei parempaa — tai jopa huonompaa — kuin aiempi inkarnaatio, koska epäonnistuimme oppimaan nykyisen järjestelmän virheistä.

- *Vältä kiusausta uudelleenkirjoittaa kaikki.* On parempi uudelleenkäyttää koodia niin paljon kuin mahdollista. Oli koodi kuinka rumaa tahansa, se on jo testattu, läpikäyty jne. Vanhan koodin poisheittäminen, erityisesti jos se oli tuotannossa, tarkoittaa kuukausien (tai vuosien) aikana testattua, karaistunutta(battle-hardened) koodia, joka saattoi sisältää tiettyjä kiertotapoja(workaround) ja korjauksia joista et ole tietoinen. Jos et ota tätä huomioon, koodi jonka kirjoitat saattaa sisältää samat mysteeriset viat, jotka oli korjattu vanhassa koodissa. Tämä tuhlaa paljon aikaa, vaivaa ja vuosien saatossa kertynyttä tietämystä.

- *Monta pientä muutosta on parempi kuin yksi massiivinen muutos.* Pienet muutokset sallivat vaikutusten mittaamisen helpommin palautteen kautta, kuten esimerkiksi testien. Ei ole kivaa nähdä sadan testin epäonnistuneen muutoksen jälkeen. Tämä johtaa turhautumiseen ja paineeseen, joka voi johtaa huonoihin päätöksiin. Muutama epäonnistunut testi on helppo käsitellä ja tarjoaa helpomman lähestymistavan.

- *Jokaisen iteraation jälkeen on tärkea varmistaa, että olemassaolevat testit menevät läpi.* Lisää uusia testejä jos nykyiset testit eivät riitä kattamaan tekemiäsi muutoksia. Älä jätä pois vanhan koodin testejä ilman harkintaa. Pintapuolisesti kyseiset testit eivät välttämättä ole sovellettavissa uuteen suunnitelmaasi, mutta se voi olla sen arvoista yrittää ymmärtää, miksi kyseiset testit oli lisätty.

- *Omien mieltymysten ja egon ei pitäisi häiritä.* Jos jokin ei ole rikki, miksi korjata se? Se että koodin tyyli ja rakenne eroaa mieltymyksistäsi ei ole kunnollinen syy refaktorointiin. Ajattelu, että pystyt ratkaisemaan asian paremmin kuin aiempi ohjelmoija ei myöskään ole kunnollinen syy.

- *Uusi teknologia on riittämätön syy refaktorointiin.* Yksi huonoimmista syistä refaktoroida on, että nykyinen koodi jäljessä nykyisistä hienoista teknologioista ja uskomme, että uusi kieli tai ohjelmistokehys voi ratkaista asiat paljon elegantimmin. Ellei kustannus-hyötyanalyysi näytä uuden kielen tai ohjelmistokehyksen tuovan huomattavia parannuksia toiminnallisuuteen, ylläpidettävyyteen tai tuottavuuteen, on paras jättää asiat niin kuin ne ovat.

- *Muista, että ihmiset tekevät virheitä.* Rakennemuutokset eivät aina takaa, että uusi koodi on parempaa, tai edes yhtä hyvää, kuin aiempi yritys. Olen nähnyt ja osallistunut useisiin epäonnistuneisiin rakennemuutosyrityksiin. Se ei ollut kaunista, mutta se oli inhimillistä.

Alkuperäinen kirjoittaja [Rajith Attapattu](http://programmer.97things.oreilly.com/wiki/index.php/Rajith_Attapattu)