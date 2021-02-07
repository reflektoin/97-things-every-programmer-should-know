# Älä Toista Itseäsi

Kaikista ohjelmoinnin periaatteista, Älä Toista Itseäsi(DRY, Don't Repeat Yourself), on ehkä kaikista tärkein(most fundamental). Periaatteen muotoilivat Andy Hunt ja Dave Thomas kirjassaan *The Pragmatic Programmer* ja se on useiden muiden ohjelmointikäytäntöjen ja suunnittelumallien taustalla. Kehittäjä, joka oppii tunnistamaan päällekkäisyydet(duplication) ja ymmärtää kuinka poistaa kunnollisilla käytännöillä ja abstraktioilla voi tuottaa paljon siistimpää koodia kuin henkilö, joka jatkuvasti aiheuttaa lisää tarpeetonta toistoa sovelluksessa.

Toisto on hukkaa
--

Jokaista riviä, joka laitetaan sovellukseen, tulee ylläpitää ja ne ovat tulevaisuudessa potentiaalisia bugeja. Toisto tarpeettomasti turvottaa(bloats) koodikantaa aiheuttaen enemmän mahdollisuuksia bugeille, sekä lisää vahingonomaista monimutkaisuutta(accidental complexity) järjestelmään. Turvotus(the bloat), jonka toisto lisää järjestelmään vaikeuttaa kehittäjien työtä hankaloittamalla järjestelmän kokonaisvaltaista ymmärtämistä, tai varmistumista siitä, moneenko paikkaan muutos täytyy lisätä. ÄTI(engl. DRY. Don't Repeat Yourself) vaatii, että "jokainen tiedonpala täytyy olla esitetty kertaalleen ja yksiselitteisesti järjestelmässä."

Prosessissa tapahtuva toisto vaatii automatisointia
--

Monet ohjelmistotuotannon prosessit ovat toistuvia ja helposti automatisoitavissa. DRY-periaate pätee sekä näissä konteksteissa kuin sovelluksen lähdekoodissa. Manuaalinen testaus on hidasta, virhealtista ja hankala toistaa, joten automaattisia testipaketteja tulisi käyttää mahdollisuuksien mukaan. Ohjelmiston integrointi voi olla aikaa vievää ja virhealtista käsin suoritettuna, joten kokoonpanoprosessi(build process) pitäisi ajaa mahdollisimman usein, ideaalitapauksessa joka muutoksen yhteydessä(every check-in). Hankala manuaalinen prosessi tulisi automatisoida ja standardisoita, mikäli se on mahdollista. Tavoite on varmistaa, että on vain yksi tapa suorittaa tehtävä ja että se olisi mahdollisimman kivutonta.

Toisto logiikassa vaatii abstrahointia
--

Toisto logiikassa voi ilmetä monin tavoin. Kopioi-ja-liitä *if-then* tai *switch-case* logiikka on yksi helpoimmista havaita ja korvata. Monien suunnittelumallien eksplisiittinen tavoite on vähentää tai poistaa sovelluslogiikan toistoa. Jos olio tyypillisesti vaatii useiden asioiden tapahtuneen ennen kuin sitä voidaan käyttää, tämä voidaan saavuttaa Abstract Factorylla tai Factory-metodilla. Jos oliosta on monia muunnelmia sen käyttäytymisessä, nämä käyttäytymiset voidaan lisätä käyttäen Strategy-mallia suuren *if-then* -rakenteen sijaan. Itse asiassa  suunnittelumallien muotoilu itsessään on yritys vähentää toistoa ongelmien ratkomisessa ja keskustella ratkaisutavoista. Tämän lisäksi, DRY:ta voidaan soveltaa rakenteisiin, kuten tietokanta-skeemoihin, josta syntyy normalisointi.

Periaatteen asia(A Matter of principle)
--

Muut ohjelmistoperiaatteet liittyvät myös DRY:hin. Kerran Ja vain Kerran -periaate(Once and Only Once), joka pätee koodin mahdollistamaan toiminnallisuuteen(functional behaviour of code) voidaan ajatella DRYn osajoukkona. Avoin/Suljetty -periaate(Open/Closed), joka sanoo "ohjelmistokappaleiden tulisi olla avoimia laajennuksille, mutta suljettuja muokkaamiselle" toimii vain jos DRY:ta noudatetaan. Samoin, laajalti tunnettu Single Responsibility -periaate vaatii, että luokalla on "vain yksi syy muuttua", nojaa DRY:hin.

Kun sitä noudetaan rakenteessa, logiikassa, prosesseissa ja toiminnallisuuksissa, DRY-periaate tarjoaa perustavanlaatuisen ohjenuoran ohjelmistokehittäjille ja auttaa luomaan yksinkertaisempia, ylläpidettävämpiä ja laadukkaampia sovelluksia. Vaikka on tilanteita, joissa toisto voi olla tarpeen suorituskyvyn tai muiden vaatimuksien saavuttamiseksi, sitä pitäisi käyttää vain kun se suoraan ratkaisee varsinaisen, eikä keksityn ongelman.

Alkuperäinen kirjoittaja [Steve Smith](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Smith)
