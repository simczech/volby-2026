# Simczech: predikce pro volby 2026

Predikce Simczech pro komunální a senátní volby 9. a 10. října 2026.

Zatím je tu jen seznam jejich otisků s časovými razítky. Samotné predikce sem přidáme v sobotu 10. října ve 14:01, po uzavření volebních místností. Do té doby jsou k vidění na [simczech.cz](https://simczech.cz).

Otisk je krátký kód vypočítaný z obsahu souboru; když se v souboru změní jediný znak, vyjde jiný otisk.

## K čemu to je

Od soboty si každý může ověřit dvě věci:

1. Predikce existovaly v pátek 9. října večer, tedy dřív, než začalo sčítání hlasů.
2. Soubory, které tu v sobotu zveřejníme, jsou přesně ty, které v pátek dostaly razítko.

## Co tu je

Složka `razitka/2026-10-09_2058/`:

| Soubor | Co to je |
|---|---|
| `SHA256SUMS` | Seznam otisků SHA-256 všech 6&nbsp;418 souborů s predikcemi. |
| `SHA256SUMS.digicert.tsr` | Časové razítko tohoto seznamu od autority DigiCert (RFC 3161). |
| `SHA256SUMS.freetsa.tsr` | Časové razítko tohoto seznamu od autority FreeTSA (RFC 3161). |
| `SHA256SUMS.ots` | Časové razítko tohoto seznamu v blockchainu Bitcoinu (OpenTimestamps). |

Razítka DigiCert a FreeTSA nesou čas 9. října 2026, 20:58:30 (18:58:30 UTC). Zápis do blockchainu následuje s odstupem několika hodin.

## Jak to ověřit

Kdy razítko vzniklo a co bylo orazítkováno:

```sh
openssl ts -reply -in razitka/2026-10-09_2058/SHA256SUMS.digicert.tsr -text
shasum -a 256 razitka/2026-10-09_2058/SHA256SUMS
```

Řádek `Time stamp` je čas razítka v UTC. Údaj `Message data` je otisk seznamu; musí být stejný jako otisk z druhého příkazu. `openssl` ho vypisuje po dvojicích znaků na dvou řádcích, `shasum` vcelku.

Pravost razítka ověří příkaz `openssl ts -verify` (OpenSSL 3) podle kořenového certifikátu autority. Zápis v blockchainu ověří příkaz `ots verify` nebo ověřovač na [opentimestamps.org](https://opentimestamps.org).

Od soboty 14:01, až tu budou soubory s predikcemi:

```sh
cd predikce
shasum -a 256 -c ../razitka/2026-10-09_2058/SHA256SUMS
```

U každého souboru musí být `OK`.
