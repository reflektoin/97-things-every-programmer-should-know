# �l� Toista Itse�si (D

Kaikista ohjelmoinnin periaatteista, �l� Toista Itse�si(DRY, Don't Repeat Yourself), on ehk� kaikista t�rkein(most fundamental). Periaatteen muotoilivat Andy Hunt ja Dave Thomas kirjassaan *The Pragmatic Programmer* ja se on useiden muiden ohjelmointik�yt�nt�jen ja suunnittelumallien taustalla. Kehitt�j�, joka oppii tunnistamaan p��llekk�isyydet(duplication) ja ymm�rt�� kuinka poistaa kunnollisilla k�yt�nn�ill� ja abstraktioilla voi tuottaa paljon siistimp�� koodia kuin henkil�, joka jatkuvasti aiheuttaa lis�� tarpeetonta toistoa sovelluksessa.

Toisto on hukkaa
--

Jokaista rivi�, joka laitetaan sovellukseen, tulee yll�pit�� ja ne ovat tulevaisuudessa potentiaalisia bugeja. Toisto tarpeettomasti turvottaa(bloats) koodikantaa aiheuttaen enemm�n mahdollisuuksia bugeille, sek� lis�� vahingonomaista monimutkaisuutta(accidental complexity) j�rjestelm��n. Turvotus(the bloat), jonka toisto lis�� j�rjestelm��n vaikeuttaa kehitt�jien ty�t� hankaloittamalla j�rjestelm�n kokonaisvaltaista ymm�rt�mist�, tai varmistumista siit�, moneenko paikkaan muutos t�ytyy lis�t�. �TI(engl. DRY. Don't Repeat Yourself) vaatii, ett� "jokainen tiedonpala t�ytyy olla esitetty kertaalleen ja yksiselitteisesti j�rjestelm�ss�."

Prosessissa tapahtuva toisto vaatii automatisointia
--

Monet ohjelmistotuotannon prosessit ovat toistuvia ja helposti automatisoitavissa. DRY-periaate p�tee sek� n�iss� konteksteissa kuin sovelluksen l�hdekoodissa. Manuaalinen testaus on hidasta, virhealtista ja hankala toistaa, joten automaattisia testipaketteja tulisi k�ytt�� mahdollisuuksien mukaan. Ohjelmiston integrointi voi olla aikaa viev�� ja virhealtista k�sin suoritettuna, joten kokoonpanoprosessi(build process) pit�isi ajaa mahdollisimman usein, ideaalitapauksessa joka muutoksen yhteydess�(every check-in). Hankala manuaalinen prosessi tulisi automatisoida ja standardisoita, mik�li se on mahdollista. Tavoite on varmistaa, ett� on vain yksi tapa suorittaa teht�v� ja ett� se olisi mahdollisimman kivutonta.

Toisto logiikassa vaatii absrahointia
--

Toisto logiikassa voi ilmet� monin tavoin. Kopioi-ja-liit� *if-then* tai *switch-case* logiikka on yksi helpoimmista havaita ja korvata. Monien suunnittelumallien eksplisiittinen tavoite on v�hent�� tai poistaa sovelluslogiikan toistoa. Jos olio tyypillisesti vaatii useiden asioiden tapahtuneen ennen kuin sit� voidaan k�ytt��, t�m� voidaan saavuttaa Abstract Factorylla tai Factory-metodilla. Jos oliosta on monia muunnelmia sen k�ytt�ytymisess�, n�m� k�ytt�ytymiset voidaan lis�t� k�ytt�en Strategy-mallia suuren *if-then* -rakenteen sijaan. Itse asiassa  suunnittelumallien muotoilu itsess��n on yritys v�hent�� toistoa ongelmien ratkomisessa ja keskustella ratkaisutavoista. T�m�n lis�ksi, DRY:ta voidaan soveltaa rakenteisiin, kuten tietokanta-skeemoihin, josta syntyy normalisointi.

Periaatteen asia(A Matter of principle)
--

Muut ohjelmistoperiaatteet liittyv�t my�s DRY:hin. Kerran Ja vain Kerran -periaate(Once and Only Once), joka p�tee koodin mahdollistamaan toiminnallisuuteen(functional behaviour of code) voidaan ajatella DRYn osajoukkona. Avoin/Suljetty -periaate(Open/Closed), joka sanoo "ohjelmistokappaleiden tulisi olla avoimia laajennuksille, mutta suljettuja muokkaamiselle" toimii vain jos DRY:ta noudatetaan. Samoin, laajalti tunnettu Single Responsibility -periaate vaatii, ett� luokalla on "vain yksi syy muuttua", nojaa DRY:hin.

Kun sit� noudetaan rakenteessa, logiikassa, prosesseissa ja toiminnallisuuksissa, DRY-periaate tarjoaa perustavanlaatuisen ohjenuoran ohjelmistokehitt�jille ja auttaa luomaan yksinkertaisempia, yll�pidett�v�mpi� ja laadukkaampia sovelluksia. Vaikka on tilanteita, joissa toisto voi olla tarpeen suorituskyvyn tai muiden vaatimuksien saavuttamiseksi, sit� pit�isi k�ytt�� vain kun se suoraan ratkaisee varsinaisen, eik� keksityn ongelman.

Alkuper�inen kirjoittaja [Steve Smith](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Smith)