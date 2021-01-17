# Älä Koske siihen Koodiin!

Se on tapahtunut kaikille meille jossain vaiheessa. Koodisi siirrettiin staging-serverille järjestelmätestausta varten ja testauspäällikkö(testing manager) kirjoittaa, että hän on törmännyt ongelmaan. Ensimmäinen reaktiosi on "Korjaan sen pikaisesti, tiedän mikä on vialla."

Isommassa kuvassa, vika on, että kehittäjänä ajattelet, että sinun pitäisi olla pääsy staging-serverille. Suuremmassa osassa web-pohjaisissa kehitysympäristöissä arkkitehtuuri voidaan jakaa seuraaviin osiin:

- Paikallinen kehitys ja yksikkötestit kehittäjän omalla koneella
- Kehitys-palvelin, jossa tehdään manuaaliset tai automaattiset integraatiotestit
- Staging-palvelin, jossa laadunvarmistus(QA) tiimi ja käyttäjät tekevät hyväksyntätestauksen
- Tuotantopalvelin

Kyllä, on myös muita palvelimia ja palveluita siellä täällä, kuten versionhallinta ja tiketit, mutta idea menee perille. Tätä mallia käyttäen, kehittäjän - edes seniori-kehittäjän - ei tulisi koskaan päästä kehityspalvelinta pidemmälle. Suurin osa kehitysksestä tapahtuu kehittäjän omalla koneella käyttäen heidän lempiyhdistelmäänsä IDE:stä, virtuaalikoneista ja sopivasta ripauksesta mustaa magiaa varmuuden vuoksi.

Versionhallintaan tallentamisen jälkeen, manuaalisesti tai automaattisesti, sen pitäisi siirtyä kehityspalvelimelle, jossa se voidaan testata ja hioa tarpeen tullen kuntoon, jotta kaikki toimii. Tästä eteenpäin kehittäjän pitäisi vain seurata prosessia.

Staging managerin pitäisi pakata ja siirtää ohjelmisto staging palvelimelle laadunhallinta tiimiä varten. Aivan kuten kehittäjien ei pitäisi päästä kehityspalvelinta pidemmälle, laadunhallinan tiimin ja käyttäjien ei pitäisi päästä kehityspalvelimelle. Jos se on valmis hyväksyntätestaukseen, luo julkaisu, älä pyydä käyttäjää "vilkaise nopsaa yhtä asiaa" kehityspalvelimella. Muista, ellet koodaa projektiasi yksin, muilla ihmisillä on myös koodia siellä, eivätkä ne välttämättä ole valmiina näytettäväksi käyttäjälle. Julkaisupäällikkö(release manager) on ainut henkilö kenellä pitäisi olla pääsy molempiin

Missään tilanteessa - koskaan - kehittäjän ei pitäisi päästä tuotantopalvelimelle. Ongelman ilmaantuessa tukihenkilöstön(support staff) pitäisi korjata se tai pyytää sinua korjaamaan asia. Kun se on tallennettu versionhallintaan, he tekevät muutoksen sieltä. Suurimmat ohjelmointikatastrofit, joissa olen ollut mukana ovat tapahtuneet, koska joku \**köh*\*minä**köh\** rikkoivat tätä viimeistä sääntöä. Jos se on rikki, sitä ei pitäisi korjata tuotannossa.

Alkuperäinen kirjoittaja [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)