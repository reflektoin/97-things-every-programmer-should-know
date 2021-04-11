# Laita Kaikki Versionhallintaan

Laita kaikki projektisi versionhallintaan. Kaikki tarvitsemasi resurssit löytyvät: vapaat työkalut kuten Subversion, Git, Mercurial ja CVS; runsaasti levytilaa; halpoja ja tehokkaita palvelimia; verkkoyhteys; ja jopa projektien isännöinti(hosting). Versionhallinnan asentamisen jälkeen sinun tarvitsee vain käyttää oikeaa komentoa koodisi sisältämässä hakemistossa. Ja on vain kaksi perusoperaatio, jotka sinun tarvitsee opetella: *commit*oit muutoksesi repositorioon ja päivität toimivan versiosi repositorion versiolle.

Kun projektisi on versionhallinnassa, voit tietenkin seurata sen historiaa, kuka kirjoitti mitäkin ja viitata tiedostoon tai projektin versioon yksilöllisellä tunnisteella. Mikä tärkeämpää, voin tehdä rohkeita muutoksia ilman pelkoa - ei enää kommentoitua koodia siltä varalta, että saatat tarvita sitä, koska vanha versio on turvallisesti repositoriossa. Voit (ja sinun pitäisi) tagata julkaisu nimellä, jotta voit helposti palata asiakkaan käyttämään versioon. Voit luoda haaroja(branches) rinnakkaista kehitystä varten: Useimmilla projekteilla on haara aktiiviseen kehitykseen ja yksi tai useampia haaroja tuettujen julkaisujen ylläpitoon.

Versionhallinta minimoi kitkaa kehittäjien välillä. Ohjelmoijien muuttaessa ohjelmiston itsenäisiä osia, nämä muutokset integroidaan lähes taianomaisesti. Astuessaa toistensa varpaille järjestelmä huomaa asian, ilmoittaa heille asista ja sallii heidän sovitella konfliktit. Lisäjärjestelyllä järjestelmä voi ilmoittaa kaikille kehittäjille jokaisesta muutoksen vahvistamisesta(commit), luodakseen yhteisen ymmärryksen projektin etenemisestä.

Kun luot projektin älä pihistele: sijoita *kaikki* projektin resurssit(asset) versionhallintaan. Lähdekoodin lisäksi, lisää dokumentaatio, työkalut, koonti-skriptit, testitapaukset, kuvamateriaali(artwork) ja jopa kirjastot. Koko projektin ollessa turvallisesti repositoriossa(ja säännölliset varmuuskopiot otettuna) kovalevyn menettämisen vaikutukset on minimoitu. Ympäristön luominen uudelle koneelle vaatii ainoastaan projektin hakemisen(checkout) repositoriosta. Tämä yksinkertaistaa koodin jakelua, koontia ja testausta eri alustoilla: jokaisella koneella update-koneoto varmistaa, että käytössä on uusin versio.

Kun olet nähnyt versionhallinnan kanssa työskentelyn kauneuden, muutamien sääntöjen noudattaminen tekee sinusta ja tiimistäsi vielä tehokkaampia:

- Vahvista jokainen looginen muutos erillisenä operaationa. Monien muutosten niputtaminen yhteen commit-komentoon vaikeuttaa niiden selvittämistä tulevaisuudessa. Tämä on erityisen tärkeää, kun teet projektin laajuisia uudelleenmuotoiluita tai tyylin muutoksia, jotka saattavat helposti peittää muita muutoksia.

- Täydennä jokaista commit-viestiä selostavalla viestillä. Kuvaa vähintään, mitä muutit, mutta halutessasi myös kirjata muutoksen syyn, tämä on paras paikka tehdä se.

- Lopuksi, vältä commitoimasta projektin koonnin rikkovaa koodia, muuten sinusta tulee epäsuosittu projektin muiden ohjelmoijien keskuudessa.

Elämä versionhallinnan kanssa on liian hyvää, jotta sen pilaisi muutamalla helposti vältettävällä harha-askeleella.

Kirjoittanut [Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis)