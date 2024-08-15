# Spring Boot -palvelun julkaiseminen Rahti-ympäristössä

## Tavoite

Tässä ohjeessa käydään läpi Spring-palvelun julkaisu Rahti-palvelussa. 

Oletuksena on, että 

- julkaistavassa palvelussa on Spring-palvelin ja relaatiotietokanta
- julkaisu tehdään GitHub-repositoriosta. 

Julkaisu tehdään esimerkissä vaiheittain.

## Ennakkovaatimukset

Resepti edellyttää seuraavia toimenpiteitä:

- [Komentorivityökalun asennus](ohje_rahti_komentorivityokalun_asennus.md)

## Resepti

1. [Luo Rahti-projekti](ohje_rahti_projektin_luonti.md){target="_blank"}
2. [Luo projektiin tietokanta](ohje_rahti_tietokantapalvelun_luominen.md){target="_blank"}
3. [Julkaise Spring-palvelin ilman ulkoista tietokantaa](ohje_spring_rahti_ilman_tietokantaa.md){target="_blank"}
4. [Konfiguroi Spring-palvelin käyttämään ulkoista tietokantapalvelua](ohje_spring_rahti_tietokannan_konfigurointi.md){target="_blank"}

```mermaid
flowchart LR
  classDef highlight fill:#ffe2ff,stroke:#996d99,stroke-width:3px;

  step1[Rahti-projektin luonti]
  step2[Tietokantapalvelun luonti]
  step3[Spring Boot -palvelimen julkaisu]
  step4[Tietokannan konfigurointi]

  step1-->step2
  step2-->step3
  step3-->step4
```

## Lisäohjeita

- [Virheenjäljitys](ohje_rahti_virheenjaljitys.md)
- [HTTPS-konfigurointi](ohje_rahti_https_konfigurointi.md)
- [Julkaisu yksityisestä repositoriosta](ohje_rahti_julkaisu_yksityisesta_repositoriosta.md)

## Liittyviä ohjeita

- [Julkaisu paikallisesta hakemistosta JKube OpenShift Maven pluginilla](ohje_spring_rahti_jkube_plugin.md)