# Osobní stránka

Moje osobní stránka do WA (úloha Přístupnost). Je na ní něco o mně, projekty, dovednosti a kontakt.
Stránka splňuje WCAG 2.2 AA a přizpůsobí se tomu, co má člověk nastavené v systému.

Stránka: https://meko-lol.github.io/osobni-stranka/

Zpráva o přístupnosti je v [ACCESSIBILITY.md](ACCESSIBILITY.md).

## Media rules

| Pravidlo | Co se mění a proč |
| --- | --- |
| `min-width` (40em, 60em, 80em) | Na mobilu je navigace 2×2 a projekty pod sebou, na větším displeji jsou vedle sebe, aby nikde nebyl vodorovný posuvník. |
| `prefers-color-scheme: dark` | Tmavé barvy i posuvníky (`color-scheme`), aby stránka v tmavém režimu neoslňovala. |
| `prefers-contrast: more` | Kontrast aspoň 7 : 1, bez přechodu v pozadí, silnější okraje a podtržené odkazy, aby se to líp četlo. |
| `prefers-reduced-motion: reduce` | Vypne animaci karet, přechod odkazů a plynulé rolování, protože pohyb může někomu dělat špatně. |
| `prefers-reduced-transparency: reduce` | Karty mají plnou barvu bez rozostření, protože průhledné pozadí se hůř čte. |
| `forced-colors: active` | Okraje a fokus v systémových barvách, protože stíny v tomhle režimu zmizí. |
| `dark` and `prefers-contrast: more` | Černé pozadí, bílý text a žluté odkazy, jinak by vyšší kontrast v tmavém režimu udělal bílou stránku. |
