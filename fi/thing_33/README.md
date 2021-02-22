# Keskeneräinen, lauseita osittain suomentamatta
# Liukuluvut eivät ole reaalilukuja

Liukuluvut eivät ole reaalilukuja matemaattisessa merkityksessä, vaikka niitä kutsutaan *reaali*luvuiksi joissain ohjelmointikielissä, kuten Pascalissa ja Fortranissa. Reaaliluvuilla on ääretön tarkkuus ja ovat siten jatkuvia(continuous) ja ei-häviöllisiä(non-lossy); liukuluvuilla on rajattu tarkkuus, joten ne ovat rajallisia ja ne muistuttavat "huonosti käyttäytyviä" kokonaislukuja, koska ne eivät ole tasaisesti jakautuneet alueelle(range).

Valaistaan esimerkillä, aseta 2147483647 (suurin etumerkillinen 32-bittinen kokonaisluku) 32-bittiseen kaksoistarkkuuden liukuluku -muuttujaan, ja tulosta se. Näet luvun 2147483648. Nyt tulosta `x - 64`. Edelleen 2147483648. Nyt tulosta `x - 65` ja saat 2147483520! Miksi? Koska viereisten floattien väli sillä välillä on 128, ja liukuluku operaatiot pyöristetään lähimpään liukulukuun.

IEEE-liukuluvut ovat fixed-precision numeroita, jotka pohjautuvat 2-kanta tieteelliseen notaatioon: 1.d<sub>1</sub>d<sub>2</sub>...d<sub>p-1</sub> × 2<sup>e</sup>, missä *p* on tarkkuus (24 yksinkertaisen tarkkuuden liukuluvulle, 53 kaksoistarkkuuden liukuluvulle). Kahden peräkkäisen luvun väli on 2<sup>1-p+e</sup>, mikä voidaan turvallisesti approksimoida ε|x|, missä ε on *kone epsilon*https://en.wikipedia.org/wiki/Machine_epsilon (2<sup>1-p</sup>).

Liukuluvun naapuruston välien tietäminen auttaa välttämään klassiset numeeriset kömmähdykset. Esimerkiksi, jos suoritat iteratiivista laskua, esimerkiksi kaavan juuren etsintää, ei ole järkeä pyytää suurempaa tarkkuutta kuin numerojärjestelmä pystyy antamaan. Varmista, että pyytämäsi toleranssi ei ole pienempi kuin spacing(suomeksi?); muuten lasku looppaa ikuisesti.

Koska liukuluvut ovat approksimaatioita reaaliluvuista, tulee väistämättä pieniä virheitä. Tämä virhe, nimeltään *roundoff*, voi johtaa yllättäviin tuloksiin. Kun vähennät lähes samat numberot, esimerkiksi, merkityksellisimmät numerot(most significant digits) mitätöivät toisensa, joten mikä oli vähiten merkityksellinen numero(missä roundoff-virhe sijaitsee) ylennetään merkityksellisimpään asemaan liukuluku-tuloksessa, pohjimmiltaan pilaamaan tulevat laskut(ilmiön termi englanniksi on *smearing*). Sinun täytyy katsoa tarkasti algoritmisi estääksesi *katastrofiset mitätöinnit*. Esimerkiksi, pohdi kaavan *x<sup>2</sup> - 100000x + 1 = 0* ratkaisemista toisen asteen yhtälön ratkaisukaaavalla. Koska lausekkeen *-b + sqrt(b<sup>2</sup> - 4)* operandit ovat lähes samaa suuruusluokkaa(magnitude), voit sen sijaan laskea juuren *r<sub>1</sub> = -b + sqrt(b<sup>2</sup> - 4)*,, ja sitten saada *r<sub>2</sub> = 1/r<sub>1</sub>*, koska mille tahansa toisen asteen yhtälölle, ax2 + bx + c = 0, juuret toteuttavat(satisfy) *r<sub>1</sub>r<sub>2</sub> = c/a*.

Smearing(suomeksi?) voi esiintyä hienovaraisemmillakin tavoilla. Oletataan, että kirjasto laskee naiivisti *e<sup>x</sup>* kaavalla *1 + x + x<sup>2</sup>/2 + x<sup>3</sup>/3!  + ...*. Tämä toimii hyvin positiivisille *x*, mutta mieti mitä tapahtuu, kun *x* on iso negatiivinen numero. Samaa suuruusluokkaa olevat termit johtavat isoihin positiivisiin numeroihin, ja odd-powered suuruusluokkien numerot eivät edes vaikuta lopputulokseen. Ongelmana on, että roundoff isoille positiivisille termeille on digit positionissa paljon suurempi merkitys kuin oikeassa vastauksessa(tarkasta virke!). Vastaus hajaantuu kohti positiivista äärettömyyttä! Ratkaisu on myös yksinkertainen: negatiiviselle *x*, laske *e<sup>x</sup> = 1/e<sup>|x|</sup>*.

Pitäisi olla sanomattakin selvää, että sinun ei pitäisi käyttää liukulukuja talouden sovelluksissa - sitä varten on desimaali-luokat kielissä kuten Python ja C#. Liukuluvut on tarkoitettu suorituskykyiseen tieteelliseen laskentaan. Mutt suorityskyky on arvotonta ilman tarkkuutta, joten muista pyöristysvirheiden aiheuttaja ja ohjelmoi sen mukaisesti!

Alkuperäinen kirjoittaja [Chuck Allison](http://programmer.97things.oreilly.com/wiki/index.php/Chuck_Allison)