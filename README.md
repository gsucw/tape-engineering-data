# Adhesive tape engineering data

Open reference data for engineers who specify pressure-sensitive tapes and die-cut tape parts:

- **Tape spec unit factors**: peel adhesion, thickness, bond strength, coat weight, foam density and roll length, with exact conversion factors.
- **Surface energy of common substrates**: 28 plastics, rubbers, coatings, metals and glass in dyn/cm, with surface energy class and bonding notes.

Plain CSV and JSON, so the data can be used in spreadsheets, scripts or datasheet tools.

The same data powers two free web tools:

- [Tape spec unit converter](https://alstape.com/tools/tape-unit-converter)
- [Surface energy chart and tape adhesive selector](https://alstape.com/tools/surface-energy-chart)

## Files

| File | Contents |
|---|---|
| [`data/tape-unit-factors.csv`](data/tape-unit-factors.csv) / [`.json`](data/tape-unit-factors.json) | Units per quantity and the factor to the base unit |
| [`data/surface-energy.csv`](data/surface-energy.csv) / [`.json`](data/surface-energy.json) | Material, group, min and max surface energy (dyn/cm), class, note |

## Tape spec units

Each row gives `to_base`: multiply a value in that unit by `to_base` to get the base unit, then divide by the target unit's `to_base`.

Example: 40 oz/in in N/25 mm = 40 × 10.9454272 ÷ 40 = **10.95 N/25 mm**.

Common peel adhesion equivalents:

| N/25 mm | N/cm | oz/in | lb/in |
|---|---|---|---|
| 1 | 0.4 | 3.65 | 0.228 |
| 5 | 2 | 18.3 | 1.14 |
| 10 | 4 | 36.5 | 2.28 |
| 20 | 8 | 73.1 | 4.57 |

Exact definitions used: 1 in = 25.4 mm; 1 lbf = 4.4482216152605 N; 1 ozf = 1/16 lbf; 1 kgf = 9.80665 N; 1 lb = 453.59237 g; 1 oz = 28.349523125 g; 1 ft = 0.3048 m. Temperature: °F = °C × 9/5 + 32.

A converted number is only comparable if the test is too: peel values also depend on the test method (ASTM D3330, PSTC-101, ISO 29862), peel angle, dwell time, test substrate and backing.

## Surface energy

Values are in dyn/cm (1 dyn/cm = 1 mN/m = 1 mJ/m²). Where two published tables list the same material, `min_dyn_cm` and `max_dyn_cm` span both; blank values mean no single number is published (class only).

Classes follow 3M's grouping: low surface energy (LSE) below about 36 dyn/cm. tesa places the boundary at 36–38 mN/m, so that band is marked borderline.

| Class | Range | Typical starting adhesive |
|---|---|---|
| Very low | about 18–21 dyn/cm (PTFE, silicone) | Silicone PSA |
| Low (LSE) | below 36 dyn/cm (PP, PE, TPO, EVA) | LSE acrylic or synthetic rubber, or treat the surface |
| Borderline | about 34–38 dyn/cm (PS, POM, PMMA) | Test standard vs LSE acrylic |
| Medium (MSE) | about 38–50 dyn/cm (ABS, PC, PET, nylon) | Standard acrylic |
| High (HSE) | hundreds of dyn/cm (metals, glass) | Standard acrylic |

These are typical values for choosing a starting point. Grade, fillers, mould release and plasticizers change the real surface; check production parts with dyne pens (ASTM D2578) and confirm with a peel test.

### Sources

- 3M, *Categorizing Surface Energy* (Science of Adhesion): https://www.3m.com/3M/en_US/bonding-and-assembly-us/resources/science-of-adhesion/categorizing-surface-energy/
- 3M Bonding Solutions catalogue, surface energy chart: https://www.3m.com.au/intl/au/Catalogue/IATD_BondingSolutions/files/assets/basic-html/page30.html
- Accu Dyne Test, critical surface tension of polymers: https://www.accudynetest.com/polytable_03_print.html?sortby=cst
- tesa, LSE converter assortment (36–38 mN/m boundary): https://www.tesa.com/en/files/download/10894056,0,tesa-lse-surfacetension-converterassortment-2022.pdf
- Saint-Gobain Tape Solutions, acrylic vs rubber vs silicone adhesive: https://www.tapesolutions.saint-gobain.com/en-gb/resources/blog/acrylic-rubber-or-silicone-adhesive

## License

Data compilation and notes: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Use it freely, with attribution to "ALS Tape (alstape.com)". Measured values belong to the sources above; cite them when you republish the numbers.

Corrections are welcome: open an issue with the value, the source and the page.

## About

Maintained by [ALS Tape](https://alstape.com), Xiamen, China: custom die-cut tape parts, gaskets and films from 3M, tesa, Nitto and other brands, converted at partner facilities.
