# SEO & URL-Optimalisatie Rapport

**Project:** Huisentuinsteigerhout.nl
**Onderwerp:** Herstructurering URL's, Interne Linkbuilding & Technische SEO

---

Beste [Naam Klant / Klant van MarketingBoer],

Om de zichtbaarheid van de webshop in Google verder te vergroten en de prestaties van de website te verbeteren, hebben we de afgelopen periode een ingrijpende optimalisatie uitgevoerd aan de structuur van de website. 

In dit verslag vind je een helder overzicht van de werkzaamheden die zijn uitgevoerd en wat dit betekent voor de vindbaarheid en techniek van de webshop.

### 1. Implementatie van een "Silo" URL-Structuur
Voorheen bevatte de website onnodig lange en complexe links. De focus lag op het creëren van een logische, hiërarchische structuur (een zogenaamde Silo-structuur). Dit helpt Google om de website beter te begrijpen en rankt producten sneller op voor de juiste zoektermen.

* **Verwijderen van de `/product/` toevoeging:** Alle producten hadden WooCommerce's standaard `/product/` in de link. Dit voegt voor SEO niets toe en maakt links onnodig lang. Deze vaste "base" hebben we over de hele website verwijderd.
* **Inkorten van overtollige zoekwoorden (Keyword stuffing):** Subcategorieën en producten bevatten vaak opeenhopingen van dezelfde woorden, wat ten koste gaat van de leesbaarheid.
  * *Voorbeeld oud:* `/douglashout-tuinmeubelen/douglashout-tuinsets/`
  * *Voorbeeld nieuw:* `/douglashout-tuinmeubelen/tuinsets/`
* **Resultaat:** Meer dan 127 product- en categorie-URL's zijn getrimd en geoptimaliseerd voor een schonere, strakkere uitstraling.

### 2. Vlekkeloze 301-Redirects (Geen 404's)
Wanneer je URL's wijzigt op een website die al bezocht wordt en in Google staat, loop je normaal gesproken het risico op dode links ("404 Not Found" errors).
* Om de opgebouwde "Link Waarde" in Google te behouden, hebben we voor élke gewijzigde pagina en elk product een permanente **301 Regex Redirect** ingesteld op serverniveau (`.htaccess`). 
* Dit resulteert erin dat alle oude links (bijv. via oude social media posts, Google zoekresultaten of externe websites) bliksemsnel en onzichtbaar doorsturen naar de nieuwe, korte URL's.
* **Resultaat:** Uit een onafhankelijke paginacrawl (met Screaming Frog) is gebleken dat we de wijziging hebben doorgevoerd met **0 Client Errors (0 dode links)**. 

### 3. Schoonmaak van Interne Links & "Redirect-chains"
Het instellen van redirects vangt extern verkeer op, maar het is van cruciaal belang dat de knoppen en teksten *op de website zelf* niet naar de oude URL's blijven wijzen. Als de site zichzelf constant moet doorverwijzen via redirects, vertraagt dit de laadtijd en "lekt" er SEO-waarde.
* Via een database-brede opschoonactie (Search & Replace) zijn in totaal honderden hyperlinks in menu's, themahuid, footers en tekstblokken direct omgeschreven naar de uiteindelijke URL.
* Oude "vervuiling" uit het verleden (zoals legacy OpenCart URL's: `index.php?route...`) is tevens direct met de wortel uitgeroeid en hersteld.
* **Resultaat:** De website linkt intern 100% efficiënt, zonder kostbare milliseconden te verliezen aan interne doorverwijzingen.

### 4. Overige Technische Validaties & H1-Optimalisaties
* **Database Backup:** Voorafgaand aan deze ingrijpende database-wijzigingen is alles veilig geback-upt naar een veilige externe repository als fallback.
* **H1 Titels:** De 7 belangrijkste hoofdpagina's (waaronder de Homepage en de hoofdcategorieën Steigerhout, Douglashout en Eikenhout) ontbeerden de belangrijkste HTML-tag voor zoekmachines: de **H1**. Deze zijn handmatig toegevoegd voor een aanzienlijke rankings-boost.

### Samenvatting
De fundering van *Huisentuinsteigerhout.nl* staat na deze ingreep ijzersterk. Met de geoptimaliseerde Silo-structuur, feilloze interne linkbuilding en het elimineren van dode links voldoet de winkel nu aan de strengste technische SEO-eisen uit de markt, wat direct zal bijdragen aan een betere indexatie en hogere posities.

Met vriendelijke groet,

[Jouw Naam / MarketingBoer]
