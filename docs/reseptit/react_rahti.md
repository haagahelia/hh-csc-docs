# React-sovelluksen julkaiseminen Rahti-ympäristössä

## Tavoite

Tässä ohjeessa käydään läpi React-sovelluksen julkaisu Rahti-palvelussa. 

Oletuksena on, että

- julkaisu tehdään GitHub-repositoriosta.

## Ennakkovaatimukset

Resepti edellyttää seuraavia toimenpiteitä:

- [Komentorivityökalun asennus](../rahti/komentorivityokalun_asennus.md)

## Resepti

```mermaid
flowchart LR
  classDef highlight fill:#ffe2ff,stroke:#996d99,stroke-width:3px;

  step1[Rahti-projektin luonti]
  step2[React-sovelluksen julkaisu]
  step3[Buildin automatisointi]

  step1-->step2
  step2-->step3
```

1. [Luo Rahti-projekti](../rahti/projektin_luonti.md)
2. [Julkaise React-sovellus](../rahti/react_julkaiseminen.md)
3. [Automatisoi build (valinnainen)](../rahti/buildin_automatisointi.md)

## Lisäohjeita

- [Virheenjäljitys](../rahti/virheenjaljitys.md)
- [HTTPS-konfigurointi](../rahti/https_konfigurointi.md)
- [Julkaisu yksityisestä repositoriosta](../rahti/julkaisu_yksityisesta_repositoriosta.md)



