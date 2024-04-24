# Spring Boot -palvelun julkaiseminen Rahti-ympäristössä

## Tavoite

Tässä ohjeessa käydään läpi Spring-palvelun julkaisu Rahti-palvelussa. 

Oletuksena on, että julkaistavassa palvelussa on Spring-palvelin sekä relaatiotietokanta. Julkaisu tehdään seuraavassa esimerkissä vaiheittain.

## Resepti

1. [Luo Rahti-projekti](ohje_yleinen_rahti.md#rahti-projektin-luonti)
2. [Luo projektiin tietokanta](ohje_yleinen_rahti.md#tietokantapalvelun-luominen)
3. [Julkaise Spring-palvelin ilman ulkoista tietokantaa](ohje_spring_rahti_ilman_tietokantaa.md)
4. [Konfiguroi Spring-palvelin käyttämään ulkoista tietokantapalvelua](ohje_spring_rahti_tietokannan_konfigurointi.md)

```mermaid
flowchart LR
  classDef highlight fill:#ffe2ff,stroke:#996d99,stroke-width:3px;

  step1[Rahti-projektin luonti]
  step2[Tietokantapalvelun luonti]
  step3[Spring Boot -palvelimen julkaisu]
  step4[Tietokannan konfigurointi]

  step1-->step2
  click step1 "/ohje_yleinen_rahti#rahti-projektin-luonti" "This is a link"
  step2-->step3
  step3-->step4
```

## Lisäohjeita

- Virheenjäljitys
- HTTPS-konfigurointi
- Projektin uudelleenluonti
- Julkaisu yksityisestä repositoriosta