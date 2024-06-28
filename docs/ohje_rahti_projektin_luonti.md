# Rahti-projektin luonti

Jotta Rahti-palvelua voi käyttää, pitää sen olla otettuna käyttöön MyCSC projektissa ja itse Rahti-palveluun pitää olla määriteltynä Rahti-projekti. 

Avaa Rahti-palvelun web-käyttöliittymä osoitteessa <https://rahti.csc.fi>, valitse Rahti-2 ja kirjaudu palveluun CSC-tunnuksellasi. Kirjautumisen jälkeen palvelun etusivu näyttää tältä:

![](img/rahti_portal.png)

Lisää itsellesi Rahti-projekti painamalla aloitussivun ’Create a new project’ linkkiä. Anna projektille kuvaava nimi.

![](img/rahti_create_project.png)

MyCSC:n projektinäkymässä näkyvä projektinumero tulee mainita Rahti-projektin kuvauskentässä projektia luotaessa. Tällä mekanismilla palvelun käytöstä syntyneet kulut kohdennetaan määriteltyyn MyCSC projektiin.

Kirjaa projektinumero projektin kommenttikenttään seuraavasti:
```
csc_project:<projektinumero>
```
Korvaa _\<projektinumero>_ oman MyCSC projektisi numerosarjalla.

Kun painat _Create_, luodaan Rahti-projekti, johon voidaan määritellä tarvittavia palveluja ja resursseja.

## Jäsenten lisääminen Rahti-projektiin

Rahti-projektit ovat sidottuja MyCSC projekteihin ja oletuksena näkyvät vain MyCSC projektin jäsenille. Projektiin voidaan lisätä muita käyttäjiä heidän CSC-tunnuksillaan _Administrator/User Management/RoleBindings_-asetuksen kautta.

![](img/rahti_add_member.png)

Voit Rahti-projektin omistajana näin lisätä kurssin opettajan omaan projektiisi. 
