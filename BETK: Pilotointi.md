# Pilotointisuunnitelma

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Päivämäärä: 26.03.2026  
Versio: 0.0.1
Status: Luonnos


## Asiakirjan tiedot

Pilotointisuunnitelma perustuu modulaariseen lähestymistapaan ja jakautuu selkeästi tunnistettuihin osakokonaisuuksiin, joita voidaan pilotoida joko itsenäisesti tai osana laajempaa avoimen toimintaympäristön kokonaisuutta. 
Pilotoinnin tavoitteena on tuottaa luotettavaa tietoa ratkaisun toimivuudesta, vaikuttavuudesta ja kehitystarpeista aidossa toimintaympäristössä.

Pilotoitavat osakokonaisuudet perustuvat Rakennusteollisuus RT:n BETK-toimitusketjutyöryhmän tunnistettuihin kehitysaihioihin. Pilotin odotetaan edistävän rakennusalan toimitusketjujen digitaalisen hallinnan kehitystä ja tukevan alan systeemistä muutosta kohti tehokkaampaa ja läpinäkyvämpää toimintaympäristöä. Toimitusketjun testauksen tulokset dokumentoidaan, analysoidaan ja julkaistaan avoimesti rakennusalan toimijoiden käyttöön sekä suomeksi että englanniksi. 

Pyrimme pilotissa dokumentoimaan kaikki pilotointiin liittyvät vaiheet ja havainnot. Dokumentoinnin tavoitteena on mahdollistaa tulosten hyödyntämisen alan kehityksen edistämisessä.

<details> 
<Summary>Asiakirjan versio</Summary>
 
| **Versio**| **Päivämäärä**| **Tekijä**      |**Muutoskuvaus**                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 0.0.1      | 2026-03-26        |TeAla            | Luonnos vaihe                                  |

</details>

## Sisällysluettelo

1. [Suunnitteluvaiheen tietosisältöjen pilotointi](#1-suunnitteluvaiheen-tietosisältöjen-pilotointi)

2. [Tapahtumatiedon jakaminen toimitusketjussa](#2-tapahtumatiedon-jakaminen-toimitusketjussa)  
   2.1 [Käyttötapaukset ja toteutus](#21-käyttötapaukset-ja-toteutus)  
   2.2 [Aikataulu](#22-aikataulu)  
   2.3 [Dokumentointi](#23-dokumentointi)  

3. [Transaktiotiedonvaihto Peppol-verkossa](#3-transaktiotiedonvaihto-peppol-verkossa)  
   3.1 [Pilotin soveltamisala](#31-pilotin-soveltamisala)  
   3.2 [Käyttötapaukset ja toteutus](#32-käyttötapaukset-ja-toteutus)  
   3.3 [Arvioitavat tulokset](#33-arvioitavat-tulokset)  
   3.4 [Yhteys EPCIS-tapahtumatietoon](#34-yhteys-epcis-tapahtumatietoon)  
---

## 1. Suunnitteluvaiheen tietosisältöjen pilotointi

Suunnitteluvaiheen pilotoinnissa keskeisenä tavoitteena on testata, miten tietomallipohjaisesta suunnitteluprosessista voidaan tuottaa vakioitu ja koneluettava osaluettelo (BOM), joka on suoraan hyödynnettävissä toimitusketjun eri tietojärjestelmissä.

Pilotointi perustuu Rakennusteollisuus RT:n BETK-työryhmän laatimaan soveltamisohjeeseen Tarjousvaiheen tietomääritykset ja toteutusvaiheen tietomalliohjeet toimitusketjulle. Kyseinen ohje määrittelee ne tietosisällöt ja ominaisuustiedot, joiden avulla betonielementit voidaan tunnistaa, luokitella ja käsitellä koneluettavasti eri hankkeiden välillä. Pilotissa näitä määrittelyjä sovelletaan käytännössä ja arvioidaan niiden toimivuutta osana digitaalista toimitusketjua.

Pilotissa tarkastellaan mallinnusprosessia kokonaisuutena siten, että suunnittelijan tuottama tietomalli toimii rakenteisena tietolähteenä, josta voidaan muodostaa toimitusketjun tarvitsema tuotetieto ilman manuaalista tulkintaa. Erityinen painopiste on siinä, missä määrin tietomalliin sisällytetyt vakioidut ominaisuustiedot mahdollistavat osaluettelon (BOM) automaattisen muodostamisen.

BETK-soveltamisohjeen mukaisesti pilotissa hyödynnettävät keskeiset tietosisällöt liittyvät elementtien yksiselitteiseen tunnistamiseen ja kuvaamiseen. Näitä ovat muun muassa kokoonpanon tyyppi (esimerkiksi betonielementti), elementtityyppi (koodi ja kuvaus), sekä elementin tekniset ominaisuudet, kuten raudoitus, pintakäsittely ja mahdollinen väribetoni. Lisäksi pilotissa tarkastellaan täydentäviä ominaisuuksia, kuten vähähiilisyystietoa, tyyppielementtimäärittelyä sekä asennukseen liittyviä erityispiirteitä, kuten työmaalla käännettävyyttä.

Näiden tietojen keskeinen merkitys pilotissa on se, että ne muodostavat perustan BOM-rakenteelle. Tavoitteena on varmistaa, että tietomallista voidaan johdonmukaisesti muodostaa osaluettelo, jossa elementit voidaan ryhmitellä, tunnistaa ja siirtää eteenpäin ilman hankekohtaisia tulkintoja tai erillisiä manuaalisia rikastamisvaiheita. Tämä on merkittävä muutos nykytilaan, jossa tietomallien hyödyntäminen edellyttää usein asiantuntijatulkintaa.

Pilotissa testataan käytännössä prosessia, jossa IFC-muotoinen tietomalli sisältää BETK-määrittelyjen mukaiset ominaisuustiedot, ja tästä tietomallista muodostetaan vakioitu BOM. Tämän jälkeen arvioidaan, miten BOM voidaan siirtää ja hyödyntää toimitusketjun eri järjestelmissä, kuten hankinnan, tuotannon ja logistiikan ratkaisuissa.

Tietosisällön laadun ja yhdenmukaisuuden varmistamiseksi pilotissa hyödynnetään IDS-määrityksiä (Information Delivery Specification). IDS toimii validointimekanismina, jonka avulla voidaan määritellä vaadittavat tietokentät ja niiden sallitut arvot sekä tarkistaa, että tietomalli täyttää nämä vaatimukset ennen BOM:n muodostamista. Näin varmistetaan, että tietomallista johdettu tieto on rakenteellisesti oikeellista ja yhteentoimivaa eri järjestelmien välillä.

Pilotoinnissa kiinnitetään erityistä huomiota siihen, missä määrin vakioidut tietosisällöt mahdollistavat elementtien koneluettavan tunnistamisen ilman hankekohtaisia nimeämiskäytäntöjä. Tämä liittyy suoraan BETK-ohjeessa tunnistettuun nykytilan haasteeseen, jossa elementtityyppien tunnistaminen perustuu usein projektikohtaisiin tunnisteisiin, eikä ole automatisoitavissa.

Lisäksi pilotissa arvioidaan, miten suunnitteluvaiheen tietosisältö kytkeytyy toimitusketjun myöhempiin vaiheisiin. Erityisesti tarkastellaan, voidaanko BOM-rakenteen kautta muodostettu tuotetieto yhdistää tuotteiden yksilöintiin sekä toimitusketjun tapahtumatietoon (EPCIS). Tavoitteena on luoda yhtenäinen tietovirta suunnittelusta toteutukseen ja edelleen elinkaaren aikaiseen tiedonhallintaan.

Pilotin tuloksena muodostetaan kokonaiskuva siitä, millä edellytyksillä BETK-soveltamisohjeen mukainen tietosisältö mahdollistaa tietomallipohjaisen BOM:n muodostamisen sekä sen hyödyntämisen toimitusketjun digitaalisissa prosesseissa. Samalla tunnistetaan mahdolliset puutteet tietosisällöissä, mallinnusohjeissa tai käytännön toteutuksessa, ja esitetään suositukset jatkokehitystä varten.
---

## 2. Tapahtumatiedon jakaminen toimitusketjussa
Pilotin aiheena on testata ja arvioida BETK-työryhmässä vakioitujen GS1-toimitusketjustandardeihin perustuvien koneluettavien tietomäärittelyiden sekä rakenteellisessa muodossa jaettavien tapahtumatietojen (GS1 EPCIS) tiedonsiirron toimintamallien toimivuutta toimitusketjun eri vaiheissa.

Lisäksi yhtenä keskeisenä aiheena on testata tuoteyksilöinnin ja -tunnistamisen toteutusta fyysisten tuotteiden toimitusketjussa hyödyntäen koneellisesti luettavia standardoituja menetelmiä, kuten 2D-viivakoodeja ja RFID-teknologiaa. Toimitusketjun eri vaiheissa syntyvien lukutapahtumien keruu ja jakaminen GS1 EPCIS-standardin mukaisesti. Pilotin laajuus on suunniteltu kattavaksi, jotta määrällinen data-analyysi voidaan suorittaa riittävän suurella tarkasteltavien tuotteiden joukolla (noin 100 tuotetta). 

### 2.1 Käyttötapaukset ja toteutus

<h2>Käyttötapaukset & toteutus</h2>

<table border="1" cellpadding="8" cellspacing="0" style="width:100%; border-collapse:collapse;">

  <thead>
    <tr>
      <th style="width:220px;">Käyttötapaukset</th>
      <th colspan="2">Kuvaus</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Tiedonkantajien määrä</strong></td>
      <td colspan="2">
        Testataan tiedonkantajien (esim. passiivisten UHF RFID -tunnisteiden) toimivuutta yli sadan (100) elementin otannalla.
      </td>
    </tr>
    <tr>
      <td><strong>Tagin sijoittelu</strong></td>
      <td>
        Testataan, miten tiedonkantajan (esim. RFID-tagien) eri sijoittelut elementeissä vaikuttavat luettavuuteen.<br><br>
        <strong>Asennussijainnit:</strong>
        <ul>
          <li>Kokeillaan erilaisia variaatioita huomioiden aiemman pilotoinnin tulokset antennien lukusuunnan osalta</li>
        </ul>
        <strong>Kiinnitystavat:</strong>
        <ul>
          <li>Kokeillaan erilaisia variaatioita riippuen tiedonkantajasta ja elementistä</li>
        </ul>
        <strong>RFID-piirin orientaatio:</strong>
        <ul>
          <li>RFID-piiri edullisessa lukusuunnassa XY</li>
          <li>RFID-piiri epäedullisessa lukusuunnassa YZ ja XZ</li>
        </ul>
      </td>
     <td><img width="394" height="229" alt="image" src="https://github.com/user-attachments/assets/571881fa-b1a7-44dc-a68b-fde2822cd959" /></td>
    </tr>
    <tr>
      <td><strong>Ympäristövaikutukset (jos mahdollista)</strong></td>
      <td colspan="2">
        Tutkitaan ulkoisten tekijöiden vaikutusta (kosteus, lämpötila ja mekaaninen rasitus) RFID-tagien toimintaan ja kestävyyteen.
      </td>
    </tr>
    <tr>
      <th colspan="3" style="text-align:left;">Testattavat osiot</th>
    </tr>
    <tr>
      <td><strong>Piirin enkoodaus</strong></td>
      <td colspan="2">
        Piirille / 2D viivakoodiin enkoodataan BETK vakiotiedot elementin minimivaatimukset
      </td>
    </tr>
    <tr>
      <td><strong>Lukutarkastus</strong></td>
      <td>
        <ul>
          <li>Luetaan tiedonkantaja ja varmistetaan toimivuus</li>
          <li>Luennan toimivuus</li>
          <li>Luenta etäisyys lukijan ja RFID-piirin välillä</li>
          <li>Luenta voimakkuus / taajuus</li>
          <li>Huomioitava elementin kosteus (mitattava jos mahdollista)</li>
        </ul>
      </td>
      <td style="width:220px;">
        <img width="283" height="229" alt="image" src="https://github.com/user-attachments/assets/432f8995-e5ad-48c3-b697-d0cee8c3d454" />
      </td>
    </tr>
    <tr>
      <td><strong>RFID-piirin asennuspaikat</strong></td>
      <td colspan="2">
        <ul>
          <li>Ohessa esimerkki tavasta dokumentoida mihin RFID-piiri elementissä on asennettu</li>
          <li>Dokumentaatiossa ei tarvitse esittää varsinaista elementtikuvaa, koska tärkein tieto on missä nurkassa ja pinnassa piiri on</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="3">
        <img src="https://github.com/user-attachments/assets/6607bf2a-51a9-406c-bf54-31dbf730a035" /> <br>
        <em>Kuva 1. Havainne kuva RFID-piirin sijoituksesta</em>
      </td>
    </tr>
  </tbody>
</table>

<h2>Käytettävät tiedonkantajat ja tunnistusteknologia</h2>
Pilotoinnissa käytettävien tiedonkantajien tiedot. Pyrimme ensisijaisesti hyödyntämään RFID-teknologiaa tiedonkantajina. Vaihtoehtoisina tai lisätiedonkantajina voidaan hyödyntää 2D-viivakoodeja (DataMatrix ja GS1 Digital Link).
<table border="1" cellpadding="8" cellspacing="0" style="width:100%; border-collapse:collapse;">
  <thead>
    <tr>
      <th colspan="4">Testiympäristö X</th>
    </tr>
    <tr>
      <th>Laite/tuote</th>
      <th>Valmistaja</th>
      <th>Käyttötarkoitus / tekniset tiedot</th>
      <th>Määrä (kpl)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

<h2>Käyttötapaukset pilotissa</h2>

<table border="1" cellpadding="8" cellspacing="0" style="width:100%; border-collapse:collapse;">
  <thead>
    <tr>
      <th colspan="2" style="width:200px;">Osa-alue</th>
      <th>Kuvaus</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="2" style="width:200px;">Tiedonkantajien luenta</td>
      <td>
        Testataan tiedonkantajien (passiivisten UHF RFID -tunnisteiden sekä DataMatrix + GS1 Digital Link 2D -viivakoodien)
        toimivuutta elementtien toimitusketjun eri vaiheissa. Tarkasteltava vaihe voi olla myös osaprosessi (esim. elementtitehtaan sisäinen portti varastoalueelle elementin siirron yhteydessä)
      </td>
    </tr>
    <tr>
      <td colspan="2" style="width:200px;">EPCIS-standardi</td>
      <td>
        GS1 EPCIS mahdollistaa tapahtumatietojen tallentamisen ja jakamisen tuotteiden ja sijaintien muutoksista toimitusketjussa.
        Määrittelee tapahtumatietomallin ja jakamisen rajapinnat. RFID/EPC yksilöi elementit
        <br>• Testataan lukutapahtumien jakamista EPCIS-standardin mukaan
      </td>
    </tr>
  </tbody>
  <thead>
    <tr>
      <th style="width:120px;">Kuva</th>
      <th>Vaihe</th>
      <th>Tiedot</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/e1cfdbab-6a3e-4dd4-9fe3-3f6f5ef05f68" style="max-width:100px;"></td>
      <td><strong>Elementin valmistus tehtaalla</strong></td>
      <td>
        Kuka: (GLN) Elementtitoimittaja<br>
        Mitä: (SGTIN) Betonielementti<br>
        Missä: (GLN) Tehdas<br>
        Milloin: YYYY-MM-DDThh:mm:ssZ<br>
        Miksi: Valmistus<br>
        Status: Aktiivinen
      </td>
    </tr>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/e6c24d12-0349-4cdf-b575-36aab6f6ec41" style="max-width:100px;"></td>
      <td><strong>Elementin lastaus tehtaalla</strong></td>
      <td>
        Kuka: (GLN) Elementtitoimittaja<br>
        Mitä: (SSCC) Kuorma + (SGTIN1..n) Betonielementit<br>
        Missä: (GLN) Tehdas<br>
        Milloin: YYYY-MM-DDThh:mm:ssZ<br>
        Miksi: Kuormaus<br>
        Status: Kuljetuksessa
      </td>
    </tr>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/ff35d6e3-ec2a-4bbd-a29d-277faa06f17f" style="max-width:100px;"></td>
      <td><strong>Elementin vastaanotto työmaalla</strong></td>
      <td>
        Kuka: (GLN) Pääurakoitsija<br>
        Mitä: (SSCC) Kuorma + (SGTIN1..n) Betonielementit<br>
        Missä: (GLN) Työmaa<br>
        Milloin: YYYY-MM-DDThh:mm:ssZ<br>
        Miksi: Vastaanotto<br>
        Status: Vastaanotettu
      </td>
    </tr>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/d42a6085-85ad-426b-8be0-fdcb85776584" style="max-width:100px;"></td>
      <td><strong>Elementin asennus työmaalla</strong></td>
      <td>
        Kuka: (GLN) Pääurakoitsija<br>
        Mitä: (SGTIN) Betonielementti<br>
        Missä: (GLN) Työmaa + tarkenne<br>
        Milloin: YYYY-MM-DDThh:mm:ssZ<br>
        Miksi: Asentaminen<br>
        Status: Asennettu
      </td>
    </tr>
    <tr>
      <td><img src="https://github.com/user-attachments/assets/0068e5c9-b500-48e6-a84e-84b87e2f8fd2" style="max-width:100px;"></td>
      <td><strong>Elementin elinkaaren aikainen tarkastus</strong></td>
      <td>
        Kuka: (GLN) Rakennuksen omistaja<br>
        Mitä: (SGTIN) Betonielementti<br>
        Missä: (GLN) Rakennus + tarkenne<br>
        Milloin: YYYY-MM-DDThh:mm:ssZ<br>
        Miksi: Elinkaarentapahtuma X<br>
        Status: Tapahtuma X
      </td>
    </tr>
  </tbody>
</table>

**AIDC teknologian mahdolliset tunnistetut haasteet**<br>
RFID-piirien osalta on mahdollisena tunnistettuna haasteena betonielementtiin upotettuna RFID-tunnisteen antennin suuntauksen ja lukuetäisyyden rajoitteet RFID-tunnisteiden luennassa automaattisten porttien läpi. Tiedonkantajien luentatapahtumien toteuttaminen prosessissa vaatii osapuolten sitoutumista tehtävän suorittamiseen, vaikka lähtökohtaisesti lukutapahtumat toteutettaisiin automaattisten porttien kautta. Koska tärkeää on saada määrällistä dataa, yksittäisen staattisen pisteen merkitys lukutapahtumien tuottamisessa on tärkeä (esim. elementtitehtaalle asennettava kiinteä portti). Pilotissa voidaan hyödyntää myös ei-standardoituja täydentäviä tietolähteitä, kuten GPS-pohjaista geoaidattua sijaintitietoa. Nämä tiedot voidaan liittää EPCIS-tapahtumiin laajennuksina (extensions), mutta ne eivät ole osa varsinaista EPCIS-standardia.


**EPCIS-tiedonsiirron tekninen toteutus**
EPCIS-tapahtumat välitetään järjestelmien välillä standardoitujen rajapintojen kautta hyödyntäen REST-arkkitehtuuria. Tiedonsiirrossa käytetään EPCIS 2.0 -standardin mukaista JSON-LD -esitysmuotoa, joka mahdollistaa semanttisesti yhteentoimivan tiedonvaihdon eri osapuolten järjestelmien välillä.

EPCIS määrittelee tapahtumatietomallin (event model), joka kuvaa, mitä toimitusketjussa tapahtuu (esim. tapahtumatyyppi, ajankohta, sijainti ja liiketoimintakonteksti). JSON-LD toimii tiedon esitysmuotona, jossa tapahtumat kuvataan koneellisesti luettavassa ja laajennettavassa muodossa.

Tapahtumat voidaan validoida EPCIS 2.0 -standardin mukaisilla JSON-skeemoilla ennen niiden välittämistä tai tallentamista, mikä varmistaa tiedon rakenteellisen oikeellisuuden ja yhteentoimivuuden.

### 2.2 Aikataulu
| TEHTÄVÄ                                   | QX | QX | QX | QX | QX |
|-------------------------------------------|----|----|----|----|----|
| Esivalmistelu                             |    |    |    |    |    |
| Osapuolien kontaktointi                   | X  | X  |    |    |    |
| Pilotointisuunnitelman päivitykset        | X  | X  |    |    |    |
| Pilotointivalmistelut                     |    | X  | X  |    |    |
| Testausvaihe                              |    |    | X  | X  | X  |
| Raportointi ja tulosten analysointi       |    |    | X  | X  | X  |

### 2.3 Dokumentointi

|#|Dokumentoinnin vaiheet|Sisältö|
|-|----------------------|-------|
|1.| Pilotointisuunnitelma | Yksityiskohtainen suunnitelma sisältää pilotoinnin tavoitteet, pilotointien kuvaukset, aikataulun ja vastuuhenkilöt.|
|2.|	Tunnisteteknologian ja tiedonsiirron menetelmien kirjaaminen| Dokumentoidaan pilotissa testatut tiedonkantajat ja lukijat sekä niiden tekniset tiedot. Dokumentoidaan pilotissa testatut tiedonsiirron menetelmät.|
|3.|	Tuotetietojen kirjaaminen| Dokumentoidaan pilottiin sisältyvien tuotteiden informaatiosisältö koneluettavassa muodossa.|
|4.|	Suunnitteluprosessin kuvaus| Dokumentoidaan tiedonkantajien (esim. RFID-piirien) tarkat sijoituspaikat tuotteiden tuotantosuunnitelmiin.|
|5.|	Asennusprosessin kuvaus| Dokumentoidaan toimitusketjun eri vaiheiden prosessit ja tapahtumat yksityiskohtaisesti (myös käytetyt menetelmät, tarvikkeet ja työkalut, sijainnit).| 
|6.|	Luettavuustestit| Dokumentoidaan tiedonkantajien luettavuus eri vaiheissa ja olosuhteissa, mukaan lukien mahdolliset häiriötekijät ja niiden vaikutukset.|
|7.|	Kenttätestaus| Kirjataan havainnot tiedonkantajien (esim. RFID-piirien) toiminnasta eri toimitusketjun vaiheissa, kuten elementtien valmistuksessa, kuljetuksessa ja asennuksessa. Pyritään hyödyntämään automaattisia portteja (mikäli tiedonkantajana testataan RFID-tunnisteita).|
|8.|	Tapahtumatieto| Dokumentoidaan ja jaetaan toimitusketjujen lukutapahtumat GS1 EPCIS-standardin mukaan CBV-arvoja hyödyntäen.|
|9.|	Data-analyysi| Analysoidaan kerätty data tiedonkantajien (RFID-piirien) suorituskyvystä ja luettavuudesta sekä toimitusketjussa jaettavan tiedon (tapahtumatiedon) virtauksesta. Laaditaan yhteenveto tuloksista, mukaan lukien mahdolliset ongelmat ja niiden ratkaisut.|
|10.|	Raportit| Laaditaan kattava loppuraportti, joka sisältää analyysin tulokset, suositukset ja johtopäätökset pilotoinnin tuloksista.|



---

## 3. Transaktiotiedonvaihto Peppol-verkossa

Pilotin tavoitteena on testata hankinta-toimitusketjussa tapahtuvaa sanomavälitystä hyödyntäen Peppol-verkkoa tilaajan ja toimittajan välisessä kommunikaatiossa. Pilotissa keskitytään erityisesti Peppol BIS -sanomien välitykseen ja niiden muodostamaan sanomakoreografiaan todellisessa toimintaympäristössä.

---

### 3.1 Pilotin soveltamisala

Pilotissa testataan seuraavia vaihtoehtoisia sanomakokonaisuuksia:

- Catalogue (Peppol BIS Catalogue)
- Catalogue Response
- Order (Peppol BIS Order)
- Order Response
- (valinnainen) Despatch Advice
- (valinnainen) Receipt Advice

---

### 3.2 Käyttötapaukset ja toteutus

Pilotissa testataan seuraavat osa-alueet:

#### Sanomien muodostus ja validointi
- Sanomien muodostaminen Peppol BIS -määritysten mukaisesti  
- Sanomien validointi ennen lähetystä  

#### Sanomien välitys
- Sanomien siirto Peppol Access Point -verkoston kautta  
- Osapuolten tunnistaminen Peppol Participant ID -tunnisteilla  

#### Sanomakoreografia
- Tilausprosessin eteneminen Order → Order Response -ketjussa  
- Sanomien keskinäinen looginen riippuvuus ja oikea ajoitus  

#### Integraatio liiketoimintaprosesseihin
- Sanomien kytkeytyminen osapuolten toiminnanohjausjärjestelmiin (ERP)  
- Manuaalisten työvaiheiden väheneminen  

### 3.3 Arvioitavat tulokset

Pilotissa arvioidaan:

- Peppol-sanomien tekninen toimivuus eri järjestelmien välillä  
- Sanomien semanttinen yhteentoimivuus (tulkinnan yhdenmukaisuus)  
- Prosessin sujuvuus ja läpimenoaika  
- Mahdolliset puutteet tai kehitystarpeet sanomasisällöissä  

### 3.4 Yhteys EPCIS-tapahtumatietoon (suositeltu)

Peppol-sanomien pilotointi toteutetaan yhteensopivasti EPCIS-pohjaisen tapahtumatiedon kanssa siten, että tilaus- ja toimitustapahtumat voidaan tarvittaessa linkittää toimitusketjun tapahtumadataan.

Tämä mahdollistaa transaktio- ja tapahtumatiedon yhdistämisen yhtenäiseksi näkymäksi toimitusketjun eri vaiheista.
