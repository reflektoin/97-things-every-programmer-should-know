# Käytä Mielummin Sovellusalueen Tyyppejä Kuin Alkeistyyppejä (Tai käytä Sovellusalueen Tyyppeja Alkeistyyppien sijaan)

23. syyskuuta 1999 menetettiin maalla tapahtuneen ohjelmistovian takia 327,6 miljoonan dollarin Mars Climate Orbiter sen asettuessa Marsin kiertoradalle. Vikaa myöhemmin kutsuttiin *metriseksi mokaksi*(metric mix-up). Maa-aseman ohjelmisto toimi paunoissa avaruusaluksen odottaessa newtoneita, mikä johti maa-aseman 4,45-kertaiseen aliarviointiin avaruusaluksen tarvitsemasta työntövoimasta.

Tämä on yksi useista ohjelmistovirheistä, joka olisi voitu välttää käyttämällä vahvempia ja enemmän sovellusalueen tyyppejä. Se on myös syy monille Ada-kielen ominaisuuksille, jonka pääsuunnittelutavoitteet on toteuttaa turvallisuuden kannalta kriittisiä sulautettuja ohjelmistoja. Adassa on vahva ja staattinen tyypitys sekä alkeistyypeille että käyttäjän määrittämille tyypeille:

```
type Velocity_In_Knots is new Float range 0.0 .. 500.00;

type Distance_In_Nautical_Miles is new Float range 0.0 .. 3000.00;

Velocity: Velocity_In_Knots;

Distance: Distance_In_Nautical_Miles;

Some_Number: Float;

Some_Number:= Distance + Velocity; -- Will be caught by the compiler as a type error.
```

Vähemmän vaativilla sovellusalueilla työskentelevät kehittäjät voivat myös hyötyä sovellusalue-kohtaisesta tyypityksest, jossa he normaalisti käyttäisivät kielen ja sen kirjastojen tarjoamia alkeistyyppejä, kuten merkkijonoja ja liukulukuja. Javassa, C++:ssa, Pythonissa ja muissa moderneissa kielissä abstrakti tietotyyppi tunnetaan luokkana. Käyttäen luokkia, kuten `Velocity_In_Knots` ja `Distance_In_Nautical_Miles` parantaa koodin laatua:

1. Koodista tulee luettavampaa sen esittäessä asiat sovellusalueen käsittein, ei vain liukulukuina ja merkkijonoina.

- Koodista tulee testattavampaa, kun koodi kapseloi testattavan toiminnan.

- Koodi helpottaa uudelleenkäyttöä sovellusten ja järjestelmien välillä.

Tämä tapa toimii sekä staattisen että dynaamisen tyypityksen kielillä. Ainoana erona staattisen tyypityksen kielet saavat hieman apua kääntäjältä, kun dynaamisten kielten käyttäjät todennäköisesti luottavat yksikkötesteihinsä. Tarkastamistapa on eri, mutta perustelu ja tyyli eivät ole.

Opetus on aloittaa tutkimaan sovellusalue-kohtaisia tyyppejä parantaaksemme ohjelmistojen laatua.

Kirjoittanut [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)