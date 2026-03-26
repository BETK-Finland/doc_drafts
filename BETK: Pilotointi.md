# Pilotointisuunnitelma

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Päivämäärä: 26.03.2026  
Versio: 0.0.1
Status: Luonnos


## Asiakirjan tiedot

Pilotointisuunnitelma perustuu modulaariseen lähestymistapaan ja jakautuu selkeästi tunnistettuihin osakokonaisuuksiin, joita voidaan pilotoida joko itsenäisesti tai osana laajempaa kokonaisuutta. 
Pilotoinnin tavoitteena on tuottaa luotettavaa tietoa ratkaisun toimivuudesta, vaikuttavuudesta ja kehitystarpeista aidossa toimintaympäristössä.

Pilotoitavat osakokonaisuudet perustuvat Rakennusteollisuus RT:n BETK-toimitusketjutyöryhmän tunnistettuihin kehitysaihioihin. Pilotin odotetaan edistävän rakennusalan toimitusketjujen digitaalisen hallinnan kehitystä ja tukevan alan systeemistä muutosta kohti tehokkaampaa ja läpinäkyvämpää toimintaympäristöä. Toimitusketjun testauksen tulokset dokumentoidaan, analysoidaan ja julkaistaan avoimesti rakennusalan toimijoiden käyttöön sekä suomeksi että englanniksi. 

Pyrimme pilotissa dokumentoimaan kaikki pilotointiin liittyvät vaiheet ja havainnot. Dokumentoinnin tavoitteena on mahdollistaa tulosten hyödyntämisen alan kehityksen edistämisessä.

<details> 
<Summary>Asiakirjan versio</Summary>
 
| **Versio**| **Päivämäärä**| **Tekijä**      |**Muutoskuvaus**                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 0.0.1      | 2026-03-26        |TeAla            | Luonnos vaihe                                  |

</details>

1. [Suunnittelu](#1-suunnittelu)
2. [Tapahtumatiedon jakaminen toimitusketjussa](#2-tapahtumatiedon-jakaminen-toimitusketjussa)

---

## 1. Suunnitteluvaiheen tietosisältöjen pilotointi

---

## 2. Tapahtumatiedon jakaminen toimitusketjussa
Pilotin aiheena on testata ja arvioida BETK-työryhmässä vakioitujen GS1-toimitusketjustandardeihin perustuvien koneluettavien tietomäärittelyiden sekä rakenteellisessa muodossa jaettavien tapahtumatietojen (GS1 EPCIS) tiedonsiirron toimintamallien toimivuutta toimitusketjun eri vaiheissa.

Lisäksi yhtenä keskeisenä aiheena on testata tuoteyksilöinnin ja -tunnistamisen toteutusta fyysisten tuotteiden toimi-tusketjussa hyödyntäen koneellisesti luettavia standardoituja menetelmiä, kuten 2D-viivakoodeja ja RFID-teknologiaa. Toimitusketjun eri vaiheissa syntyvät lukutapahtumat ja kyseisen tapahtumatiedon jakaminen GS1 EPCIS standardin mukaisesti. Pilotin laajuus on suunniteltu kattavaksi, jotta määrällinen data-analyysi voidaan suorittaa riittävän suurella tarkastel-tavien tuotteiden joukolla (noin 100 tuotetta). 

### 2.1 Käyttötapaukset ja toteutus

<h2>Käyttötapaukset pilotissa 2</h2>

<table border="1" cellpadding="8" cellspacing="0" style="width:100%; border-collapse:collapse;">
  <thead>
    <tr>
      <th style="width:120px;">Kuva</th>
      <th style="width:200px;">Osa-alue</th>
      <th>Kuvaus</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td>Tiedonkantajien luenta</td>
      <td>
        Testataan tiedonkantajien (passiivisten UHF RFID -tunnisteiden sekä DataMatrix + GS1 Digital Link 2D -viivakoodien)
        toimivuutta elementtien toimitusketjun eri vaiheissa
      </td>
    </tr>
    <tr>
      <td></td>
      <td>EPCIS-standardi</td>
      <td>
        GS1 EPCIS mahdollistaa tapahtumatietojen tallentamisen ja jakamisen tuotteiden ja sijaintien muutoksista toimitusketjussa.
        Määrittelee tiedon koodauksen ja kommunikoinnin eri osapuolten välillä. RFID/EPC yksilöi elementit
        <br>• Testataan lukutapahtumien jakamista EPCIS-standardin mukaan
      </td>
    </tr>
  </tbody>
</table>
<br>
<h2>Tapahtumat toimitusketjussa</h2>
<table border="1" cellpadding="8" cellspacing="0" style="width:100%; border-collapse:collapse;">
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

Pilotin aiheena on testata hankinta-toimitusketjussa Peppol-sanomavälitystä tilaajan ja myyjän välisessä kommunikaatiossa.
