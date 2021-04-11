# Isot Yhteenliittyvät Tiedot Kuuluvat Tietokantaan

Jos sovelluksesi käsittelee laajaa, pysyvää, yhteen liittyviä tietoelementtejä, älä epäroi sijoittaa niitä relaatiotietokantaan. Ennen vanhaan RDBMS:t olivat kalliita, harvinaisia, monimutkaisia ja kankeita petoja. Se ei enää pidä paikkansa. Nykyisin RDBMS-järjestelmiä on helppo löytää - todennäköisesti käyttämäsi järjestelmässä on jo muutama sellainen asennettuna. Jotkut relaatiotietokannat, kuten MySQL ja PostgreSQL ovat avoimen lähdekoodin ohjelmistoja, joten hinta ei ole enää ongelma. Mikä parempaa, niin sanotut sulautetut tietokannat(embedded database systems) voidaan linkata kirjastoina suoraan sovellukseesi, ilman järjestelemistä tai hallinnointia - kaksi merkittävää avoimen lähdekoodin ohjelmistoa on SQLite ja HSQLDB. Nämä järjestelmät ovat erittäin suorituskykyisiä.

Jos sovelluksesi data on isompi kuin järjestelmäsi RAM, niin indeksoitu RDBMS taulu suoriutuu suuruusluokkia paremmin kuin kirjastosi map-tietorakenne, joka roskaa virtuaalimuistin sivut. Modernit tietokannat pystyvät kasvamaan tarpeidesi mukaan. Asianmukaisella työllä voit tarpeen vaatiessa skaalata sulautetusta tietokannasta isompaan tietokantajärjstelmään. Myöhemmin voit vaihtaa ilmaisesta avoimen lähdekoodin tuotteesta paremmin tuettuun tai tehokkaampaan patentoituun(proprietary) järjestelmään.

Kun olet päässyt perille SQL:stä, tietokantaan perustuvien sovellusten tekeminen on mukavaa. Kun olet tallentanut normalisoidun datan tietokantaan, siitä on helppo poimia tehokkaasti tietoja helposti luettavalla SQL-kyselyllä; ei ole tarvetta kirjoittaa monimutkaista koodia. Samaan tapaan, yksi SQL-komento voi tehdä monimutkaisia muutoksia dataan. Yksittäismuutoksiin, esimerkiksi tapaan järjestää pysyvä data, sinun ei edes tarvitse kirjoittaa koodia: Käynnistä vain tietokannan suora SQL-rajapinta. Tämä sama rajapinta sallii kyselyillä kokeilut, ohittaen perinteisten ohjelmointikielien käännös-muokkaus -syklin.

Toinen RDBMS:n hyöty koskee data elementtien suhteiden hallintaa. Voit kuvata datasi eheys(consistency)-rajoitukset deklaratiivisesti, välttäen roikkuvat(dangling) osoittimimet jos unohdat päivittää datasi rajatapauksessa. Voit esimerkiksi määrittää, että jos käyttäjä poistetaan, niin hänen lähettämät viestit tulee myös poistaa.

Voit myös luoda halutessasi suorituskykyisiä linkkejä kannassa olevien kokonaisuuksien(entity) välille luomalla uuden indeksin. Ei ole tarvetta suorittaa kallista ja laajaa luokkien kenttien(class fields) uudelleenmuotoilua(refactoring). Lisäksi, tietokannan ympäri koodaaminen sallii monien sovellusten pääsyn tietoihisi turvallisesti. Tämä helpottaa sovelluksesi päivittämisen samanaikaista käyttöä tukevaksi(concurrent use) ja voit koodata jokaisen sovelluksesi osan sopivimmalla ohjelmointikielellä ja alustalla. Esimerkiksi, voisit kirjoitttaa web-pohaisen sovelluksesi XML -takaosan(back-end) Javalla, auditointiskriptejä Rubyllä ja visualisointirajapinnan [Processingilla](http://www.processing.org/).

Lopuksi, pidä mielessä, että RDBMS pyrkii optimoimaan SQL-komentosi, sallien sinun keskittyä sovelluksesi toiminnallisuuksiin algoritmien hienosäätämisen sijaan. Kehittyneet tietokantajärjestelmät voivat jopa hyödyntää moniydinprosessoreita selkäsi takana. Ja teknologian parantuessasi järjestelmäsi suorituskykykin paranee.

Kirjoittaja [Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis)