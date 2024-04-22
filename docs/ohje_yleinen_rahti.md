# Rahti-palvelun yleiset ohjeet

## Rahti-projektin luonti

Jotta Rahti-palvelua voi käyttää, pitää sen olla otettuna käyttöön MyCSC projektissa ja itse Rahti-palveluun pitää olla määriteltynä Rahti-projekti. 

Kirjaudu Rahti-palvelun web-käyttöliittymään osoitteessa <https://rahti.csc.fi:8443> CSC-tunnuksellasi. Kirjautumisen jälkeen palvelun etusivu näyttää tältä:

![](img/rahti_portal.png)

Lisää itsellesi Rahti-projekti painamalla ’Create Project’ painiketta näkymän oikeasta yläreunasta. Anna projektille kuvaava nimi.

![](img/rahti_create_project.png)

MyCSC:n projektinäkymässä näkyvä projektinumero tulee mainita Rahti-projektin kuvauskentässä projektia luotaessa. Tällä mekanismilla palvelun käytöstä syntyneet kulut kohdennetaan määriteltyyn MyCSC projektiin.

Kirjaa projektinumero projektin kommenttikenttään seuraavasti:
```
csc_project:<projektinumero>
```
Korvaa _\<projektinumero>_ oman MyCSC projektisi numerosarjalla.

Kun painat _Create_, luodaan Rahti-projekti, johon voidaan määritellä tarvittavia palveluja ja resursseja.

### Jäsenten lisääminen Rahti-projektiin

Rahti-projektit ovat henkilökohtaisia, eivätkä ne oletusarvoisesti näy muille. Projektiin voidaan lisätä muita käyttäjiä heidän CSC-tunnuksillaan _Resources/Membership_-asetuksen kautta.

![](img/rahti_add_member.png)

Voit Rahti-projektin omistajana näin lisätä projektitiimin jäsenet tai kurssin opettajan omaan projektiisi. 

## Openshift-komentorivityökalun asennus

Red Hat tarjoaa työkalun nimeltään `oc` OpenShift ympäristön hallintaan komentoriviltä käsin. Linkki `oc`-työkalun lataamiseen löytyy Rahti-palvelun hallintanäkymästä.

![](img/rahti_commandline_tools.png)

Linkistä avautuvalta sivustolta voi ladata omalle käyttöjärjestelmälle soveltuvan version. Linkeistä latautuu yksittäinen, suoritettava tiedosto nimeltään `oc`. Kyseisen tiedoston tulee löytyä käyttöjärjestelmän polusta (esim. Windows-ympäristön `PATH`-muuttujan määrittämässä sijainnissa) tai sen Spring-sovelluksen hakemistosta, mistä komentoja suoritetaan.

Jatkossa oletetaan, että `oc`-työkalu on asennettu polkuun. 

### Asennus Windows-ympäristössä

Kopioi `oc.exe` johonkin hakemistoon koneellasi (esimerkissä `c:\openshift\CLI`) ja lisää hakemisto polkuun.

```powershell
$Path = [Environment]::GetEnvironmentVariable("PATH", "User") + [IO.Path]::PathSeparator + "C:\openshift\CLI"
[Environment]::SetEnvironmentVariable( "Path", $Path, "User" )
```

## Rahti-palveluun kirjautuminen komentorivillä

Jotta `oc`-komentoja voi antaa, on kirjauduttava Rahti-palveluun komentorivin kautta. 

Kirjautumiskomennon saa web käyttöliittymänäkymän oikeasta yläkulmasta _oma nimi_ ja sen alta avautuvasta valikosta _Copy Login Command_.

![](img/rahti_copy_login_command.png)

Liitä komento leikepöydältä paikallisen koneesi komentoriville ja suorita se projektin juurihakemistossa.  

Huom! Jos `oc`-komento ei ole polussa, voi olla tarpeen antaa komennonlle myös polku, esim.
```bash
./oc login https://rahti.csc.fi:8443 -token=...
```

## Tietokantapalvelun luominen

Rahti-projektiin voi lisätä esivalmisteltuja kontteja _Browse Catalog_-näkymästä:

![](img/rahti_add_service.png)

![](img/rahti_browse_catalog.png)

Tässä esimerkissä käytetään MySQL-vaihtoehtoa. 

_Huom! Tarjolla olevat Ephemeral-versiot tietokantapalveluista käyttävät pelkästään väliaikaista tallennuskapasiteettia ja kaikki mahdolliset muutokset mm. tietokantaan häviävät samalla, kun kontin suoritus loppuu. Pysyvää tallennusta varten tulee valita "tavallinen" tietokantapalvelukontti ja sille dedikoitu Persistent Volume Claim (PVC) -tallennustila._

Etene luontivelhon näkymässä ’Next’ painikkeella konfigurointikohtaan ja täytä kontille haluamasi asetukset. Asetuksista kannattaa täydentää ainakin:

-	__Database Service Name__: Tietokantapalvelun nimi. Tällä nimellä muut kontit löytävät palvelun.
-	__MySQLConnection Username__: Käyttäjätunnus sql-palvelimelle kirjautumiseen.
-	__MySQL Connection Password__: Salasana sql-palvelimelle kirjautumiseen.
-	__MySQL Database Name__. Luotavan tietokannan nimi.

![](img/mysql_configuration_dialog.png)

Luontivelho tarjoaa mahdollisuuden luoda tietokannan luonnin yhteydessä salaisuustiedosto (_secret_), johon talletetaan tietokannan konfiguraatiotiedot. 

Salaisuus kannattaa luoda, sillä sitä käyttäen luottamuksellisia konfiguraatiotietoja ei tarvitse tallettaa versionhallintaan, eikä niitä tarvitse lainkaan käsitellä suoraan vaan ne voidaan tarvittaessa lukea salaisuustiedostosta.

![](img/mysql_create_secret.png)

Salaisuudet (ja muut vastaavat resurssit) löytyvät Rahti-palvelun web-käyttöliittymästä _Resources_-valikon alta.

![](img/rahti_resources_secret.png)

