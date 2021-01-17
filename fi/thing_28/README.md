# Älä Naulaa Ohjelmaasi Pystyasentoon

Kirjoitin kerran vitsinä C++ tietokilpailu, jossa satiirisesti ehdotin seuraavaa strategiaa poikkeustenkäsittelyyn:

> Monilla `try...catch` rakenteilla ympäri koodikantaamme, we joskus pystymme estämään sovelluksiamme sammumasta. Ajattelemme syntyvää tilaa "ruumiin naulaamisen pystyasentoon."

Kevytmielisyydestäni huolimatta todellisuudessa tein yhteenvetoa opetuksesta, jonka sain Katkeran Kokemuksen daamin polvella.

Se oli sovelluksen kantaluokka(base application class) omassa kotitekoisessa C++-kirjastossa. Se oli kärsinyt monien ohjelmoijien sorkkimisesta vuosien varrella: Kenenkään kädet eivät olleet puhtaat. Se sisälsi koodia, joka käsittelee kaikkien muiden poikkeukset. Taking our lead from Yossarian in Catch-22, päätimme, tai koimme (*päätimme* viittaa suurempaan ajatteluun kuin mitä tämän hirviön luomiseen käytettiin), että tämän luokan ilmentymän pitäisi elää ikuisesta tai kuolla yrittäessään.

Tätä varten me punoimme yhteen monia poikkeustenkäsittelijöitä. Me yhtistimme Windowsin strukturoidun poikkeustenkäsittelun natiivilla lajilla (muistatko `__try...__except` C++:ssa? En minäkään). Kun poikkeus tapahtui, me yritimme kutsua sitä uudelleen, muuttaen parametreja(pressing the parameters harder). Taakse katsoessa, tykkään ajatella, että kirjoittaessani sisäistä `try..catch` -käsittelijää toisen catch-lauseen sisälle, jokin itsetietoisuus hiipi ylitseni, että olisin saattanut vahingossa siirtyä hyvien käytäntöjen moottoritieltä aromaattisen, mutta epäterveellisen hulluuden kujalle. Tämä on takautuvaa viisautta.

Lienee tarpeetonta sanoa, kun sovelluksessa jokin tähän luokkaan perustuva asia menee pieleen, niin se katoaa kuin Mafian uhrit telakalla, jättämättä jälkeensä mitään hyödyllistä joka kertoisi mitä tapahtui, poislukien dumppaus-rutiinit, jotka oletettavasti kutsuttiin taltioimaan onnettomuus. Lopulta ymmärsimme, mitä olimme tehneet, ja koimme häpeää. Me korvasimme koko sotkun minimaalisella ja kestävällä raportointimekanismilla. Mutta tämä oli monen kaatumisen jälkeen.

En vaivaisi sinua tällä - koska ketkään eivät varmastikaan ole yhtä tyhmiä kuin me olimme - muuten kuin verkkoväittelyn(online argument) takia, joka minulla oli hetki sitten tyypin kanssa, jonka akateemisen tittelinsä perusteella pitäisi tietää paremmin. Me keskustelimme Java-koodista etä-transaktiossa(remote transaction). Jos koodi epäonnistui, hän väitti, sen pitäisi ottaa kiinni ja estää poikkeus *in situ*. ("Ja sen jälkeen tehdä *mitä* sillä?" kysyin. "Kokata sille lounasta?")

Hän siteerasi UI-suunnittelijoiden sääntöä: ÄLÄ KOSKAAN ANNA KÄYTTÄJÄN NÄHDÄ POIKKEUSRAPORTTIA, ikään kuin tämä olisi ratkaissut asian, suuraakkosina kirjoitettuna ja kaikkea. Pohdin oliko hän vastuussa jostakin niiden sininäyttöisten pankkiautomaattien koodista, joiden kuvat koristavat blogeja ja ovat pysyvästi traumatisoituneita.

Joka tapauksessa, jos tapaat hänet, nyökkää, hymyile, äläkä ota sitä huomioon hivuttautuessasi kohti ovea.

Alkuperäinen kirjoittaja [Verity Stob](http://programmer.97things.oreilly.com/wiki/index.php/Verity_Stob)