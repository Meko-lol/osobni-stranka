# Osobní stránka

Osobní stránka Jana Petráka, úloha Přístupnost z předmětu WA.

## Media rules

| Pravidlo | Co se mění a proč |
| --- | --- |
| `min-width` (šířka okna) | Tři zlomy (40em, 60em, 80em): navigace se z mřížky 2×2 přeskupí do řádku a projekty z jednoho sloupce do dvou a tří, aby stránka fungovala od nejmenšího telefonu po široký monitor bez vodorovného posuvníku. |
| `prefers-color-scheme: dark` | Proměnné v `:root` dostanou tmavé hodnoty a `color-scheme` (v CSS i `<meta>`) přepne i posuvníky a formulářové prvky, aby stránka neoslňovala lidi, kteří mají v systému tmavý režim. |
| `prefers-contrast: more` | Text má kontrast aspoň 7 : 1 (WCAG AAA), pozadí je plné bez přechodu, okraje jsou silnější a všechny odkazy podtržené, aby se stránka dobře četla lidem se slabším zrakem. |
| `prefers-reduced-motion: reduce` | Vypne animaci karet, přechod barvy odkazů a plynulé rolování, protože pohyb může lidem s poruchou vestibulárního systému způsobit závrať. |
| `prefers-reduced-transparency: reduce` | Poloprůhledné pozadí karet a navigace se nahradí plnou barvou a zmizí rozostření (`backdrop-filter`), protože průsvitné plochy zhoršují čitelnost a soustředění. |
| `forced-colors: active` | TODO |
| Kombinace `prefers-color-scheme: dark` and `prefers-contrast: more` | Černé pozadí, bílý text a žluté odkazy, protože samotné pravidlo pro vyšší kontrast by lidem s tmavým režimem vrátilo bílou stránku. |
