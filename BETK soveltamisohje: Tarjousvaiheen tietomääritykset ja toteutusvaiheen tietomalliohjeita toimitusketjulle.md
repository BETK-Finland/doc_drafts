# BETK soveltamisohje: Tarjousvaiheen tietomääritykset ja toteutusvaiheen tietomalliohjeita toimitusketjulle

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Päivämäärä: 17.12.2025  
Versio: 1.0
Status: Luonnos



## Asiakirjan tiedot
<details> 
<Summary>Asiakirjan versio</Summary>
 
| **Versio **| **Päivämäärä    **| **Tekijä**      |**Muutoskuvaus     **                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 0.1        | 2024-12-30        |AnPekk           | Luonnos vaihe                                  |
| 0.2        | 2025-02-25        |AnPekk           |Tekstiosuuksia täydennetty                      |
| 0.3        | 2025-05-30        |AnPekk           | Tekstiosuuksia täydennetty                     |
| 0.4        | 2025-07-02        |AnPekk           | YIT, NCC ja Consoliksen kommentit huomioitu    |
| 0.5        | 2025-09-12        |AnPekk           | Elementtityyppi-listausta päivitetty           |
| 0.6        | 2025-10-22        |AnPekk           | Propertyjen nimet tarkistettu excelin mukaiseksi|
| 0.7        | 2025-12-05        |AnPekk           | Pintakäsittely ja väribetonit-kentät muokattu  |
| 1.0        | 2025-12-17        |AnPekk           | Github julkaisu                                |
</details>

<details> 
<Summary>Asiakirjan laatijat</Summary>

| **Nimi**            | **Organisaatio**               |
|---------------------|--------------------------------|
| Antti Pekkala       | Fira Oy                        |
| Teemu Anttila       | Ramboll                        |
| Janne Kihula        | Rakennustuoteteollisuus RTT ry |
| Teemu Alaluusua     | Aalto-yliopisto                |
| Tom Partanen        | Consolis Parma Oy              |
| Eetu Lahtinen       | Consolis Parma Oy              |
| Satu Parikka        | Consolis Parma Oy              |
| Kari Turunen        | Lujabetoni Oy                  |
| Markku Räisänen     | Betset Oy                      |
| Jarkko Vitikainen   | Sitowise Oy                    |
| Antti Taskinen      | Fira Oy                        |
| Riku Laiho          | NCC Suomi Oy                   |
| Arto Nieminen       | NCC Suomi Oy                   |
| Paula Valkonen      | Suutarinen / SBS Betoni Oy     |
</details>

1. [Tausta](#1-tausta)
2. [Soveltamisohjeen tarkoitus ja rajaukset](#2-soveltamisohjeen-tarkoitus-ja-rajaukset)
3. [Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa](#3-rakentamiskohteen-tietomallin-tietosisällöt-tarjousvaiheessa)<br>
   3.1. [Elementin tuotetiedot tarjousvaiheessa](#31-elementin-tuotetiedot-tarjousvaiheessa)<br>
      3.1.1. [Kokoonpanon tyyppi](#311-kokoonpanon-tyyppi)<br>
      3.1.2. [Elementtityyppi](#312-elementtityyppi)<br>
      3.1.3. [Raudoitus](#313-raudoitus)<br>
      3.1.4. [Pintakäsittely](#314-pintakäsittely)<br>
      3.1.5. [Väribetoni](#315-väribetoni)<br>
      3.1.6. [Vähähiilinen](#316-vähähiilinen)<br>
      3.1.7. [Tyyppielementti](#317-tyyppielementti)<br>
      3.1.8. [Työmaalla käännettävä elementti](#318-työmaalla-käännettävä-elementti)<br>
5. [Toimintaohjeita hankkeisiin](#4toimintaohjeita-hankkeisiin)
6. [Lyhenteet ja terminologia](#lyhenteet-ja-terminologia)<br>
   [Liite 1: Esimerkkejä raudoitustiedosta betonielementti tehtaan tarjouslaskennassa](#liite-1-esimerkkejä-raudoitustiedosta-betonielementti-tehtaan-tarjouslaskennassa)<br>
   [Viittaukset](#viittaukset)
---

## 1 Tausta
Tällä hetkellä rakennushankkeen tietomallit ovat yleinen osa hankkeen tarjouspyyntöjä ja niiden määrä- ja kustannuslaskentaa. Suunnittelijoiden tekemiä tietomalleja käyttävät rakennusliikkeet ja elementtitoimittajat mm. määrä- ja tarjouslaskennassa, hankkeen toteutuksen suunnittelussa ja aikatauluttamisessa jne. BEC2012-hankkeessa[^1] luodut vakioidut tietokentät, mallinnusohje ja mallinnustyökalut ovat alalla yleisesti käytössä.  BEC-ohjeistus ei kuitenkaan mahdollista koneluettavaa tiedonsiirtoa, koska usea asia on BEC-ohjeistuksessa määritetty hankekohtaisesti sovittavaksi eikä tietokentille ole ohjeistettu sallittuja arvoja. Tiedot ovat saatavissa tietomalleista mutta edellyttää ihmisen taitoa lukea tietomallia ja samalla myös muita hankkeen suunnitelmadokumentteja. Esimerkkinä tällaisesta käyttötapauksesta on esim. kuinka tunnistetaan tiililaattapintaiset SW-elementit hankkeen tietomallista ja voidaan erotella tietomallin muista elementeistä. Usein hankkeissa käytetään hankekohtaisesti sovittuna elementtityyppitunnuksessa myös pintakäsittelyä tai sijaintia tarkentavia numero- tai kirjainyhdistelyitä, kuten esim. <code>V1-A</code>. Nämä johtavat siihen, että elementtityyppejä ei voida tunnistaa koneluettavasti hankkeesta toiseen.  Tällä hetkellä tunnistaminen ei onnistu automaattisesti. Soveltamisohjeessa kuvattu ratkaisu elementtityyppien tunnistamiseen pohjautuu alalla yleisesti käytettyihin elementtityyppitunnuksiin, esim. ```V```, ```R``` ja ```S``` jne.[^2] Näitä tietoja täydennetään mm. vakioiduilla pintakäsittely tiedoilla. 

IFC-tietomallistandardissa rakenneosien tunnistamiseksi objekteille voidaan määrittää IFC-luokkia, kuten esimerkiksi *ifcwall*. Useilla IFC-luokilla on lisäksi *PredefinedType*-ominaisuus, joka tarkentaa luokan tyyppiä. Esimerkiksi *ifcwall*-luokka voi sisältää *PredefinedType*-arvoja, kuten ```ELEMENTEDWALL``` tai ```SOLIDWALL```. Standardissa määriteltyjen luokitteluiden tarkkuustaso riittää karkeaan luokitteluun, mutta ei mahdollista riittävän tarkkaa tunnistamista määrä- ja kustannuslaskentaa varten. Tämän vuoksi tarvitaan lisäattribuutteja, jotta tietomallin avulla saavutetaan vaadittava tarkkuustaso. Ohjeessa kuvattu ratkaisusta on tehty myös esimerkki malli Tekla Structures-ohjelmassa ja mallista IFC-tiedosto, eli ratkaisu on myös toteuttamiskelpoinen nykyisillä ohjelmistoilla.

Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Asiakirja on jatkuvasti päivittyvä ja sitä kehitetään edelleen Rakennusteollisuus RT:n kehityshankkeen havaintojen perusteella. Tätä ohjetta täydentävät muut BETK-hankkeen julkaisut:

•	BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen[^3]<br>
•	Excel-taulukko muuttujista[^4]<br>
• Esimerkki malli IFC-muodossa [^5]<br>
•	Soveltamisohje GS1 EPCIS (tapahtumatieto) käytöstä [syksyllä tehdään]<br>
•	Keskustelupaperi sijaintitiedoista rakennushankkeessa<br>
•	Huomioita sijaintiedosta betonielementtien toimitusketjussa<br>

[^1]: https://www.elementtisuunnittelu.fi/suunnitteluprosessi/mallintava-suunnittelu
[^2]: https://www.elementtisuunnittelu.fi/runkorakenteet/elementtitunnukset
[^3]: BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen
[^4]: Excel-taulukko muuttujista
[^5]: Esimerkki malli IFC-muodossa

## 2 Soveltamisohjeen tarkoitus ja rajaukset
Soveltamisohje keskittyy suunnittelijan tuottaman tietomallin sisällön vakiointiin tarjousvaiheessa. Samalla BETK-hankkeessa on BEC2012-tietokenttien nimeämistä tarkennettu ja IFC-malliin kirjoitettavia ominaisuus-tietoja määritetty elementtityyppikohtaiseksi tiedonsiirron laadun parantamiseksi. Samalla on tietokenttien nimeämisessä pyritty huomioimaan mahdollisesti tulevaisuudessa kehitettävää muiden rakenneosien ja materiaalien tunnistamista ja vakiointia. Tiedonsiirron vakiointia on myös kehitetty lisäämällä sallittujen arvojen listauksia tietokenttiin, joissa se mahdollista ja järkevää tehdä. Ominaisuus-tiedoissa on huomioitu myös tietomallin rikastamista toteutusvaiheessa toimitusketjulta tulevilla tiedoilla.  Soveltamisohjetta täydentävät erillinen taulukko tietokentistä[^4] joissa mm. elementtien mittatiedot ja esimerkkitietomalli[^5]. Tätä soveltamisohjetta täydentää myös erillinen ohje elementtien yksilöinnistä toimitusketjussa[^3] ja esimerkki malli IFC-muodossa[^5]. Tätä soveltamisohjetta voidaan päivittää myöhemmin standardoinnin edetessä. Tämä soveltamisohje ei ota kantaa muuhun tarjouspyyntö aineistoon. 

## 3 Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa
Tarjousvaiheessa tietomallissa käytettävät tietokentät elementtityyppien tunnistamiseen on kuvattu alla olevissa taulukoissa. Taulukoiden arvojen lisäksi hankintavaiheessa tarvittavat mitta- ja pinta-alojen ominaisuudet kuvattu erillisessä excel-taulukossa [^4]. Excel-taulukossa on myös muita toteutusvaiheessa tarvittavia ominaisuus-tietoja sallittuine arvoineen

### 3.1 Elementin tuotetiedot tarjousvaiheessa

#### 3.1.1 Kokoonpanon tyyppi
Betonielementtien erottamiseen tietomallin muista objekteista ja kokoonpanoista voi käyttää kokoonpanon tyyppi-ominaisuustietoa. 

###### Taulukko 1.

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td><code>Kokoonpanon tyyppi</code></td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td><code>–</code></td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td><code>BETK-Tunnistetiedot ja luokittelu</code></td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td><code>Kokoonpanon tyyppi</code></td>
      </tr>
          <th rowspan="5">Sallitut arvot</th>
      <td><code>BETONIELEMENTTI</code></td>
     </tr>
    <tr>
      <td><code>PAIKALLAVALU</code></td>
     <tr>
      <td><code>PUUKOKOONPANO</code></td>
      </tr>
      <tr>
      <td><code>TERÄSKOKOONPANO</code></td>
       </tr>
      <tr>
      <td><code>EI ASETETTU</code></td>
    </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.2 Elementtityyppi
Elementtityyppi-ominaisuuden avulla voidaan tunnistaa eri elementtityypit. Tiedot syötetään laskenta-aineiston laadinnan yhteydessä ja päivitetään ja pidetään ajantasalla myös toteustusvaiheessa, jotta loppuselvityksessä voidaan tehdä tarvittaessa määrälaskenta käyttäen ominaisuutta elementtien ryhmittelyssä.

###### Taulukko 2. 

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">IFC tietokentät</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Tietosisältötarve</b></td>
            <td colspan="2"><b>Elementtityyppi</b></td>
        </tr>
          <tr>
            <td>Rajaukset</td>
            <td colspan="2">-</td>
        </tr>
        <tr>
            <td>Ominaisuusjoukko</td>
            <td colspan="2">BETK-hankinta</td>
        </tr>
         <tr>
            <td>Ominaisuus</td>
            <td colspan="2">Sallitut arvot jaetaan kahteen ominaisuuskenttään:  
Elementin tyyppi, koodi ( AK jne)
Elementin tyyppi, kuvaus (Sokkelipalkki jne)
</td>
        </tr>
        <tr>
            <td rowspan="67">Sallitut arvot<br>(Enumerated options)</td>
            <td><code>A</code></td>
            <td>Anturaelementti</td>
        </tr>
        <tr>
            <td><code>PH</code></td>
            <td>Pilariholkkielementti</td>
        </tr>
      <tr>
            <td><code>AN</code></td>
            <td>Sokkelielementti (ei-kantava)</td>
        </tr>
     <tr>
            <td><code>AS</code></td>
            <td>Sokkelielementti (kantava)</td>
        </tr>
      <tr>
            <td><code>AS</code></td>
            <td>Sokkelielementti (kantava)</td>
        </tr>
      <tr>
       <td><code>AK</code></td>
       <td>Sokkelipalkki</td>
      </tr>
    <tr>
     <td><code>AR</code></td>
     <td>Sokkeliruutuelementti (maanpaine)</td>
    </tr>
    <tr>
     <td><code>AV</code></td>
     <td>Sokkelielementti (yksi kuori)</td>
    </tr>
    <tr>
     <td><code>MP</code></td>
     <td>Maanpaineseinäelementti</td>
    </tr>
    <tr>
     <td><code>TKE</code></td>
     <td>Tukimuurielementti</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu perustuselementti</td>
    </tr>
    <tr>
     <td><code>P</code></td>
     <td>Pilari</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu pilarielementti</td>
    </tr>
    <tr>
     <td><code>V</code></td>
     <td>Väliseinä</td>
    </tr>
    <tr>
     <td><code>VSP</code></td>
     <td>Väliseinä (seinämäinen palkki)</td>
    </tr>
    <tr>
     <td><code>S</code></td>
     <td>Ruutuelementti (kantava)</td>
    </tr>
    <tr>
     <td><code>R</code></td>
     <td>Ruutuelementti (ei-kantava)</td>
    </tr>
    <tr>
     <td><code>SK</code></td>
     <td>Sisäkuorielementti (kantava)</td>
    </tr>
    <tr>
     <td><code>RK</code></td>
     <td>Sisäkuorielementti (ei-kantava)</td>
    </tr>
    <tr>
     <td><code>SKE</code></td>
     <td>Sisäkuorielementti (kantava, tehdaseriste)</td>
    </tr>
    <tr>
     <td><code>RKE</code></td>
     <td>Sisäkuorielementti (ei kantava, tehdaseriste)</td>
    </tr>
    <tr>
     <td><code>SKRO</code></td>
     <td>Ohutrapattu elementti (kantava)</td>
    </tr>
    <tr>
     <td><code>RKRO</code></td>
     <td>Ohutrapattu elementti (ei-kantava)</td>
    </tr>
    <tr>
     <td><code>SKRP</code></td>
     <td>Paksurapattu elementti (kantava)</td>
    </tr>
    <tr>
     <td><code>RKRP</code></td><td>Paksurapattu elementti (ei-kantava)</td>
    </tr>
    <tr>
     <td><code>NK</code></td>
     <td>Nauhaelementti (kantava)</td>
    </tr>
    <tr>
     <td><code>N</code></td>
     <td>Nauhaelementti (ei-kantava)</td>
    </tr>
    <tr>
     <td><code>KE</code></td>
     <td>Kuorielementti</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu seinäelementti</td>
    </tr>
    <tr>
     <td><code>K</code></td>
     <td>Palkkielementti (teräsbetoni)</td>
    </tr>
    <tr>
     <td><code>I</code></td>
     <td>Jännebetonipalkki (I-profiili)</td>
    </tr>
    <tr>
     <td><code>HI</code></td>
     <td>Jännebetonipalkki (HI-profiili)</td>
    </tr>
    <tr>
     <td><code>JK</code></td>
     <td>Jännebetonipalkki (muut profiilit)</td>
    </tr>
    <tr>
     <td><code>JR</code></td>
     <td>Jäykistesauva</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu palkkielementti</td>
    </tr>
    <tr>
     <td><code>L</code></td>
     <td>Laattaelementti (massiivilaatta, välipohja)</td>
    </tr>
    <tr>
     <td><code>EL</code></td>
     <td>Alapohjalaatta (massivilaatta, eristetty)</td>
    </tr>
    <tr>
     <td><code>JL</code></td>
     <td>Jännitetty laattaelementti</td>
    </tr>
    <tr>
     <td><code>O</code></td>
     <td>Ontelolaatta</td>
    </tr>
    <tr>
     <td><code>KL</code></td>
     <td>Kuorilaatta</td>
    </tr>
    <tr>
     <td><code>SL</code></td>
     <td>Luja-Superlaatta</td>
    </tr>
    <tr>
     <td><code>TT</code></td>
     <td>TT-laatta</td>
    </tr>
    <tr>
     <td><code>TEK</code></td>
     <td>TEK-laatta</td>
    </tr>
    <tr>
     <td><code>STT</code></td>
     <td>SuperTT-laatta</td>
    </tr>
    <tr>
     <td><code>HTT</code></td>
     <td>HTT-laatta</td>
    </tr>
    <tr>
     <td><code>RL</code></td>
     <td>Ripalaatta</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu laattaelementti</td>
    </tr>
    <tr>
     <td><code>C</code></td>
     <td>Parveke-elementti</td>
    </tr>
    <tr>
     <td><code>CL</code></td>
     <td>Parvekelaattaelementti</td>
    </tr>
    <tr>
     <td><code>CP</code></td>
     <td>Parvekepilari</td>
    </tr>
    <tr>
     <td><code>JCL</code></td>
     <td>Jännitetty parvekelaattaelementti</td>
    </tr>
    <tr>
     <td><code>UCL</code></td>
     <td>Ulokeparvekelaatta</td>
    </tr>
    <tr>
     <td><code>M</code></td>
     <td>Parvekepielielementti</td>
    </tr>
    <tr>
     <td><code>Z</code></td>
     <td>Parvekekaide-elementti</td>
    </tr>
    <tr>
     <td><code>CX</code></td>
     <td>Parvekekattoelementti</td>
    </tr>
    <tr>
     <td><code>JCX</code></td>
     <td>Jännitetty parvekkeen kattoelementti</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu parveke-elementti</td>
    </tr>
    <tr>
     <td><code>T</code></td>
     <td>Porraselementti</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu porraselementti</td>
    </tr>
    <tr>
     <td><code>HK</code></td>
     <td>Hissikuiluelementti</td>
    </tr>
    <tr>
     <td><code>HKA</code></td>
     <td>Hissikuilun pohjaelementti</td>
    </tr>
    <tr>
     <td><code>HKL</code></td>
     <td>Hissikuilun kattolaatta</td>
    </tr>
    <tr>
     <td><code>HKY</code></td>
     <td>Hissikuilun yläpään elementti</td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu hissikuilun elementti</td>
    </tr>
    <tr>
     <td><code>H</code></td>
     <td>Hormielementti</code></td>
    </tr>
    <tr>
     <td><code>MUU</code></td>
     <td>Muu erikoiselementti</td>
    </tr>
    <tr><td>Ei asetettu</td><td>Ei  asetettu</td></tr>
    </tbody>
</table>
</html>

#### 3.1.3 Raudoitus
Raudoitustietokentästä valitaan elementtityypin raudoitustyyppitieto. Description-kentässä tarkempi kuvaus. Esim R1 ja 2T10 ymp tai R2 ja 2T10 ymp , #10-200 mp. Tarvittaessa hankkeessa käytetyt raudoituskoodit voi tarkentaa erillisessä mallin mukana toimitettavassa dokumentissa. Esimerkkitaulukot raudoitustiedosta tarjousvaiheessa ohjeen lopussa. 

###### Taulukko 3. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">Raudoitusmäärä</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td colspan="2"><b>Raudoitus 1, koodi<br>Raudoitus 1, kuvaus<br>Raudoitus 2, koodi<br>Raudoitus 2, kuvaus</b></td>
      </tr>
          <th rowspan="11">Sallitut arvot<br>(Option list/String UDA)</th>
      <td>R1</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R2</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R3</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R4</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R5</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R6</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R7</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R8</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>R9</td>
      <td>Description</td>
     </tr>
        <tr>
        <td>Ei asetettu</td>
        <td></td>
     </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.4 Pintakäsittely
Pintakäsittely-tietokenttään merkitään tarjousvaiheessa elementin ulkokuoren pintakäsittely. Jos samassa elementissä useampaa pintakäsittelyä käytetään tarvittaessa arvoja PK2, PK3 tarkentamaan tyypitystä. Toteutusvaiheessa käytetään BY40 mukaista koodausta, ks. kohta 4. 

###### Taulukko 4.

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">Elementin pintakäsittely</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td colspan="2">Pintakäsittely</td>
      </tr>
          <th rowspan="30">Sallitut arvot<br>(Option list)</th>
      <td colspan="2">PK1</td>
     </tr>
    <tr>
      <td rowspan="8">(Enumerated options if selected)</td>
      <td>01 MUO-muottipinta</td>
    </tr>
       <tr>
         <td>02 TIIP-Tiililaatta pinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>03 KALV-Valukalvon päälle valettu pesubetoni-pinta</td>
         </tr>
      <tr>
         <td>04 MUK-Kuvioitua muottia vasten valettu pinta</td>
         </tr>
      <tr>
         <td>05 ER-Eristepinta</td>
         </tr>
      <tr>
         <td>06 SEM-Sementtiliiman poisto</td>
         </tr>
      <tr>
         <td>07 PESH- Hienopesubetonipinta</td>
         </tr>
      <tr>
         <td>08 MUU-Muu pinta</td>
         </tr>
      <tr>
      <td colspan="2">PK2</td>
      </tr>
             <tr>
      <td rowspan="8">(Enumerated options if selected)</td>
      <td>01 MUO-muottipinta</td>
    </tr>
       <tr>
         <td>02 TIIP-Tiililaatta pinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>03 KALV-Valukalvon päälle valettu pesubetoni-pinta</td>
         </tr>
      <tr>
         <td>04 MUK-Kuvioitua muottia vasten valettu pinta</td>
         </tr>
      <tr>
         <td>05 ER-Eristepinta</td>
         </tr>
      <tr>
         <td>06 SEM-Sementtiliiman poisto</td>
         </tr>
      <tr>
         <td>07 PESH- Hienopesubetonipinta</td>
         </tr>
      <tr>
         <td>08 MUU-Muu pinta</td>
         </tr>
      <tr>
      <td colspan="2">PK3 - 9 (jos tarvetta)</td>
       </tr>
          <tr>
      <td rowspan="8">(Enumerated options if selected)</td>
      <td>01 MUO-muottipinta</td>
    </tr>
       <tr>
         <td>02 TIIP-Tiililaatta pinta (poltetut tiilet)</td>
         </tr>
      <tr>
         <td>03 KALV-Valukalvon päälle valettu pesubetoni-pinta</td>
         </tr>
      <tr>
         <td>04 MUK-Kuvioitua muottia vasten valettu pinta</td>
         </tr>
      <tr>
         <td>05 ER-Eristepinta</td>
         </tr>
      <tr>
         <td>06 SEM-Sementtiliiman poisto</td>
         </tr>
      <tr>
         <td>07 PESH- Hienopesubetonipinta</td>
         </tr>
      <tr>
         <td>08 MUU-Muu pinta</td>
         </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.5 Väribetoni

Väribetoni-kenttään merkitään väribetonin väri.

<html>
<body>
  <table>
     <thead>
      <tr>
        <th>Tietosisältötarve</th>
        <td>Väribetoni</td>
</tr><tr>
        <th>Rajaukset</th>
        <td>–</td>
</tr><tr>
        <th>Ominaisuusjoukko</th>
        <td>BETK-Hankinta</td>
</tr><tr>
        <th>Ominaisuus</th>
        <td>Väribetoni</td>
</tr><tr>
      <th rowspan="10">Sallitut arvot<br>(String)</th>
      <td>01 Harmaa, värjätty</td>
</tr><tr>
      <td>02 MUS-Musta</td>
</tr><tr>
      <td>03 VAL-Valkoinen</td>
</tr><tr>
      <td>04 PUN-Punainen</td>
</tr><tr>
      <td>05 SIN-Sininen</td>
</tr><tr>
      <td>06 RUS-Ruskea</td>
</tr><tr>
      <td>07 VIH-Vihreä</td>
</tr><tr>
      <td>05 SIN-Sininen</td>
</tr><tr>
      <td>08 KEL-Keltainen</td>
</tr><tr>
      <td>Muu</td>      
         </tr>
    </tbody>
  </table>
</body>
</html>                        

#### 3.1.6 Vähähiilinen
Vähähiilinen-tiedon avulla mahdollista erotella tarjousvaiheessa vähähiiliseksi ajattelut tuotteet Kyllä/Ei-valinnalla. Toteutussuunnittelussa elementeille määritellään tarkemmat GWP-arvot.

###### Taulukko 5. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">Vähähiilinen</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td colspan="2">Vähähiilinen</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(String)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description </td>
    </tr>
    </tbody>
  </table>
</body>
</html>

#### 3.1.7 Tyyppielementti
Kyllä/-Ei-tieto elementistä, joka on varusteltu tietomallissa toteutusta vastaavaksi tyyppielementiksi. Tyyppielementti sisältää raudoitukset ja valutarvikkeet mallinnettuna. Tarjousvaiheessa valutarvikkeita ei ole yleensä mallinnettuna, joten tarjousvaiheessa tieto tarjousvaiheessa huomioitavista valutarvikkeista on kerrottava muussa tarjousaineistossa.

###### Taulukko 6. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">Tyyppielementti</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td colspan="2">Onko tyyppielementti</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(Boolean)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description</td>
    </tr>
    </tbody>
  </table>
</body>
</html>
      
#### 3.1.8	Työmaalla käännettävä elementti
Tieto työmaalla käännettävästä elementistä. Asennustyön hinnoittelua varten tarvittava tieto. Jos ei ole tietoa asennustavasta niin kenttä jätetään tyhjäksi.

###### Taulukko 7. 

<html>
<body>
  <table>
     <thead>
      <tr>
        <th scope="row">Tietosisältötarve</th>
        <td colspan="2">Kääntökivi</td>
      </tr>
      <tr>
        <th scope="row">Rajaukset</th>
        <td colspan="2">–</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuusjoukko</th>
        <td colspan="2">BETK-Hankinta</td>
      </tr>
      <tr>
        <th scope="row">Ominaisuus</th>
        <td colspan="2">Kääntökivi</td>
      </tr>
          <th rowspan="2">Sallitut arvot<br>(Boolean)</th>
      <td colspan="2">Ei</td>
     </tr>
    <tr>
      <td>Kyllä</td>
      <td>Description</td>
    </tr>
    </tbody>
  </table>
</body>
</html>

## 4	Toimintaohjeita hankkeisiin  
**Numerointi**   
Tässä ohjeessa kuvattu elementtityyppien yksilöinti ja tunnistaminen ei vaikuta hankkeissa käytettyyn toteutusvaiheen elementtien numerointiin ja piirustusten nimeämiseen. Numerointi voidaan sopia hankekohtaisesti huomioiden mm. Tekla Strucrures-ohjelman numeroinnin ominaisuudet. Jos toteutusvaiheessa käytetään Tuoteyksilöinti ja -tunnistaminen ohjeessa [^3] kuvattua tapaa elementtien yksilöintii ei ACN-numeron käytölle ole tarvetta.  

**Sijaintieto**  
Lohko- ja kerrostiedosta erillinen ohje  

**Revisiointi käytännöt**  

Toteutusvaiheessa tapahtuva revisiointi ja tiedonsiirto käyttäen Peppol-sanomia tarkennetaan myöhemmin.


## Lyhenteet ja terminologia

<html>
<table>
    <tbody>
        <tr>            
          <td>Alkuperäisformaatti</td>
          <td>Mallinnusohjelman oma tallennusformaatti. Alan julkaisuissa käytetään tälle synonyyminä käsitteitä natiivimalli tai natiiviformaatti.</td>
        </tr>
        <tr>
           <td>BIM</td>
          <td>Rakennuskohteen tietomalli tai tietomallinnus, lyhenne englanninkielisestä käsitteestä Building Information Modeling.</td>
        </tr>
        <tr>
          <td>IFC</td>
          <td>Rakennusten mallinnuksessa käytetty tuotetietojen siirron kansainvälinen standardi, lyhenne englanninkielisestä käsitteestä Industry Foundation Classes. </td>
        </tr>
         <tr>
          <td>UDA</td>
          <td>Suunnitteluohjelmistoissa mallin objekteille talletettavaa liitännäistietoa (metatieto), lyhenne englanninkielisestä käsitteestä User Defined Attribute.</td>
        </tr>
        <tr>
          <td>Ominaisuusryhmä</td>
          <td>Rakentamisalalla on yleisesti käytössä ”Property Set” -termi. Tässä dokumentissa käytetään termiä ”Ominaisuusryhmä”, jotta termi on helpommin ymmärrettävissä ja päästään eroon vieraskielisestä termistä. Ominaisuusryhmien tarkka määrittäminen mahdollistaa ominaisuuksien ryhmittelyn ihmiselle sopiviin kokonaisuuksiin. Usealla ominaisuusryhmällä vältetään myös ominaisuuksien pitkä listaus yhdessä ”kaiken kattavassa” ominaisuusryhmässä. </td>
        </tr>
           <tr>
          <td>Ominaisuus</td>
          <td>Rakentamisalalle on vakiintunut ”Property” -termin käyttö. Tässä dokumentissa käytetään termiä ”Ominaisuus”, jotta termi on helpommin ymmärrettävissä ja päästään eroon vieraskielisestä termistä. Ominaisuuksien tarkka määrittäminen mahdollistaa vakioidun tietorakenteen. Ominaisuudet on aina liitetty johonkin ominaisuusryhmään. </td>
        </tr>
    </tbody>
</table>
</html>

## Liite 1: Esimerkkejä raudoitustiedosta betonielementti tehtaan tarjouslaskennassa

<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>V</th>
      <th>1.krs 20%</th>
      <th>2.krs 50%</th>
      <th>3–4.krs</th>
      <th>5.krs</th>
      <th>6–9.krs</th>
      <th>10–14.krs</th>
      <th>15–16.krs</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Paksuus (mm)</td>
      <td>250</td>
      <td>200 / 240 / 250</td>
      <td>200 / 240 / 250</td>
      <td>200 / 220 / 250</td>
      <td>200 / 220 / 250</td>
      <td>200 / 220 / 250</td>
      <td>200 / 220 / 250</td>
    </tr>
    <tr>
      <td>Bet. lujuus</td>
      <td>C35/45</td>
      <td>C35/45</td>
      <td>C35/45</td>
      <td>C35/45</td>
      <td>C35/45</td>
      <td>C35/45</td>
      <td>C35/45</td>
    </tr>
    <tr>
      <td>Pääteräs</td>
      <td>#10-k200 MP</td>
      <td>#10-k150 MP</td>
      <td>#10-k150 MP</td>
      <td>#10-k150 MP</td>
      <td>#8-k150 MP</td>
      <td>ei verkoraud.</td>
      <td>ei verkoraud.</td>
    </tr>
    <tr>
      <td>Lisäraudoitus, vaaka</td>
      <td>-</td>
      <td>4+4T16 (VSP)</td>
      <td>–</td>
      <td>–</td>
      <td>–</td>
      <td>–</td>
      <td>–</td>
    </tr>
    <tr>
      <td>Haat elem. ymp.</td>
      <td>T10-k200</td>
      <td>T10-k150</td>
      <td>T10-k150</td>
      <td>T10-k150</td>
      <td>T8-k150</td>
      <td>–</td>
      <td>–</td>
    </tr>
    <tr>
      <td>Reunaraud. ymp.</td>
      <td>2T12</td>
      <td>2T12</td>
      <td>2T12</td>
      <td>2T12</td>
      <td>2T12</td>
      <td>2T10</td>
      <td>2T10</td>
    </tr>
    <tr>
      <td>Pilariosat PT</td>
      <td>–</td>
      <td>4+4T16</td>
      <td>4+4T16</td>
      <td>4+4T16</td>
      <td>4+4T16</td>
      <td>4+4T10</td>
      <td>2+2T10</td>
    </tr>
    <tr>
      <td>Pilariosat UH</td>
      <td>–</td>
      <td>T10-k125</td>
      <td>T10-k150</td>
      <td>T10-k150</td>
      <td>T10-k150</td>
      <td>T8-k200</td>
      <td>T8-k200</td>
    </tr>
    <tr>
      <td>Palkkiosat PT</td>
      <td>2+2T16</td>
      <td>2+2T20</td>
      <td>2+2T20</td>
      <td>2+2T16</td>
      <td>2+2T16</td>
      <td>2+2T16</td>
      <td>2+2T12</td>
    </tr>
    <tr>
      <td>Palkkiosat UH</td>
      <td>T10-k200</td>
      <td>T10-k100</td>
      <td>T10-k100</td>
      <td>T10-k100</td>
      <td>T10-k100</td>
      <td>T10-k150</td>
      <td>T10-k200</td>
    </tr>
  </tbody>
</table>

<details> 
<Summary>Yaml versio</Summary>

```
rakennetyyppi: "V"
kuvaus: "Betonirakenteiden paksuudet, lujuudet ja raudoitukset kerrosluvun mukaan"

kerrokset:

  1.krs_20%:
    paksuus_mm: 250
    betonilujuus: C35/45
    paatera: "#10-k200 MP"
    lisaraudoitus_vaaka: null
    haat_elementti: T10-k200
    reunaraudoitus_ymp: 2T12
    pilariosat:
      pt: null
      uh: null
    palkkiosat:
      pt: "2+2T16"
      uh: "T10-k200"

  2.krs_50%:
    paksuus_mm: "200 / 240 / 250"
    betonilujuus: C35/45
    paatera: "#10-k150 MP"
    lisaraudoitus_vaaka: "4+4T16 (VSP)"
    haat_elementti: T10-k150
    reunaraudoitus_ymp: 2T12
    pilariosat:
      pt: "4+4T16"
      uh: "T10-k125"
    palkkiosat:
      pt: "2+2T20"
      uh: "T10-k100"

  3-4.krs:
    paksuus_mm: "200 / 240 / 250"
    betonilujuus: C35/45
    paatera: "#10-k150 MP"
    lisaraudoitus_vaaka: null
    haat_elementti: T10-k150
    reunaraudoitus_ymp: 2T12
    pilariosat:
      pt: "4+4T16"
      uh: "T10-k150"
    palkkiosat:
      pt: "2+2T20"
      uh: "T10-k100"

  5.krs:
    paksuus_mm: "200 / 220 / 250"
    betonilujuus: C35/45
    paatera: "#10-k150 MP"
    lisaraudoitus_vaaka: null
    haat_elementti: T10-k150
    reunaraudoitus_ymp: 2T12
    pilariosat:
      pt: "4+4T16"
      uh: "T10-k150"
    palkkiosat:
      pt: "2+2T16"
      uh: "T10-k100"

  6-9.krs:
    paksuus_mm: "200 / 220 / 250"
    betonilujuus: C35/45
    paatera: "#8-k150 MP"
    lisaraudoitus_vaaka: null
    haat_elementti: T8-k150
    reunaraudoitus_ymp: 2T12
    pilariosat:
      pt: "4+4T16"
      uh: "T10-k150"
    palkkiosat:
      pt: "2+2T16"
      uh: "T10-k100"

  10-14.krs:
    paksuus_mm: "200 / 220 / 250"
    betonilujuus: C35/45
    paatera: "ei verkoraud."
    lisaraudoitus_vaaka: null
    haat_elementti: null
    reunaraudoitus_ymp: 2T10
    pilariosat:
      pt: "4+4T10"
      uh: "T8-k200"
    palkkiosat:
      pt: "2+2T16"
      uh: "T10-k150"

  15-16.krs:
    paksuus_mm: "200 / 220 / 250"
    betonilujuus: C35/45
    paatera: "ei verkoraud."
    lisaraudoitus_vaaka: null
    haat_elementti: null
    reunaraudoitus_ymp: 2T10
    pilariosat:
      pt: "2+2T10"
      uh: "T8-k200"
    palkkiosat:
      pt: "2+2T12"
      uh: "T10-k200"


```
</details> 

---


<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>S, SK (ei parv)</th>
      <th>1.krs</th>
      <th>2.krs</th>
      <th>3–4.krs</th>
      <th>5.krs</th>
      <th>6–9.krs</th>
      <th>10–14.krs</th>
      <th>15–16.krs</th>
      <th>Vesikatto</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Paksuus (SK), mm</td>
      <td>–</td><td>250</td><td>250</td><td>200</td><td>200</td><td>180</td><td>180</td><td>180</td>
    </tr>
    <tr>
      <td>Paksuus (UK), mm</td>
      <td>–</td><td>0</td><td>0</td><td>0 / 135</td><td>0 / 135</td><td>0 / 135</td><td>0 / 135</td><td>135</td>
    </tr>
    <tr>
      <td>Bet. lujuus (SK)</td>
      <td>–</td><td>C35/45</td><td>C35/45</td><td>C35/45</td><td>C35/45</td><td>C35/45</td><td>C35/45</td><td>C35/45</td>
    </tr>
    <tr>
      <td>Bet. lujuus (UK)</td>
      <td>–</td><td>–</td><td>–</td><td>C30/37 säänkest.</td><td>C30/37 säänkest.</td><td>C30/37 säänkest.</td><td>C30/37 säänkest.</td><td>C30/37 säänkest.</td>
    </tr>
    <tr>
      <td>Reunaraudoitus ymp. (SK)</td>
      <td>–</td><td>2T12</td><td>2T12</td><td>2T12</td><td>2T12</td><td>2T12</td><td>2T10</td><td>2T12</td>
    </tr>
    <tr>
      <td>Reunaraudoitus ymp. (UK)</td>
      <td>–</td><td>–</td><td>–</td><td>1E7</td><td>1E7</td><td>1E7</td><td>1E7</td><td>1E7</td>
    </tr>
    <tr>
      <td>Pääteräs (SK)</td>
      <td>–</td><td>#10-K150 MP</td><td>#10-K150 MP</td><td>#8-K150 MP</td><td>#8-K150 MP</td><td>#8-K200 MP (50%)</td><td>#8-K200 MP</td><td>#8-K200 MP</td>
    </tr>
    <tr>
      <td>Pääteräs (UK)</td>
      <td>–</td><td>–</td><td>–</td><td>#E5-150</td><td>#E5-150</td><td>#E5-150</td><td>#E5-150</td><td>#E5-150</td>
    </tr>
    <tr>
      <td>Haat elem. ymp.</td>
      <td>–</td><td>T10-K150</td><td>T10-K150</td><td>T8-K150</td><td>T8-K150</td><td>T8-K200</td><td>–</td><td>T8-K200</td>
    </tr>
    <tr>
      <td>Pilariosat &gt;980 mm (PT)</td>
      <td>–</td><td>2×8T20</td><td>2×8T16</td><td>2×6T20</td><td>2×6T16</td><td>2×6T12</td><td>2×4T10</td><td>–</td>
    </tr>
    <tr>
      <td>Pilariosat &gt;980 mm (UH)</td>
      <td>–</td><td>T10-K150</td><td>T10-K150</td><td>T8-K150</td><td>T8-K150</td><td>T8-K150</td><td>T8-K150</td><td>–</td>
    </tr>
    <tr>
      <td>Palkkiosat, ikkuna – yläosa (PT)</td>
      <td>–</td><td>2×2T20</td><td>2×2T16</td><td>2×2T16</td><td>2×2T16</td><td>2×2T16</td><td>2×2T12</td><td>–</td>
    </tr>
    <tr>
      <td>Palkkiosat, ikkuna – yläosa (UH)</td>
      <td>–</td><td>T10-K100</td><td>T10-K100</td><td>T10-K100</td><td>T10-K125</td><td>T10-K150</td><td>T10-K150</td><td>–</td>
    </tr>
    <tr>
      <td>Palkkiosat, ikkuna – alaosa (PT)</td>
      <td>–</td><td>2×2T16</td><td>2×2T16</td><td>2×2T16</td><td>2×2T16</td><td>2×2T16</td><td>2×2T12</td><td>–</td>
    </tr>
    <tr>
      <td>Palkkiosat, ikkuna – alaosa (UH)</td>
      <td>–</td><td>T10-K150</td><td>T10-K200</td><td>T10-K200</td><td>T10-K200</td><td>T10-K200</td><td>T10-K200</td><td>–</td>
    </tr>
  </tbody>
</table>

<details> 
<Summary>Yaml versio</Summary>

```
rakennetyyppi: "S, SK (ei parv)"
kuvaus: "Betonirakenteiden paksuudet, lujuudet ja raudoitukset kerrosluvun mukaan"

kerrokset:

  1.krs:
    paksuus:
      sk_mm: null
      uk_mm: null
    betonilujuus:
      sk: null
      uk: null
    reunaraudoitus:
      sk: null
      uk: null
    paatera:
      sk: null
      uk: null
    haat_elementti: null
    pilariosat_yli_980mm:
      pt: null
      uh: null
    palkkiosat_ikkuna:
      ylaosa:
        pt: null
        uh: null
      alaosa:
        pt: null
        uh: null

  2.krs:
    paksuus:
      sk_mm: 250
      uk_mm: 0
    betonilujuus:
      sk: C35/45
      uk: null
    reunaraudoitus:
      sk: 2T12
      uk: null
    paatera:
      sk: "#10-K150 MP"
      uk: null
    haat_elementti: T10-K150
    pilariosat_yli_980mm:
      pt: "2x8T20"
      uh: "T10-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T20"
        uh: "T10-K100"
      alaosa:
        pt: "2x2T16"
        uh: "T10-K150"

  3-4.krs:
    paksuus:
      sk_mm: 250
      uk_mm: 0
    betonilujuus:
      sk: C35/45
      uk: null
    reunaraudoitus:
      sk: 2T12
      uk: null
    paatera:
      sk: "#10-K150 MP"
      uk: null
    haat_elementti: T10-K150
    pilariosat_yli_980mm:
      pt: "2x8T16"
      uh: "T10-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T16"
        uh: "T10-K100"
      alaosa:
        pt: "2x2T16"
        uh: "T10-K200"

  5.krs:
    paksuus:
      sk_mm: 200
      uk_mm: "0/135"
    betonilujuus:
      sk: C35/45
      uk: "C30/37 säänkest."
    reunaraudoitus:
      sk: 2T12
      uk: 1E7
    paatera:
      sk: "#8-K150 MP"
      uk: "#E5-150"
    haat_elementti: T8-K150
    pilariosat_yli_980mm:
      pt: "2x6T20"
      uh: "T8-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T16"
        uh: "T10-K100"
      alaosa:
        pt: "2x2T16"
        uh: "T10-K200"

  6-9.krs:
    paksuus:
      sk_mm: 200
      uk_mm: "0/135"
    betonilujuus:
      sk: C35/45
      uk: "C30/37 säänkest."
    reunaraudoitus:
      sk: 2T12
      uk: 1E7
    paatera:
      sk: "#8-K150 MP"
      uk: "#E5-150"
    haat_elementti: T8-K150
    pilariosat_yli_980mm:
      pt: "2x6T16"
      uh: "T8-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T16"
        uh: "T10-K125"
      alaosa:
        pt: "2x2T16"
        uh: "T10-K200"

  10-14.krs:
    paksuus:
      sk_mm: 180
      uk_mm: "0/135"
    betonilujuus:
      sk: C35/45
      uk: "C30/37 säänkest."
    reunaraudoitus:
      sk: 2T12
      uk: 1E7
    paatera:
      sk: "#8-K200 MP (50%)"
      uk: "#E5-150"
    haat_elementti: T8-K200
    pilariosat_yli_980mm:
      pt: "2x6T12"
      uh: "T8-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T16"
        uh: "T10-K150"
      alaosa:
        pt: "2x2T16"
        uh: "T10-K200"

  15-16.krs:
    paksuus:
      sk_mm: 180
      uk_mm: "0/135"
    betonilujuus:
      sk: C35/45
      uk: "C30/37 säänkest."
    reunaraudoitus:
      sk: 2T10
      uk: 1E7
    paatera:
      sk: "#8-K200 MP"
      uk: "#E5-150"
    haat_elementti: null
    pilariosat_yli_980mm:
      pt: "2x4T10"
      uh: "T8-K150"
    palkkiosat_ikkuna:
      ylaosa:
        pt: "2x2T12"
        uh: "T10-K150"
      alaosa:
        pt: "2x2T12"
        uh: "T10-K200"

  vesikatto:
    paksuus:
      sk_mm: 180
      uk_mm: 135
    betonilujuus:
      sk: C35/45
      uk: "C30/37 säänkest."
    reunaraudoitus:
      sk: 2T12
      uk: 1E7
    paatera:
      sk: "#8-K200 MP"
      uk: "#E5-150"
    haat_elementti: T8-K200

```
</details> 

## Viittaukset




