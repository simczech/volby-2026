# Simczech: predikce pro volby 2026

Predikce Simczech pro komunální a senátní volby 9. a 10. října 2026. Poslední verze je ta, kterou právě zobrazuje [simczech.cz](https://simczech.cz).

Každá verze tu má vlastní složku a vlastní seznam otisků s časovými razítky. Otisk je krátký kód vypočítaný z obsahu souboru; když se v souboru změní jediný znak, vyjde jiný otisk.

| Verze | Soubory | Seznam otisků a razítka |
|---|---|---|
| pátek 9. října 2026, 20:58 | `predikce/2026-10-09_2058/` | `razitka/2026-10-09_2058/` |

Pokud predikce do uzavření volebních místností ještě upravíme, přibude tu nová verze s vlastním razítkem. Starší verze zůstanou.

## K čemu to je

Každý si může ověřit dvě věci:

1. Predikce existovaly v pátek 9. října večer, tedy dřív, než začalo sčítání hlasů.
2. Soubory ve složce `predikce/2026-10-09_2058/` jsou přesně ty, které v pátek dostaly razítko.

## Co tu je

Složka `predikce/2026-10-09_2058/`:

| Soubor | Co to je |
|---|---|
| `forecasts/obec-<kód obce>.json` | Predikce pro zastupitelstvo obce (6&nbsp;249 souborů). |
| `forecasts/mc-<kód>.json` | Predikce pro zastupitelstvo městské části nebo městského obvodu (140 souborů). |
| `forecasts/senat-<číslo obvodu>.json` | Predikce pro senátní obvod (27 souborů). |
| `manifest.json` | Seznam odhadů a jejich názvy. |
| `summary.json` | Přehled hlavního odhadu za všechna místa. |

Složka `razitka/2026-10-09_2058/`:

| Soubor | Co to je |
|---|---|
| `SHA256SUMS` | Seznam otisků SHA-256 všech 6&nbsp;418 souborů s predikcemi. |
| `SHA256SUMS.digicert.tsr` | Časové razítko tohoto seznamu od autority DigiCert (RFC 3161). |
| `SHA256SUMS.freetsa.tsr` | Časové razítko tohoto seznamu od autority FreeTSA (RFC 3161). |
| `SHA256SUMS.ots` | Časové razítko tohoto seznamu v blockchainu Bitcoinu (OpenTimestamps). |

Razítka DigiCert a FreeTSA nesou čas 9. října 2026, 20:58:30 (18:58:30 UTC). Zápis v blockchainu Bitcoinu je v blocích 970675, 970676, 970680 a 970681, vytěžených v pátek 9. října mezi 22:14 a 23:40.

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

Shoda souborů se seznamem otisků:

```sh
cd predikce/2026-10-09_2058
shasum -a 256 -c ../../razitka/2026-10-09_2058/SHA256SUMS
```

U každého souboru musí být `OK`.

Kdy razítko vzniklo a co bylo orazítkováno:

```sh
openssl ts -reply -in razitka/2026-10-09_2058/SHA256SUMS.digicert.tsr -text
shasum -a 256 razitka/2026-10-09_2058/SHA256SUMS
```

Řádek `Time stamp` je čas razítka v UTC. Údaj `Message data` je otisk seznamu; musí být stejný jako otisk z druhého příkazu. `openssl` ho vypisuje po dvojicích znaků na dvou řádcích, `shasum` vcelku.

Pravost razítka ověří příkaz `openssl ts -verify` (OpenSSL 3) podle kořenového certifikátu autority. Zápis v blockchainu ověří příkaz `ots verify` nebo ověřovač na [opentimestamps.org](https://opentimestamps.org).
