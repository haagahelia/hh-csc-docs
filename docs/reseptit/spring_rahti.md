# Spring Boot -palvelun julkaiseminen Rahti-ympäristössä

## Tavoite

Tässä ohjeessa käydään läpi Spring-palvelun julkaisu Rahti-palvelussa. 

Oletuksena on, että 

- julkaistavassa palvelussa on Spring-palvelin ja relaatiotietokanta
- julkaisu tehdään GitHub-repositoriosta. 

Julkaisu tehdään esimerkissä vaiheittain.

## Ennakkovaatimukset

Jos halutaan käyttää komentorivikomentoja, resepti edellyttää seuraavia toimenpiteitä:

- [Komentorivityökalun asennus](../rahti/komentorivityokalun_asennus.md){target="_blank"}

## Resepti

```mermaid
flowchart LR
  classDef highlight fill:#ffe2ff,stroke:#996d99,stroke-width:3px;

  step1[Rahti-projektin luonti]
  step2[Tietokantapalvelun luonti]
  step3[Spring Boot -palvelimen julkaisu]
  step4[Tietokannan konfigurointi]
  step5[Buildin automatisointi]

  step1-->step2
  step2-->step3
  step3-->step4
  step4-->step5
```

1. [Luo Rahti-projekti](../rahti/projektin_luonti.md){target="_blank"}
2. [Luo projektiin tietokanta](../rahti/tietokantapalvelun_luominen.md){target="_blank"}
3. [Julkaise Spring-palvelin ilman ulkoista tietokantaa](../rahti/spring_ilman_tietokantaa.md){target="_blank"}
4. [Konfiguroi Spring-palvelin käyttämään ulkoista tietokantapalvelua](../rahti/spring_tietokannan_konfigurointi.md){target="_blank"}
5. [Automatisoi build (valinnainen)](../rahti/buildin_automatisointi.md){target="_blank"}

## Lisäohjeita

- [Virheenjäljitys](../rahti/virheenjaljitys.md){target="_blank"}
- [HTTPS-konfigurointi](../rahti/https_konfigurointi.md){target="_blank"}
- [Julkaisu yksityisestä repositoriosta](../rahti/julkaisu_yksityisesta_repositoriosta.md){target="_blank"}

## Liittyviä ohjeita

- [Julkaisu paikallisesta hakemistosta JKube OpenShift Maven pluginilla](../rahti/spring_jkube_plugin.md){target="_blank"}