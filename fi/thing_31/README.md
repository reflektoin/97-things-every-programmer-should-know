# �l� Koske siihen Koodiin!

Se on tapahtunut kaikille meille jossain vaiheessa. Koodisi siirrettiin staging-serverille j�rjestelm�testausta varten ja testausp��llikk�(testing manager) kirjoittaa, ett� h�n on t�rm�nnyt ongelmaan. Ensimm�inen reaktiosi on "Korjaan sen pikaisesti, tied�n mik� on vialla."

Isommassa kuvassa, vika on, ett� kehitt�j�n� ajattelet, ett� sinun pit�isi olla p��sy staging-serverille. Suuremmassa osassa web-pohjaisissa kehitysymp�rist�iss� arkkitehtuuri voidaan jakaa seuraaviin osiin:

- Paikallinen kehitys ja yksikk�testit kehitt�j�n omalla koneella
- Kehitys-palvelin, jossa tehd��n manuaaliset tai automaattiset integraatiotestit
- Staging-palvelin, jossa laadunvarmistus(QA) tiimi ja k�ytt�j�t tekev�t hyv�ksynt�testauksen
- Tuotantopalvelin

Kyll�, on my�s muita palvelimia ja palveluita siell� t��ll�, kuten versionhallinta ja tiketit, mutta idea menee perille. T�t� mallia k�ytt�en, kehitt�j�n - edes seniori-kehitt�j�n - ei tulisi koskaan p��st� kehityspalvelinta pidemm�lle. Suurin osa kehitysksest� tapahtuu kehitt�j�n omalla koneella k�ytt�en heid�n lempiyhdistelm��ns� IDE:st�, virtuaalikoneista ja sopivasta ripauksesta mustaa magiaa varmuuden vuoksi.

Versionhallintaan tallentamisen j�lkeen, manuaalisesti tai automaattisesti, sen pit�isi siirty� kehityspalvelimelle, jossa se voidaan testata ja hioa tarpeen tullen kuntoon, jotta kaikki toimii. T�st� eteenp�in kehitt�j�n pit�isi vain seurata prosessia.

Staging managerin pit�isi pakata ja siirt�� ohjelmisto staging palvelimelle laadunhallinta tiimi� varten. Aivan kuten kehitt�jien ei pit�isi p��st� kehityspalvelinta pidemm�lle, laadunhallinan tiimin ja k�ytt�jien ei pit�isi p��st� kehityspalvelimelle. Jos se on valmis hyv�ksynt�testaukseen, luo julkaisu, �l� pyyd� k�ytt�j�� "vilkaise nopsaa yht� asiaa" kehityspalvelimella. Muista, ellet koodaa projektiasi yksin, muilla ihmisill� on my�s koodia siell�, eiv�tk� ne v�ltt�m�tt� ole valmiina n�ytett�v�ksi k�ytt�j�lle. Julkaisup��llikk�(release manager) on ainut henkil� kenell� pit�isi olla p��sy molempiin

Miss��n tilanteessa - koskaan - kehitt�j�n ei pit�isi p��st� tuotantopalvelimelle. Ongelman ilmaantuessa tukihenkil�st�n(support staff) pit�isi korjata se tai pyyt�� sinua korjaamaan asia. Kun se on tallennettu versionhallintaan, he tekev�t muutoksen sielt�. Suurimmat ohjelmointikatastrofit, joissa olen ollut mukana ovat tapahtuneet, koska joku \**k�h*\*min�**k�h\** rikkoivat t�t� viimeist� s��nt��. Jos se on rikki, sit� ei pit�isi korjata tuotannossa.

Alkuper�inen kirjoittaja [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)