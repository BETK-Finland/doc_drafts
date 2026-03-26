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

Dokumentointi
Pyrimme pilotissa dokumentoimaan kaikki pilotointiin liittyvät vaiheet ja havainnot. Dokumentoinnin tavoitteena on mahdollistaa tulosten hyödyntämisen alan kehityksen edistämisessä.
Dokumentoinnin vaiheet:
> 1.	Pilotointisuunnitelma: Yksityiskohtainen suunnitelma, sisältää pilotoinnin tavoitteet, pilotointien kuvaukset, aikataulun ja vastuuhenkilöt.
2.	Tunnisteteknologian ja tiedonsiirron menetelmien kirjaaminen: Dokumentoidaan pilotissa testatut tiedonkantajat ja lukijat, sekä niiden tekniset tiedot. Dokumentoidaan pilotissa testatut tiedonsiirron menetelmät.
3.	Tuotetietojen kirjaaminen: Dokumentoidaan pilottiin sisältyvien tuotteiden informaatio sisältö koneluettavassa muo-dossa.
4.	Suunnitteluprosessin kuvaus: Dokumentoidaan tiedonkantajien (esim. RFID-piirien) tarkat sijoituspaikat tuotteiden tuotantosuunnitelmiin.
5.	Asennusprosessin kuvaus: Dokumentoidaan toimitusketjun eri vaiheiden prosessit ja tapahtumat yksityiskohtaisesti (myös. käytetyt menetelmät, tarvikkeet ja työkalut, sijainnit). 
6.	Luettavuustestit: Dokumentoidaan tiedonkantajien luettavuus eri vaiheissa ja olosuhteissa, mukaan lukien mahdolliset häiriötekijät ja niiden vaikutukset.
7.	Kenttätestaus: Kirjataan havainnot tiedonkantajien (esim. RFID-piirien) toiminnasta eri toimitusketjun vaiheissa, kuten elementtien valmistuksessa, kuljetuksessa ja asennuksessa. Pyritään hyödyntämään automaattisia portteja (mikäli tie-donkantajana testataan RFID-tunnisteita).
8.	Tapahtumatieto: Dokumentoidaan ja jaetaan toimitusketjujen lukutapahtumat EPCIS-standardin mukaan.
9.	Data-analyysi: Analysoidaan kerätty data tiedonkantajien (RFID-piirien) suorituskyvystä ja luettavuudesta, sekä toimi-tusketjussa jaettavan tiedon (tapahtumatiedon) virtauksesta. Laaditaan yhteenveto tuloksista, mukaan lukien mahdolli-set ongelmat ja niiden ratkaisut.
10.	Raportit: Laaditaan kattava loppuraportti, joka sisältää analyysin tulokset, suositukset ja johtopäätökset pilotoinnin tuloksista.



---

## 3. Transaktiotiedonvaihto Peppol-verkossa

Pilotin aiheena on testata hankinta-toimitusketjussa Peppol-sanomavälitystä tilaajan ja myyjän välisessä kommunikaatiossa.
