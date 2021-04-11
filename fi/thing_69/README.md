# Irroita Ote Hiirestä ja Poistu Näppäimistön Luota

Olet keskittynyt ongelmaan tuntien ajan, eikä ratkaisua ole näkyvissä. Joten nouset jaloittelemaan, tai menet juoma-automaatille ja palatessasi vastaus tulee ilmiselväksi.

Kuulostaako tilanne tutulta? Mietitkö koskaan, miksi niin tapahtuu? Temppu on, että koodatessasi looginen osa aivoistasi on aktiivinen ja luova puoli on sammunut. Se ei voi esittää mitään, ennen kuin looginen puoli pitää tauon.

Tässä on tosi elämän esimerkki: Siistin perintökoodia(legacy code) ja törmäsin 'mielenkiintoiseen' metodiin. Se oli suunniteltu varmistamaan, että merkkijono sisältää kellonajan oikeassa muodossa *hh:mm:ss xx*, jossa *hh* edustaa tuntia, *mm* edustaa minuutteja, *ss* edustaa sekunteja ja *xx on joko *AM* tai *PM*.

Metodi käytti seuraavaa koodia muuntaakseen kaksi merkkiä (jotka edustivat tunteja) numeroksi ja varmistaakseen sen olevan hyväksyttävissä rajoissa:

```
try {
    Integer.parseInt(time.substring(0, 2));
} catch (Exception x) {
    return false;
}
if (Integer.parseInt(time.substring(0, 2)) > 12) {
    return false;
}
```

Sama esiintyi vielä kahdesti, merkkien offsettiä ja ylärajaa oli muutettu, jotta voitiin testata minuutit ja sekunnit. Metodi päättyi näihin, joilla tarkastettiin AM ja PM:

```
if (!time.substring(9, 11).equals("AM") &
    !time.substring(9, 11).equals("PM")) {
    return false;
}
```

Jos mikään sarjan vertailuista ei epäonnistuisi, palauttaen false, metodi palauttaisi true.

Jos edeltävä koodi vaikuttaa monisanaiselta ja hankalalta seurata, älä huoli. Niin minäkin ajattelin, mikä tarkoitti, että löysin jotain siistittävää. Uudelleenmuotoilin sen ja kirjoitin muutaman yksikkötestin varmistaakseni, että se edelleen toimi.

Saatuani sen valmiiksi, olin tyytyväinen tuloksiin. Uusi versio oli helppolukuinen, puolet pienempi ja tarkempi, koska alkuperäinen koodi testasi vain tuntien, minuuttien ja sekuntien ylärajat.

Seuraavana päivänä valmistautuessani töihin, sain idean: Miksen vahvistaisi merkkijonoa käyttäen säännöllisiä lausekkeita? Kirjoitettuani muutaman minuutin, minulla oli vain yhden rivin pituinen toimiva toteutus. Tässä se on:

```
public static boolean validateTime(String time) {
    return time.matches("(0[1-9]|1[0-2]):[0-5][0-9]:[0-5][0-9] ([AP]M)");
}
```

Tarinan ydin ei ole, että korvasin lopulta 30 riviä koodia yhdellä rivillä. Ydin on koneelta poistumiseen asti, ajattelin ensimmäisen yritykseni olevan paras tapa ratkaista ongelma.

Joten ensi kerran törmätessäsi vaikeaan ongelmaan, tee itsellesi palvelus. Kun ymmärrät ongelman kunnolla, tee jotain aivojesi luovaa puolta käyttävää - piirrä ongelma, kuuntele musiikkia tai käy kävelyllä. Joskus paras tapa ratkaista ongelma on irroittaa ote hiirestä ja siirtyä pois näppäimistön luota.

Kirjoittanut [BurkHufnagel](http://programmer.97things.oreilly.com/wiki/index.php/BurkHufnagel)