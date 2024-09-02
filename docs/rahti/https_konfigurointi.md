# HTTPS-konfigurointi

Julkaistu palvelu tarjotaan oletusarvoisesti vain HTTP-protokollalla. Palvelu voidaan konfiguroida tarjottavaksi myös HTTPS-protokollalla tai pelkästään HTTPS-protokollalla.

=== "Komentorivillä"

    Konfiguroinnin voi tehdä komentorivillä komennolla 
    ```bash
    oc create route edge --service=<service-name>
    ``` 

    Jos olet jo luonut suojaamattoman reitin eikä komento siksi onnistu, voit poistaa vanhan reitin komennolla 
    ```bash
    oc delete route <route-name>
    ```

    - `<route-name>` on reitin nimi. Reitin nimi on oletusarvoisesti sama kuin palvelun nimi. Voit listata olemassaolevat reitit komennolla `oc get route`.

=== "Web-käyttöliittymässä"

    Web-käyttöliittymässä määritys tehdään Rahti-sovelluksen Route-määrittelyssä.

    ![](img/rahti_routes.png)

    ![](img/rahti_route_edit.png )

    Reitille voidaan konfiguroida TLS käyttöön. Jos sertifikaatin jättää määrittämättä, käytetään oletussertifikaattia. HTTP-liikenteen voi joko sallia, estää tai uudelleenohjata.

    ![](img/rahti_route_enable_tls.png)

Lisätietoa: [Rahti Docs: Networking](https://docs.csc.fi/cloud/rahti/networking/)

