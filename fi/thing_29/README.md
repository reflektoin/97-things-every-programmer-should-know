# Älä luota kohtaan "taikoja tapahtuu täällä"

Katsoessasi mitä tahansa toimintaa, prosessia tai tiedonalaa(discipline) riittävän kaukaa, se näyttää yksinkertaiselta. Johtajat, joilla ei ole kokemusta ohjelmoinnista ajattelevat sen olevan helppoa ja ohjelmoijat ilman johtamiskokemusta ajattelevat samoin johtamisesta.

Ohjelmointi on jotain, mitä ihmiset tekevät, ajoittain. Ja sen vaikea osa, ajattelu, on asiaan perehtymättömille vähiten näkyvä ja arvostettu osa. Vuosikymmenien saatossa on useita kertoja yritetty poistaa tarve vaativalle ajattelulle. Yksi varhaisimmista ja mieleenpainuvimmista yrityksistä oli Grace Hopperin tavoite tehdä ohjelmointikielistä selkokielisempiä, jonka jotkut ennustivat poistavan spesialisti-ohjelmoijien tarpeen. Lopputulos (COBOL) on tuottanut tuloa monille spesialisti-ohjelmoijille myöhempinä vuosikausina.

Sinnikäs visio ohjelmistokehityksen yksinkertaistamisesta ohjelmoinnin poistamisella on, ohjelmoijalle joka ymmärtää siihen liittyvät asiat, selkeästi naiivia. Mutta tähän virheeseen johtava henkinen prosessi on osa ihmisluonnetta ja ohjelmoijat ovat yhtä alttiita sille kuin kaikki muutkin.

Missä tahansa projektissa on todennäköisesti useita asioita, joiden kanssa yksittäinen ohjelmoija ei ole tekemisissä: vaatimusten keräys(eliciting requirements), budjettien hyväksyntä, kokoonpanopalvelin(build server), sovelluksen toimitus laadunhallinnalle ja tuotantoympäristöihin (deploying the application to QA and production environments), liiketoiminnan muutto vanhoista prosesseista tai ohjelmista jne.

Kun et aktiivisesti tee näitä asioita, niin tulee alitajuisesti oletettua niiden olevan yksinkertaisia ja tapahtuvat "taianomaisesti". Niin pitkään kuin taiat jatkuvat, kaikki on hyvin. Mutta kun, yleensä se on "kun" eikä "jos", taika loppuu, niin projekti on ongelmissa.

Tiedän projektien menettäneen monta viikkoja kehitysaikaa (developer time), koska kukaan ei ymmärtänyt heidän olevan riippuvaisia "oikean" DLL-version lataamisesta. Kun asiat alkoivat ajoittain hajota tiimin jäsenet katsoivat kaikkialle muualle ennen kuin huomasivat "väärän" DLL-version lataamisen olevan ongelma.

Toinen osasto työskenteli tasaisesti - projektit toimitettiin ajoissa, ei myöhäisillan debuggaus-sessioita, ei hätäkorjauksia. Niin tasaisesti, että ylempi johto päätti asioiden "etenevän itsestään" ja he pärjäisivät ilman projektipäällikköä. Kuuden kuukauden sisällä yksikön projektit näyttivät samanlaisilta kuin organisaation muiden yksiköiden projektit - viivästyneiltä, bugisilta ja jatkuvasti korjattavilta.

Sinun ei tarvitse ymmärtää kaikkea "taikaa", joka saa projektisi toimimaan, mutta ei ole haittaa ymmärtää osaa siitä - tai arvostaa henkilöä, joka ymmärtää niitä asioita, joita sinä et ymmärrä.

Ennen kaikkea, varmista taikojen loppuessa, että ne voidaan käynnistää uudestaan.

Alkuperäinen kirjoittaja [AlanGriffiths](http://programmer.97things.oreilly.com/wiki/index.php/AlanGriffiths)