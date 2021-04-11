# Yhden Vastuun Periaate

Yksi hyv�n suunnitelun perusperiaatteista on:

> Ker�� samasta syyst� muuttuvat asiat, ja erota eri syist� muuttuvat asiat.

T�m� periaate tunnetaan usein nimell� *Yhden Vastuun Periaate*(Single responsibility Principle, SRP). Lyhyesti sanottauna, se tarkoittaa modulin luokan tai edes modulin ei pit�isi muuttua kuin yhdest� syyst�. Klassinen esimerkki on luokka, jonka metodit k�sittelev�t liiketoiminnan s��nt�j�, raportteja ja tietokantaa:


```
public class Employee {
  public Money calculatePay() ...
  public String reportHours() ...
  public void save() ...
}
```

Jotkut ohjelmoijat saattavat ajatella, ett� n�iden kolmen funktion laittaminen samaan luokkaan on t�ysin sopivaa. Loppujen lopuksi, luokkien tulee olla kokoelma funktioita, jotka k�sittelev�t yhteisi� muuttujia. Kuitenkin ongelma on, ett� kolme funktiota muuttuvat t�ysin eri syist�. Funktio `calculatePay` muuttuu aina, kun liiketoiminnan s��nt�� maksamiseen liittyen muutetaan. Funktio `reportHours`muuttuu aina, kun joku haluaa raportin eri muodossa. Save-funktio muutuu aina, kun DBAt muuttavat tietokannan skeemaa. N�m� kolme syyt� yhdess� tekev�t `Employee`-luokasta eritt�in alttiin muutoksille(volatile). Sit� muutetaan mist� tahansa mainituista syyst�. Mik� t�rke�mp�� `Employee`-luokan muutokset vaikuttavat my�s siihen kytk�ksiss� oleviin luokkiin.

Hyv� j�restelm�suunnittelu tarkoittaa, ett� erotamme j�rjestelm�n komponentteihin, jotka voidaan siirt�� tuotantoon itsen�isesti. Itsen�inen tuotantoon siirto(independent deployment), ett� jos muutamme yht� komponenttia, niin meid�n ei tarvitse p�ivitt�� muita komponentteja. Kuitenkin, jos muut luokat toisissa komponenteissa k�ytt�v�t paljon `Employee`-luokaa, niin jokainen Employee-luokan muutos todenn�k�isesti pakottaa muiden komponenttien uudelleen k�ytt��nottamisen(deployment); t�m� poistaa komponenttien suunnittelun hy�dyn (tai SOAn jos pid�t trendikk��mm�st� nimest�).

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

Yksinkertainen jaottelu(partitioning) yll� ratkaisee ongelmat. Jokainen luokka sijoitetaan omaan komponenttiinsa. Tai toisin sanoen, kaikki raportoinning luokat menev�t raportointi-komponenttiin. Kaikki tietokantaan liittyv�t luokat menev�t repositorio-komponenttiin. Kaikki liiketoiminnan s��nn�t menev�t liiketoiminnan s��nt�-komponenttiin.

Ter�v� lukija huomaa, ett� ratkaisussa on viel� joitakin riippuvuuksia. Ett� muut luokat ovat riippuvaisia `Employee`-luokasta. Joten jos `Employee`-luokkaa muokataan, muutkin luokat t�ytyy todenn�k�isesti k��nt�� ja ottaa uudelleen k�ytt��n(redeploy). Joten `Employee`-luokkaa ei voi muokata ja ottaa itsen�isesti k�ytt��n. Kuitenkin, toisia luokkia voi muokata ja ottaa itsen�isesti k�ytt��n. Mik��n muutos yhteen niist� ei pakota muiden uudelleenk��nt�miseen ja k�ytt��nottoon. Jopa `Employee` voitaisiin ottaa itsen�isesti k�ytt��n harkitulla *Dependency Inversion Principlen* k�yt�l�, mutta se on [eri kirjan](http://www.amazon.com/dp/0135974445/) aihe.

Harkittu SRPn k�ytt�, eri syist� muuttuvien asioiden erottaminen, on yksi avaimista, joilla luodaan suunnitelmia itsen�isesti k�ytt��notettavien komponenttien tekemiseen.

Kirjoittanut [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)