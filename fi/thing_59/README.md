# Polymorfismin Mahdollisuudet

Polymorfismi on yksi olio-ohjelmoinnin perusajatuksista. Sana, joka on otettu kreikasta tarkoittaa monia (*poly*) muotoja (*morph*). Ohjelmoinnin kontekstissa polymorfismi viittaa tietyn luokan monenlaisiin olioihin tai metodeihin. Mutta polymorfismi ei koske vain vaihtoehtoisia toteutuksia. Varovasti käyttäen, polymorfismi luo pieniä lokalisoituja ajokonteksteja, jotka antavat meidän työskennelä ilman jaarittelevia(verbose) *if-then-else* -lohkoja. Siinä, missä kontekstissa oleminen sallii oikean asian tekemisen suoraan, kontekstin ulkopuolella oleminen pakottaa meidät järjestelmään sen niin, että voimme tehdä oikean asian. Vaihtelevien toteutusten varovaisella käytöllä, voimme napata kontekstin, joka auttaa meitä tuottamaan vähemmän koodia, joka on luettavampaa. Tämä on paras demonstroida koodilla, kuten seuraavalla (epärealistisen) yksinkertaisella ostoskorilla:

```
public class ShoppingCart {
    private ArrayList<Item> cart = new ArrayList<Item>();
    public void add(Item item) { cart.add(item); }
    public Item takeNext() { return cart.remove(0);  }
    public boolean isEmpty() { return cart.isEmpty(); }
}
```

Sanotaan, että verkkokauppasi tarjoaa esineitä, jotka voidaan ladata ja esineitä, jotka tulee tomiittaa. Rakennetaan toinen olio, joka tukee näitä operaatioita:

```
public class Shipping {
    public boolean ship(Item item, SurfaceAddress address) { ...
 }
    public boolean ship(Item item, EMailAddress address) { ...
 }
}
```

Kun asiakas on suorittanut ostokset, meidän täytyy toimittaa tavarat:


```
while (!cart.isEmpty()) {
    shipping.ship(cart.takeNext(), ???);
}
```

Parametri *???* ei ole mikään hieno elvis-operaattori, se kysyy, pitäisikö minun lähettää asia sähköpostilla vai postitse? Vastauksen vaatimaa kontekstia ei ole enää olemassa. Olisimme voineet napata toimitustavan booleaniin tai enumiin ja käyttää *if-then-else*ä täyttääksemme puuttuvan parametrin. Toinen ratkaisu olisi luoda kaksi luokkaa, jotka laajentavat Item-luokkaa. Kutsutaan näitä luokiksi DownloadableItem ja SurfaceItem. Nyt kirjoitetaan hieman koodia. Nostan Item-luokan rajapinnaksi, joka tarjoaa yhden metodin, ship. Toimittaaksemme ostoskorin sisällön, kutsumme `item.ship(shipper)`. Luokat `DownloadableItem` ja `SurfaceItem` molemmat toteuttavat metodin ship.

```
public class DownloadableItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getEmailAddress());
    }
}
public class SurfaceItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getSurfaceAddress());
    }
}
```

Tässä esimerkissä olemme delegoineet vastuun `Shipping`in kanssa työskentelemisen jokaiselle Itemille. Koska jokainen esine tietää, miten se olisi parasta toimittaa, tämä järjestely välttää *if-then-else*n käyttämisen. Koodi myös demostroi kahden mallin käyttämistä, jotka usein toimivat hyvin yhdessä: Komento ja Double Dispatch. Näiden mallien tehokas käyttä vaatii polymorfismin harkittua käyttöä. Kun niin tehdään, *if-then-else* -lohkojen käyttö koodissasi vähenee.

Vaikka on tapauksia, joissa on käytännöllisempää käyttää *if-then-else*ä polymorfismin sijaan, useimmiten polymorfinen ohjelmointitapa tuottaa pienempää, luettavampaa ja vähemmän hauraan koodikannan. Menetettyjen mahdollisuuksien laskeminen onnistuu yksinkertaisesti laskemalla koodimme *if-then-else* -lauseiden määrä.

Kirjoittanut [Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine)