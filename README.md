# CeneoScraperN11
## Etap 1 - Pobranie składowych pojedynczej opinii o konkretnym produkcie z serwisu [Ceneo.pl](https://www.ceneo.pl/)
1. Pobranie kodu pojedynczej strony z opiniami o produkcie
2. Analiza struktury kodu pojedyńczej opinii

|Składowa|Selektor CSS|Nazwa zmiennej|Typ danych|
|:-------|:-----------|:-------------|:---------|
|Opinia|`div.js_product-reviev`|review|string|
|Identyfikator opinii|`["data-entry-id"]`|review_id|string|
|Autor opinii|`span.user-post__author-name`|author|string|
|Rekomendacja|`span.user-post__author-recomendation`|recommendation||
|Liczba gwiazdek|`span.user-post__score-count`|stars|number|
|Treść Opinii|`div.user-post__text`|content||
|Lista zalet|`div.review-feature__col:has(> div[class*="positives"]) > div.review-feature__item`<br> div.review-feature__col:has(> div.review-feature__title--positives) > div.review-feature__item`<br>div.review-feature__title--positives ~ div.review-feature__item`|pros||
|Lista wad|`div.review-feature__col:has(> div[class*="negatives"]) > div.review-feature__item`<br> |||`div.review-feature__col:has(> div.review-feature__title--negatives) > div.review-feature__item`<br>`div.review-feature__title--negatives ~ div.review-feature__item`|cons||
|Dla ile osób przydatna|`span[id^="votes-yes"]`<br>`button.vote-yes["data-total-vote"]`<br>`button.vote-yes > span`|usefull||
|Dla ilu osób nieprzydatnych|`span[id^="votes-no"]`<br>`button.vote-no["data-total-vote"]`<br>`button.vote-no > span`|useless||
|Czy Potwierdzona zakupem|`div.review-pz`|purchased||
|Data wystawienia opinii|`span.user-post__publish > time:nth-child(1)["datetime"]`|review_date||
|Data zakupu produktu|`span.user-post__published > time:nth-child(2)["datetime"]`|purchase_date||


div.review-feature__col:has(> div.review-feature__title--positives) > div.review-feature__item
div.review-feature__col:has(> div[class*="positives"]) > div.review-feature__item
div.review-feature__title--positives ~ div.review-feature__item
