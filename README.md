# Simczech: predikce pro volby 2026

Predikce Simczech pro komunální a senátní volby 9. a 10. října 2026 a pro druhé kolo senátních voleb 16. a&nbsp;17.&nbsp;října 2026 (oddíl „Senát, 2. kolo“ níže). Poslední verze je ta, kterou právě zobrazuje [simczech.cz](https://simczech.cz/volby-2026/).

Každá verze tu má vlastní složku a vlastní seznam otisků s časovými razítky. Otisk je krátký kód vypočítaný z obsahu souboru; když se v souboru změní jediný znak, vyjde jiný otisk.

| Verze | Soubory | Seznam otisků a razítka |
|---|---|---|
| sobota 10. října 2026, 13:39 | `predikce/2026-10-10_1339/` | `razitka/2026-10-10_1339/` |
| pátek 9. října 2026, 20:58 | `predikce/2026-10-09_2058/` | `razitka/2026-10-09_2058/` |

Sobotní verze je poslední. Od páteční se liší ve třech souborech: v predikcích pro obce Rosička (`forecasts/obec-549941.json`) a Blatnička (`forecasts/obec-586056.json`) a v přehledu `summary.json`. V každé z těchto obcí přišla jedna kandidátní listina po registraci o část kandidátů. Páteční verze s tím v odhadu podílu hlasů této listiny nepočítala, sobotní ano. Ostatních 6&nbsp;415 souborů je stejných. Páteční verze tu zůstává.

## Senát, 2. kolo (16. a&nbsp;17.&nbsp;října 2026)

Odhad druhého kola senátních voleb ve 22 obvodech, ve kterých se o&nbsp;senátorovi rozhoduje ve druhém kole. Každá verze je jeden soubor `runoff.json` s&nbsp;vlastním seznamem otisků a&nbsp;časovými razítky.

| Verze | Soubor | Seznam otisků a&nbsp;razítka |
|---|---|---|
| pátek 16.&nbsp;října 2026, 12:33 | `predikce/senat-2-kolo/2026-10-16_1233/runoff.json` | `razitka/senat-2-kolo/2026-10-16_1233/` |
| pátek 16.&nbsp;října 2026, 0:46 | `predikce/senat-2-kolo/2026-10-16_0046/runoff.json` | `razitka/senat-2-kolo/2026-10-16_0046/` |
| čtvrtek 15.&nbsp;října 2026, 14:44 | `predikce/senat-2-kolo/2026-10-15_1444/runoff.json` | `razitka/senat-2-kolo/2026-10-15_1444/` |
| pondělí 12.&nbsp;října 2026, 0:18 | `predikce/senat-2-kolo/2026-10-12_0018/runoff.json` | `razitka/senat-2-kolo/2026-10-12_0018/` |

Poslední je páteční verze vydaná ve&nbsp;12:33; používá ji [simczech.cz](https://simczech.cz/volby-2026/senat/2-kolo). Nahradila verzi vydanou v&nbsp;0:46, kterou web používal ráno 16.&nbsp;října. Odhady 22&nbsp;soubojů i&nbsp;účasti zůstaly stejné; navíc uvádí rozmezí počtu senátorů podle stran vymezené prostřední polovinou simulací (`summary.seats[].low50`, `high50`). Verze vydaná v&nbsp;0:46 přidala ke čtvrteční verzi pouze odhad celkové účasti ve 22&nbsp;obvodech (`summary.turnout`). Čtvrteční verzi web používal od 15. do 16.&nbsp;října, pondělní od 12. do 15.&nbsp;října. Razítko pondělní verze vzniklo 15.&nbsp;října ve&nbsp;13:22; dokládá existenci souboru před hlasováním, ne dobu zveřejnění.

| Položka | Význam |
|---|---|
| `districts.senat-<číslo obvodu>` | Jeden senátní obvod. |
| `pair` | Dva kandidáti druhého kola; první z&nbsp;nich je tip podle odhadu. |
| `chance` | Šance na zvolení (0 až 1). |
| `share` | Odhad podílu hlasů ve druhém kole v&nbsp;procentech. |
| `low`, `high` | Rozmezí tohoto odhadu (80&nbsp;%). |
| `turnout` | Odhad účasti ve druhém kole v&nbsp;procentech (`r2`) a&nbsp;jeho rozmezí (`low`, `high`). |
| `summary.seats` | Očekávaný počet senátorů podle stran (průměr a&nbsp;rozmezí), včetně pěti zvolených už v&nbsp;prvním kole. |
| `summary.expectedCorrect` | Očekávaný počet správných tipů z&nbsp;22 a&nbsp;jeho rozmezí. |
| `summary.turnout` | Odhad účasti ve všech 22&nbsp;obvodech dohromady v&nbsp;procentech (`r2`) a&nbsp;jeho rozmezí (`low`, `high`); `registered` je počet zapsaných voličů v&nbsp;těchto obvodech v&nbsp;1.&nbsp;kole. Od páteční verze vydané v&nbsp;0:46. |
| `summary.seats[].low50`, `high50` | Rozmezí počtu senátorů dané strany vymezené prostřední polovinou simulací. Od páteční verze vydané ve&nbsp;12:33. |

### Další odhady (sobota 17.&nbsp;října 2026, 13:51 a&nbsp;13:55)

Čtyři další odhady druhého kola, jiné než hlavní Simczech Original. Vznikly ve čtvrtek před hlasováním; časové razítko mají ze soboty 13:51, tedy z&nbsp;doby před uzavřením volebních místností ve&nbsp;14:00. Web je nezobrazuje.

| Odhad | Soubor |
|---|---|
| Simczech Tamarillo | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1351/tamarillo.json` |
| Simczech Cherimoya | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1351/cherimoya.json` |
| Simczech Mangostana | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1351/mangostana.json` |
| Simczech Sapote | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1351/sapote.json` |

Seznam otisků a&nbsp;razítka jsou v&nbsp;`razitka/senat-2-kolo/dalsi-odhady-2026-10-17_1351/`.

Ve&nbsp;13:55 přibyly další dva odhady, rovněž vytvořené ve čtvrtek před hlasováním; Simczech Akebia obsahuje jen odhad podílu hlasů. Seznam otisků a&nbsp;razítka jsou v&nbsp;`razitka/senat-2-kolo/dalsi-odhady-2026-10-17_1355/`.

| Odhad | Soubor |
|---|---|
| Simczech Akebia | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1355/akebia.json` |
| Simczech Bilimbi | `predikce/senat-2-kolo/dalsi-odhady-2026-10-17_1355/bilimbi.json` |
 Položky souborů mají stejný význam jako v&nbsp;`runoff.json`; souhrn za všechny obvody (`summary`) neobsahují.

Ověření poslední verze:

```sh
cd predikce/senat-2-kolo/2026-10-16_1233
shasum -a 256 -c ../../../razitka/senat-2-kolo/2026-10-16_1233/SHA256SUMS
openssl ts -reply -in ../../../razitka/senat-2-kolo/2026-10-16_1233/SHA256SUMS.digicert.tsr -text
```

## K čemu to je

Každý si může ověřit dvě věci:

1. Predikce existovaly dřív, než začalo sčítání hlasů: první verze v pátek 9. října ve 20:58, poslední v sobotu 10. října ve 13:39, před uzavřením volebních místností ve 14:00.
2. Soubory ve složkách `predikce/2026-10-09_2058/` a `predikce/2026-10-10_1339/` jsou přesně ty, které dostaly razítko.

## Co tu je

Složka každé verze v `predikce/` obsahuje:

| Soubor | Co to je |
|---|---|
| `forecasts/obec-<kód obce>.json` | Predikce pro zastupitelstvo obce (6&nbsp;249 souborů). |
| `forecasts/mc-<kód>.json` | Predikce pro zastupitelstvo městské části nebo městského obvodu (140 souborů). |
| `forecasts/senat-<číslo obvodu>.json` | Predikce pro senátní obvod (27 souborů). |
| `manifest.json` | Seznam odhadů a jejich názvy. |
| `summary.json` | Přehled hlavního odhadu za všechna místa. |

Složka každé verze v `razitka/` obsahuje:

| Soubor | Co to je |
|---|---|
| `SHA256SUMS` | Seznam otisků SHA-256 všech 6&nbsp;418 souborů verze. |
| `SHA256SUMS.digicert.tsr` | Časové razítko tohoto seznamu od autority DigiCert (RFC 3161). |
| `SHA256SUMS.freetsa.tsr` | Časové razítko tohoto seznamu od autority FreeTSA (RFC 3161). |
| `SHA256SUMS.ots` | Časové razítko tohoto seznamu v blockchainu Bitcoinu (OpenTimestamps). |

Páteční verze: razítka DigiCert a FreeTSA nesou čas 9. října 2026, 20:58:30 (18:58:30 UTC). Zápis v blockchainu Bitcoinu je v blocích 970675, 970676, 970680 a 970681, vytěžených v pátek 9. října mezi 22:14 a 23:40.

Sobotní verze: razítko FreeTSA nese čas 10. října 2026, 13:39:31 (11:39:31 UTC), razítko DigiCert 13:39:32 (11:39:32 UTC). Zápis do blockchainu Bitcoinu trvá obvykle několik hodin; soubor `SHA256SUMS.ots` této verze ho zatím neobsahuje, doplníme ho později. Čas před 14:00 dokládají razítka FreeTSA a DigiCert.

## Co je v souborech

Každý soubor ve složce `forecasts/` obsahuje několik odhadů (`methods`). Hlavní je Simczech Original 👑: v obcích a městských částech má označení `kiwano`, v senátních obvodech `yuzu`. Názvy ostatních jsou v souboru `manifest.json`. Některé odhady jsou jen u části míst a některé mají jen část položek.

Obce a městské části. Soubor má seznam volebních obvodů `wards`: všude je jeden, jen Lišov má dva. Obvod uvádí počet volených mandátů (`seats`) a kandidátní listiny (`lists`). Odhad pro listinu je v `methods.<odhad>.lists` pod jejím číslem (`no`; pořadí na hlasovacím lístku je v `ballot`):

| Položka | Význam |
|---|---|
| `share` | Odhad podílu hlasů v procentech. |
| `low`, `high` | Širší rozmezí tohoto odhadu. |
| `low50`, `high50` | Užší rozmezí tohoto odhadu. |
| `seats` | Odhad počtu mandátů (průměr). |
| `seatsLow`, `seatsHigh` | Rozmezí počtu mandátů. |
| `first` | Šance, že listina získá nejvíc hlasů (0 až 1). |

Senátní obvody. Kandidáti jsou v `candidates`; odhad pro kandidáta je v `methods.<odhad>.candidates` pod jeho číslem (`no`):

| Položka | Význam |
|---|---|
| `r1` | Odhad podílu hlasů v prvním kole v procentech. |
| `low`, `high`, `low50`, `high50` | Širší a užší rozmezí tohoto odhadu. |
| `advance` | Šance na postup do druhého kola (0 až 1); zvolení už v prvním kole se sem nepočítá. |
| `outright` | Šance na zvolení už v prvním kole (0 až 1). |
| `elected` | Šance, že se kandidát stane senátorem (0 až 1). |

Položka `turnout` obsahuje odhad volební účasti v procentech (`mean`) a jeho rozmezí; v senátních obvodech zvlášť pro první a druhé kolo (`r1`, `r2`). Položka `actual` je prázdná (`null`): výsledky voleb v souborech nejsou.

## Jak to ověřit

Příkazy jsou pro poslední verzi; u starší stačí změnit název složky.

Shoda souborů se seznamem otisků:

```sh
cd predikce/2026-10-10_1339
shasum -a 256 -c ../../razitka/2026-10-10_1339/SHA256SUMS
```

U každého souboru musí být `OK`.

Kdy razítko vzniklo a co bylo orazítkováno (z kořenové složky repozitáře):

```sh
openssl ts -reply -in razitka/2026-10-10_1339/SHA256SUMS.digicert.tsr -text
shasum -a 256 razitka/2026-10-10_1339/SHA256SUMS
```

Řádek `Time stamp` je čas razítka v UTC. Údaj `Message data` je otisk seznamu; musí být stejný jako otisk z druhého příkazu. `openssl` ho vypisuje po dvojicích znaků na dvou řádcích, `shasum` vcelku.

Pravost razítka ověří příkaz `openssl ts -verify` (OpenSSL 3) podle kořenového certifikátu autority. Zápis v blockchainu ověří příkaz `ots verify` nebo ověřovač na [opentimestamps.org](https://opentimestamps.org) (u sobotní verze až po doplnění zápisu).
