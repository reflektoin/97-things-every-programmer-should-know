# Toimi harkiten

> *"Mitä teetkin, toimi varovaisesti ja ota huomioon seuraukset" Anon*

Riippumatta miten turvalliselta aikataulu näyttääkään iteraation alussa, et voi välttyä ajoittaisilta aikapaineilta. Jos huomaat joutuvasi valitsemaan kahden tekotavan väliltä, "tee se kunnolla" ja "tee se nopeasi", on usein halu "tehdä se nopeasti" siinä ymmärryksessä, että korjaat sen myöhemmin. Kun teet tällaisen lupauksen itsellesi, tiimillesi ja asiakkaallesi, tarkoitat sitä. Mutta liian usein seuraava iteraatio tuo uusia ongelmia ja sinä keskityt niihin. Tämänkaltaista lykättyä työtä kutsutaan tekniseksi velaksi, eikä se ole ystäväsi. Erityisesti, Martin Fowler kutsuu sitä tietoiseksi tekniseksi velaksi hänen [teknisen velan taksonomiassaan](http://martinfowler.com/bliki/TechnicalDebtQuadrant.html), jota ei pitäisi sekoittaa tahattomaan tekniseen velkaan.

Tekninen velka on kuin laina: Hyödyt siitä lyhyellä aikavälillä, mutta sinun täytyy maksaa korkoa, kunnes se on kokonaan maksettu. Oikopolut koodissa vaikeuttaa toimintojen lisäämistä ja koodin refaktorointia. Ne ovat vikojen ja hauraiden testitapauksien lisääntymispaikkoja. Mitä pidempään sitä on, sitä huonommaksi tilanne menee. Kun viimein ryhdyt tekemään alkuperäistä korjausta, sen päälle saattaa olla tehty monia ei niin hyviä suunnittelupäätöksiä, jotka vaikeuttavat koodin refaktorointia ja korjaamista. Usein asiaa ruvetaan korjaamaan vasta pakon edessä. Ja silloin se on paljon vaikeampi korjata, kun sinulla ei ole aikaa tai riski on suuri.

On aikoja, jolloin sinun joudut aiheuttamaan teknistä velkaa deadlinen takia tai toteuttaaksesi pienen toiminnallisuuden. Koita olla joutumatta tähän tilanteeseen, mutta jos tilaane sitä vaatii, tee se. Mutta (ja tämä on iso MUTTA) sinun täytyy seurava teknisen velan määrää ja maksaa se takaisin nopeasti tai tilanne huonontuu vauhdilla. Tehdessäsi kompromissin, kirjoita tehtävälappu tai kirjaa se tukipyyntöjärjestelmään varmistaaksesi ettei sitä unohdeta.

Jos aikataulutat velanmaksun seuraavaan iteraatioon, sen hinta on minimaalinen. Velan maksamatta jättäminen kasvaa korkoa. Tuota korkoa pitäisi seurata, jotta hinta nähdään. Tämä korostaa  vaikutusta projektin teknisen velan bisnesarvoon ja mahdollistaa tarkoituksenmukaisen takaisinmaksun priorisoinnin. Koron laskemisen ja seurannan tavat riippuvat projektista, mutta sitä tulee seurata.

Maksa tekninen velka niin nopeasti kuin mahdollista. Olisi harkitsematonta tehdä toisin.

Alkuperäinen kirjoittaja [Seb Rose](http://programmer.97things.oreilly.com/wiki/index.php/Seb_Rose)