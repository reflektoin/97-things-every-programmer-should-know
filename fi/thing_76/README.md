# Yhden Vastuun Periaate

Yksi hyvän suunnitelun perusperiaatteista on:

> Kerää samasta syystä muuttuvat asiat, ja erota eri syistä muuttuvat asiat.

Tämä periaate tunnetaan usein nimellä *Yhden Vastuun Periaate*(Single responsibility Principle, SRP). Lyhyesti sanottauna, se tarkoittaa modulin luokan tai edes modulin ei pitäisi muuttua kuin yhdestä syystä. Klassinen esimerkki on luokka, jonka metodit käsittelevät liiketoiminnan sääntöjä, raportteja ja tietokantaa:


```
public class Employee {
  public Money calculatePay() ...
  public String reportHours() ...
  public void save() ...
}
```

Jotkut ohjelmoijat saattavat ajatella, että näiden kolmen funktion laittaminen samaan luokkaan on täysin sopivaa. Loppujen lopuksi, luokkien tulee olla kokoelma funktioita, jotka käsittelevät yhteisiä muuttujia. Kuitenkin ongelma on, että kolme funktiota muuttuvat täysin eri syistä. Funktio `calculatePay` muuttuu aina, kun liiketoiminnan sääntöä maksamiseen liittyen muutetaan. Funktio `reportHours`muuttuu aina, kun joku haluaa raportin eri muodossa. Save-funktio muutuu aina, kun DBAt muuttavat tietokannan skeemaa. Nämä kolme syytä yhdessä tekevät `Employee`-luokasta erittäin alttiin muutoksille(volatile). Sitä muutetaan mistä tahansa mainituista syystä. Mikä tärkeämpää `Employee`-luokan muutokset vaikuttavat myös siihen kytköksissä oleviin luokkiin.

Hyvä järestelmäsuunnittelu tarkoittaa, että erotamme järjestelmän komponentteihin, jotka voidaan siirtää tuotantoon itsenäisesti. Itsenäinen tuotantoon siirto(independent deployment), että jos muutamme yhtä komponenttia, niin meidän ei tarvitse päivittää muita komponentteja. Kuitenkin, jos muut luokat toisissa komponenteissa käyttävät paljon `Employee`-luokaa, niin jokainen Employee-luokan muutos todennäköisesti pakottaa muiden komponenttien uudelleen käyttöönottamisen(deployment); tämä poistaa komponenttien suunnittelun hyödyn (tai SOAn jos pidät trendikkäämmästä nimestä).

```
public class Employee {
  public Money calculatePay() ...
}
public class EmployeeReporter {
  public String reportHours(Employee e) ...
}
public class EmployeeRepository {
  public void save(Employee e) ...
}
```

Yksinkertainen jaottelu(partitioning) yllä ratkaisee ongelmat. Jokainen luokka sijoitetaan omaan komponenttiinsa. Tai toisin sanoen, kaikki raportoinning luokat menevät raportointi-komponenttiin. Kaikki tietokantaan liittyvät luokat menevät repositorio-komponenttiin. Kaikki liiketoiminnan säännöt menevät liiketoiminnan sääntö-komponenttiin.

Terävä lukija huomaa, että ratkaisussa on vielä joitakin riippuvuuksia. Että muut luokat ovat riippuvaisia `Employee`-luokasta. Joten jos `Employee`-luokkaa muokataan, muutkin luokat täytyy todennäköisesti kääntää ja ottaa uudelleen käyttöön(redeploy). Joten `Employee`-luokkaa ei voi muokata ja ottaa itsenäisesti käyttöön. Kuitenkin, toisia luokkia voi muokata ja ottaa itsenäisesti käyttöön. Mikään muutos yhteen niistä ei pakota muiden uudelleenkääntämiseen ja käyttöönottoon. Jopa `Employee` voitaisiin ottaa itsenäisesti käyttöön harkitulla *Dependency Inversion Principlen* käytölä, mutta se on [eri kirjan](http://www.amazon.com/dp/0135974445/) aihe.

Harkittu SRPn käyttö, eri syistä muuttuvien asioiden erottaminen, on yksi avaimista, joilla luodaan suunnitelmia itsenäisesti käyttöönotettavien komponenttien tekemiseen.

Kirjoittanut [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)