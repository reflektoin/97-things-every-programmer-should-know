# Tee Näkymättömästä Näkyvämpää

Monet näkymättömyyden puolia ylistetään hyvällä syyllä ohjelmistojen periaatteina joita ylläpitää. Terminologiamme on rikas näkymättömyyden metaforista - mekanismin läpinäkyvyys(mechanism transparency) ja tiedon piilottaminen(information hiding) nimetäkseni vain kaksi. Ohjelmistot ja niiden kehittämisen prosessi voi olla, Douglas Adamsia mukaillen, *enimmäkseen läpinäkyvää*:

- Lähdekoodilla ei ole synnynnäistä läsnäoloa, ei synnynnäistä käyttäytymistä eikä se noudata fysiikan lakeja. Se on näkyvää kun lataan sen editoriin, mutta suljettuasi editorin se on poissa. Mietittiessäsi sitä liian pitkään ja, kuten kaatuva puu, jota kukaan ei kuule, alat miettimään onko sitä edes olemassa.

- Käynnissä oleva on läsnä ja sillä on toimintoja, mutta se ei paljasta mitään lähdekoodista, millä se on rakennettu. Googlen kotisivu on miellyttävän yksinkertainen, sen taustalla tapahtuu merkittäviä asioita.

- Jos olet 90% valmis ja olet jumissa viimeisen 10% korjaamisessa, silloin et ole 90% valmis, ethän? Vikojen korjaaminen ei ole edistystä. Sinulle ei makseta vikojen korjaamisesta. Vikojen korjaus(debuggin) on hukkaa. Hukasta on hyvä tehdä näkyvämpää, jotta näet sen ja voit alkaa miettimään hukan välttämästä alusta lähtien.

- Jos projektisi on nähtävästi aikataulussa, mutta viikkoa myöhemmin se on puoli vuotta myöhässä, sinulla on ongelmia, joista suurin ei todennäköisesti ole, että olet puoli vuotta myöhässä, vaan näkymättömyyden voimakentät, jotka piilottavat puolen vuoden myöhästymisen! Näkyvän edistyksen puute on edistyksen puuttumisen synonyymi.

Näkymättömyys voi olla vaarallista. Ajattelet selkeämmin, kun sinulla on jotain konkreettista mietittävää. Hallitset asiat paremmin näkiessäsi ne ja niiden jatkuvat muutokset:

- Yksikkötestien kirjoittaminen tarjoiaa todisteitä, miten helppoa koodiyksikön yksikkötestaaminen on. Se auttaa paljastamaan kehityksen ominaisuuksien läsnäolon (tai puutteet), joita haluaisit sen osoittavan; ominaisuuksien kuten löyhä kytkentä ja suuri koheesio.

- Yksikkötestien suorittaminen esittää todisteita koodin käyttäytymisestä. Se auttaa paljastamaan ajonaikaisten ominaisuuksien läsnäolon (tai puutteet) joita haluaisit sovelluksen osoittavan; ominaisuusten kuten elinvoimaisuus(robustness) ja oikeellisuus.

- Ilmoitustaulujen ja korttien käyttö tekee edistyksestä näkyvää ja konkreettista. Tehtävät voivat olla *Ei aloitettu*, *meneillään*, tai *Valmis* ilman viittauksia piilossa olevaan projektinhallinta-työkaluun, eikä metstästää ohjelmoijia fiktiivisiä tilanneraportteja varten.

- Asteittaisen kehittäminen lisää näkyvyyttä etenemiseen (tai sen puutteeseen) lisäämällä kehityksen todisteiden esiintymistiheyttä. Julkaisukuntoon saatu ohjelmisto paljastaa todellisuuden; arviot eivät.

On parasta kehittää ohjelmistoa runsain säännöllisesti näkyvin todistein. Näkyvyys antaa luottamusta etenemisen olevan aitoa, ei illuusiota, tarkoituksellista ei tarkoituksetonta, toistettavaa eikä sattunmanvaraista.

Kirjoittanut [Jon Jagger](http://programmer.97things.oreilly.com/wiki/index.php/Jon_Jagger)