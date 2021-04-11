# Omista (ja Uudelleenumuotoile) Koonti

Ei ole harvinaista, että tiimeillä, jotka ovat muuten erittäin kurinalaisia ohjelmointikäytännöistä jättää huomiotta koonti-skriptit, joko uskosta niiden merkityksettömyydestä tai pelosta, että ne ovat liian monimutkaisia ja niitä voi käsitellä vain julkaisutekniikan(release engineerin) kultti. Ylläpitämättömät koonti-skriptit duplikaatiolla ja virheillä aiheuttavat samankaltaisia ongelmia kuin huonosti muotoiltu koodi.

Yksi selitys, miksi kurinalaiset, taitavat ohjelmoijat kohtelevat koontia toissijaisena heidän työhönsä on, että koonti-skriptit on usein kirjoitettu eri kielellä kuin lähdekoodi. Toinen syy on, että koonti ei varsinaisesti ole "koodia." Nämä oikeutukset lentää todellisuuden kasvoihin, että suurin osa ohjelmoijista nauttii uusien kielten oppimisesta ja että koonti luo suoritettavat artefaktit kehittäjien ja loppukäyttäjien testattavaksi ja ajettavaksi. Koodi on hyödytöntä ilman koontia ja koonti määrittää sovelluksen komponenttien arkkitehtuurin. Koonti on olennainen osa kehitys-prosessia ja päätökset koontiprosessista voi tehdä koodista ja koodaamisesta yksinkertaisempaa.

Väärillä idiomeilla kirjoitetut koonti-skriptit on hankalia ylläpitää ja mikä tärkeämpää, parantaa. On sen arvoista käyttää osa ajasta ymmärtääkseen oikea tapa tehdä muutos. Viat voivat ilmetä kun sovellus kootaan riippuvuuksien väärällä versiolla tai kun koonnin-aikaiset asetukset ovat väärät.

Perinteisesti testaus on jätetty "Laadunvarmistus"-tiimille. Nyt ymmärrämme ohjelmoitaessa testaamisen tarpeellisuuden toimittaaksemme arvoa ennustettavasti. Samaan tapaan, kehitys-tiimin tulee hallita koonti-prosessi.

Koonnin ymmärtäminen voi yksinkertaistaa kehityksen koko elinkaarta ja vähentää kustannuksia. Helposti ajettava koonti sallii uuden kehittäjän päästä alkuun nopeasti ja helposti. Konfiguroinnin automatisointi koonnissa voi mahdollistaa johdonmukaiset tulokset, kun monet henkilöt työskentelevät projektissa, välttäen "se toimii minulla"-keskusteut. Monet koonnin työkalut sallivat sinun luoda raportteja koodin laadusta, mahdollistaen mahdollisten ongelmien havaitsemisen aikaisin. Käyttämällä aikaa koonnin ymmärtämiseen voit auttaa itseäsi ja kaikkia tiimissäsi. Voit keskittyä ominaisuuksien ohjelmointiin, hyödyttäen sidosryhmiäsi ja tehden työstä nautinnollisempaa.

Opi koonti-prosessistasi riittävästi ymmärtääksesi milloin ja miten tehdä muutoksia. Koonti-skriptit ovat koodia. Ne ovat liian tärkeitä jätettäväksi kenellekään muulle, vaikka ainostaan siitä syystä, että ohjelma ei ole valmis ennen kuin se on koottu. Ohjelmointi ei ole valmis ennen kuin toimiva sovellus on toimitettu.

Kirjoittanut [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)