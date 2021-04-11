# Polymorfismin Mahdollisuudet

Polymorfismi on yksi olio-ohjelmoinnin perusajatuksista. Sana, joka on otettu kreikasta tarkoittaa monia (*poly*) muotoja (*morph*). Ohjelmoinnin kontekstissa polymorfismi viittaa tietyn luokan monenlaisiin olioihin tai metodeihin. Mutta polymorfismi ei koske vain vaihtoehtoisia toteutuksia. Varovasti k�ytt�en, polymorfismi luo pieni� lokalisoituja ajokonteksteja, jotka antavat meid�n ty�skennel� ilman jaarittelevia(verbose) *if-then-else* -lohkoja. Siin�, miss� kontekstissa oleminen sallii oikean asian tekemisen suoraan, kontekstin ulkopuolella oleminen pakottaa meid�t j�rjestelm��n sen niin, ett� voimme tehd� oikean asian. Vaihtelevien toteutusten varovaisella k�yt�ll�, voimme napata kontekstin, joka auttaa meit� tuottamaan v�hemm�n koodia, joka on luettavampaa. T�m� on paras demonstroida koodilla, kuten seuraavalla (ep�realistisen) yksinkertaisella ostoskorilla:

```
public class ShoppingCart {
    private ArrayList<Item> cart = new ArrayList<Item>();
    public void add(Item item) { cart.add(item); }
    public Item takeNext() { return cart.remove(0);  }
    public boolean isEmpty() { return cart.isEmpty(); }
}
```

Sanotaan, ett� verkkokauppasi tarjoaa esineit�, jotka voidaan ladata ja esineit�, jotka tulee tomiittaa. Rakennetaan toinen olio, joka tukee n�it� operaatioita:

```
public class Shipping {
    public boolean ship(Item item, SurfaceAddress address) { ...
 }
    public boolean ship(Item item, EMailAddress address) { ...
 }
}
```

Kun asiakas on suorittanut ostokset, meid�n t�ytyy toimittaa tavarat:


```
while (!cart.isEmpty()) {
    shipping.ship(cart.takeNext(), ???);
}
```

Parametri *???* ei ole mik��n hieno elvis-operaattori, se kysyy, pit�isik� minun l�hett�� asia s�hk�postilla vai postitse? Vastauksen vaatimaa kontekstia ei ole en�� olemassa. Olisimme voineet napata toimitustavan booleaniin tai enumiin ja k�ytt�� *if-then-else*� t�ytt��ksemme puuttuvan parametrin. Toinen ratkaisu olisi luoda kaksi luokkaa, jotka laajentavat Item-luokkaa. Kutsutaan n�it� luokiksi DownloadableItem ja SurfaceItem. Nyt kirjoitetaan hieman koodia. Nostan Item-luokan rajapinnaksi, joka tarjoaa yhden metodin, ship. Toimittaaksemme ostoskorin sis�ll�n, kutsumme `item.ship(shipper)`. Luokat `DownloadableItem` ja `SurfaceItem` molemmat toteuttavat metodin ship.

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

T�ss� esimerkiss� olemme delegoineet vastuun `Shipping`in kanssa ty�skentelemisen jokaiselle Itemille. Koska jokainen esine tiet��, miten se olisi parasta toimittaa, t�m� j�rjestely v�ltt�� *if-then-else*n k�ytt�misen. Koodi my�s demostroi kahden mallin k�ytt�mist�, jotka usein toimivat hyvin yhdess�: Komento ja Double Dispatch. N�iden mallien tehokas k�ytt� vaatii polymorfismin harkittua k�ytt��. Kun niin tehd��n, *if-then-else* -lohkojen k�ytt� koodissasi v�henee.

Vaikka on tapauksia, joissa on k�yt�nn�llisemp�� k�ytt�� *if-then-else*� polymorfismin sijaan, useimmiten polymorfinen ohjelmointitapa tuottaa pienemp��, luettavampaa ja v�hemm�n hauraan koodikannan. Menetettyjen mahdollisuuksien laskeminen onnistuu yksinkertaisesti laskemalla koodimme *if-then-else* -lauseiden m��r�.

Kirjoittanut [Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine)