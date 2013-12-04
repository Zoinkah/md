MuNa: Museonavigaattori
=====
Tommi Silvennoinen, Petri Rautiainen, Mikko Piuhola, Jonatan Ruottinen  
Ohjelmistotuotannon projekti  
4.12.2013  
Metropolia
*****
##Sisällys
1. Johdanto
	* 1.1 Yleiskuvaus
2. Käyttötapaukset
3. Järjestelmäarkkitehtuuri
4. Vaatimukset
5. Käyttöliittymä
	* 5.1 Yleistä käyttöliittymästä
	* 5.2 Oleelliset näkymät
	* 5.3 Kuvaukset näkymistä
	* 5.4 Näkymäkaavio
6. Projektin hallinta, reflektio

##1. Johdanto

###1.1 Yleiskuvaus
Tämän dokumentin tarkoitus on kuvata museonavigaattori MuNan vaatimukset. MuNa on museossa tai taidenäyttelyssä puhelimeen ladattava esittelykierrosohjelma, joka ottaa selvää käyttäjän sijainnista ja tarjoaa tietoa juuri saman huoneen teoksista.
Sen on tarkoitus korvata nykyiset mukana kannettavat kuulokejärjestelmät ja tarjota asiakkaalle tiedon lisäksi muita avuliaita ominaisuuksia, kuten kartan ja haluttuun kohteeseen navigoinnin.


## 5. Käyttöliittymä

###5.1 Yleistä käyttöliittymästä

Käyttöliittymässä on oleellista se, että sen käyttö on intuitiivista ja selkeätä. Niinpä käyttöliittymän toteutuksessa tulee ottaa huomioon seuraavat asiat:
- Puhelimien näyttöjen koon takia nappien täytyy olla suuria, jotta niitä voi painaa helposti
- Nappien tekstien täytyy vastata täysin sitä, minne ne vievät, jotta käyttäjä tajuaa sijaintinsa sovelluksessa. Karttaan johtava nappi tulee nimetä kartaksi, eikä esimerkiksi navigaatioksi.
- Jokaisessa näkymässä tulee olla takaisin-nappi, joka palaa takaisin edelliseen näkymään. Etusivulla vastaava nappi poistuu sovelluksesta.
- Jokaisessa näkymässä on myös palaa suoraan etusivulle -nappi
- Jokaisessa näkymässä voi vaihtaa kieltä

###5.2 Oleelliset näkymät

- Etusivu
- Huonenäkymä
- Kartta
- Huonevalinta
- Teosnäkymä
- Apua

###5.3 Kuvaukset näkymistä

![Etusivu](./images/etusivu_p.png)

#### Etusivu

Näkymä, joka avautuu, kun sovellus avataan. Etusivun kautta pääsee siirtymään kaikkiin sovelluksen eri toimintoihin. Yläkulmassa on nappi kielivalintaa varten.

![Huonenäkymä](./images/huonenakyma_p.png)

#### Huonenäkymä

Avautuu etusivun ”Huoneen teokset” -nappia painamalla. Näkymässä näkyvät huoneen teokset, joista voidaan valita yksi teos lähempää tarkastelua varten. Tämänhetkinen huone saadaan hyödyntämällä tilanpaikannusta.

![Kartta](./images/kartta_p.png)

#### Kartta

Näkymä avautuu joko painamalla etusivun ”Kartta”-nappia tai yksittäisen teoksen ”Navigoi”-nappia. Kartassa esitetään käyttäjän nykyinen sijainta museon pohjakartalla. Navigoidessa siinä näytetään myös kohde ja reitti käyttäjän nykyisestä sijainnista.

![Huonevalinta](./images/huonevalinta_p.png)

#### Huonevalinta

Näkymä avautuu painamalla etusivun ”Kaikki teokset” -nappia. Valitsemalla huone listasta, siirrytään huonenäkymään, jossa näkyy tällöin valittu eikä käyttäjän tämänhetkinen huone.

![Teosnäkymä](./images/teosnakyma_p.png)

#### Teosnäkymä

Näkymä avautuu valitsemalla yksittäinen teos Huonenäkymästä. Näkymän vasemmassa yläkulmassa näytetään kuva teoksesta. Oikeassa yläkulmassa puolestaan teoksen tiedot, kuten tekijä, ja ”Navigoi”-nappi, josta siirrytään Karttaan. Näiden elementtien alapuolella on tekstikenttä, joka sisältää lisäinformaatiota teoksesta.

![Apua](./images/apua_p.png)

#### Apua

Näkymä avautuu etusivun ”Apua”-napista. Se sisältää teksti- ja kuvamuotoista tietoa sovelluksen käytöstä yhdessä näkymässä.

###5.4 Näkymäkaavio

![Näkymäkaavio](./images/näkymäsiirtymät.png)

Näkymissä liikutaan yllä näkyvän näkymäkaavion mukaan.

Käyttäjäskenaario 2:
Käyttäjä haluaa etsiä tietoa teoksesta, joka on samassa huoneessa missä hän on. Etusivulla heti ensimmäinen nappi on "huoneen teokset", joka johtaa näkymään saman huoneen teoksista.
MuNa lähettää tietoa saamistaan wifi-signaaleistaan palvelimelle, joka laskee niiden voimakkuuksien perusteella käyttäjän sijainnin. Siispä käyttäjän ei tarvitse valita huonetta, jossa hän on, vaan sovellus päivittää sen automaattisesti.
Tästä valikosta käyttäjä valitsee teoksista haluamansa ja sovellus siirtyy teosnäkymään. Näin käyttäjä pääsee kahdella painalluksella etusivulta teoksen tietoihin käsiksi.
Mahdollisena virheenä käyttäjä voi valita kaikki teokset tai kartan, mutta niidenkin avulla oikein navigoimalla pääsee helposti teosnäkymään.

Käyttäjäskenaario 3:
Käyttäjä haluaa vaihtaa sovelluksen kielen. Jokaisessa näkymässä on selkeä kielipainike, jota painamalla nykyisen näkymän päälle ilmestyy lista valittavissa olevista kielistä. Lippua painamalla
sovelluksen kieli vaihtuu valittuun kieleen ja kielilista häviää näkyvistä. Koska kielet ja painike ovat kuvia, valikko on helppo löytää ja käyttää, vaikka käyttäjä ei ymmärtäisi sovelluksen sillä hetkellä käytössä olevaa kieltä.
