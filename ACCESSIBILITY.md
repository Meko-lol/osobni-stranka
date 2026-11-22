# Zpráva o přístupnosti

## Výsledky nástrojů

| Nástroj | Před opravami | Po opravách |
| --- | --- | --- |
| Lighthouse (Accessibility) | 100 | 100 |
| WAVE (Errors a Contrast Errors) | neměřeno (pouštěl jsem ho až po opravách) | 0 a 0, Alerts 0, AIM score 10/10 |
| Test klávesnicí | všechno jde ovládat, fokus je vidět | stejné |

## Nalezené problémy a jejich opravy

| Problém | Jak jsem ho našel | Oprava (commit) | Kritérium WCAG |
| --- | --- | --- | --- |
| Odkazy měly po vyřešení konfliktu barvu `#d5896f` s kontrastem jen 2,41 : 1 | výpočet kontrastu | `a890c1c` | 1.4.3 |
| S většími rozestupy textu tabulka na 320 px přetekla a objevil se vodorovný posuvník | přepsání line-height, letter-spacing a word-spacing | `2668fa6` | 1.4.12 |
| Okraje tlačítek v navigaci měly kontrast 1,3 : 1 (v tmavém režimu 1,8 : 1) | výpočet kontrastu | `c7376d2` | 1.4.11 |

## Test media rules

| Nastavení | Co jsem při emulaci viděl | V pořádku |
| --- | --- | --- |
| prefers-color-scheme: dark | tmavé pozadí, světlý text, tmavé posuvníky | ano |
| prefers-contrast: more | bílé pozadí bez přechodu, černý text, silnější okraje, podtržené odkazy | ano |
| prefers-color-scheme: dark + prefers-contrast: more | černé pozadí, bílý text, žluté odkazy | ano |
| prefers-reduced-motion: reduce | karty se neanimují, odkaz změní barvu hned, rolování skočí | ano |
| prefers-reduced-transparency: reduce | karty a navigace mají plnou barvu, žádné rozostření | ano |
| forced-colors: active | okraje karet a navigace i fokus jsou vidět | ano |

## Kritéria WCAG 2.2 úrovně A a AA

Specifikace: https://www.w3.org/TR/WCAG22/ (kritérium najdete podle čísla).
Úrovně A a AA mají dohromady 55 kritérií (31 úrovně A a 24 úrovně AA). Kritérium
4.1.1 Parsing bylo ve verzi 2.2 odstraněno, proto v tabulce není.

Kritéria označená „nové“ přibyla ve verzi 2.2.

### 1 Perceivable (vnímatelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 1.1.1 | Non-text Content | A | Splněno | obrázky projektů mají výstižný alt |
| 1.2.1 | Audio-only and Video-only (Prerecorded) | A | Nevztahuje se | na stránce není audio ani video |
| 1.2.2 | Captions (Prerecorded) | A | Nevztahuje se | na stránce není video |
| 1.2.3 | Audio Description or Media Alternative (Prerecorded) | A | Nevztahuje se | na stránce není video |
| 1.2.4 | Captions (Live) | AA | Nevztahuje se | na stránce není živý přenos |
| 1.2.5 | Audio Description (Prerecorded) | AA | Nevztahuje se | na stránce není video |
| 1.3.1 | Info and Relationships | A | Splněno | header, nav, main, footer, nadpisy h1–h3, seznamy, tabulka s caption a th se scope |
| 1.3.2 | Meaningful Sequence | A | Splněno | pořadí v HTML odpovídá pořadí čtení |
| 1.3.3 | Sensory Characteristics | A | Splněno | žádný pokyn se neodkazuje na tvar, barvu ani polohu |
| 1.3.4 | Orientation | AA | Splněno | stránka funguje na výšku i na šířku |
| 1.3.5 | Identify Input Purpose | AA | Nevztahuje se | na stránce není formulář |
| 1.4.1 | Use of Color | A | Splněno | odkazy v textu jsou podtržené, nic se nepozná jen podle barvy |
| 1.4.2 | Audio Control | A | Nevztahuje se | na stránce není zvuk |
| 1.4.3 | Contrast (Minimum) | AA | Splněno | text má aspoň 4,5 : 1 v obou schématech (nejhůř 5,2 : 1) |
| 1.4.4 | Resize Text | AA | Splněno | velikosti v rem, při 200 % se nic neztratí |
| 1.4.5 | Images of Text | AA | Splněno | žádné obrázky textu, ilustrace jsou bez textu |
| 1.4.10 | Reflow | AA | Splněno | na 320 px a při 400 % bez vodorovného posuvníku |
| 1.4.11 | Non-text Contrast | AA | Splněno | okraje tlačítek navigace aspoň 3,8 : 1, fokus aspoň 5,9 : 1 |
| 1.4.12 | Text Spacing | AA | Splněno | s většími rozestupy textu se nic neztratí ani nepřekrývá |
| 1.4.13 | Content on Hover or Focus | AA | Splněno | při najetí ani zaostření se neobjevuje žádný obsah, jen skip link, který zůstane vidět, dokud má fokus |

### 2 Operable (ovladatelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 2.1.1 | Keyboard | A | Splněno | všechny odkazy jdou ovládat klávesnicí |
| 2.1.2 | No Keyboard Trap | A | Splněno | Tab i Shift+Tab projdou celou stránku, nikde se neuvízne |
| 2.1.4 | Character Key Shortcuts | A | Nevztahuje se | stránka nemá klávesové zkratky |
| 2.2.1 | Timing Adjustable | A | Nevztahuje se | žádné časové limity |
| 2.2.2 | Pause, Stop, Hide | A | Splněno | animace karet trvá 0,6 s a sama skončí |
| 2.3.1 | Three Flashes or Below Threshold | A | Splněno | nic nebliká |
| 2.4.1 | Bypass Blocks | A | Splněno | skip link „Přejít na obsah“ skočí na main |
| 2.4.2 | Page Titled | A | Splněno | titulek „Jan Petrák – osobní stránka“ |
| 2.4.3 | Focus Order | A | Splněno | fokus jde skip link, navigace, projekty, kontakt |
| 2.4.4 | Link Purpose (In Context) | A | Splněno | odkazy říkají, kam vedou, např. „Zdrojový kód hry Prisoner of the Depths na GitHubu“ |
| 2.4.5 | Multiple Ways | AA | Nevztahuje se | web má jen jednu stránku |
| 2.4.6 | Headings and Labels | AA | Splněno | nadpisy popisují obsah sekcí |
| 2.4.7 | Focus Visible | AA | Splněno | :focus-visible s outline 3 px |
| 2.4.11 | Focus Not Obscured (Minimum) (nové) | AA | Splněno | na stránce není žádný pevně ukotvený prvek, fokus nic nezakryje |
| 2.5.1 | Pointer Gestures | A | Nevztahuje se | nic se neovládá gesty |
| 2.5.2 | Pointer Cancellation | A | Splněno | jen obyčejné odkazy, aktivují se až při puštění tlačítka |
| 2.5.3 | Label in Name | A | Splněno | viditelný text odkazů je i jejich název |
| 2.5.4 | Motion Actuation | A | Nevztahuje se | nic se neovládá pohybem zařízení |
| 2.5.7 | Dragging Movements (nové) | AA | Nevztahuje se | nic se netáhne |
| 2.5.8 | Target Size (Minimum) (nové) | AA | Splněno | odkazy mají aspoň 24 × 24 px (navigace 44 px na výšku, ostatní 34 px) |

### 3 Understandable (srozumitelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 3.1.1 | Language of Page | A | Splněno | <html lang="cs"> |
| 3.1.2 | Language of Parts | AA | Splněno | anglické názvy projektů mají lang="en" |
| 3.2.1 | On Focus | A | Splněno | zaostření nic nezmění |
| 3.2.2 | On Input | A | Nevztahuje se | na stránce nejsou formulářové prvky |
| 3.2.3 | Consistent Navigation | AA | Nevztahuje se | web má jen jednu stránku |
| 3.2.4 | Consistent Identification | AA | Nevztahuje se | web má jen jednu stránku |
| 3.2.6 | Consistent Help (nové) | A | Nevztahuje se | web má jen jednu stránku a žádnou nápovědu |
| 3.3.1 | Error Identification | A | Nevztahuje se | na stránce není formulář |
| 3.3.2 | Labels or Instructions | A | Nevztahuje se | na stránce není formulář |
| 3.3.3 | Error Suggestion | AA | Nevztahuje se | na stránce není formulář |
| 3.3.4 | Error Prevention (Legal, Financial, Data) | AA | Nevztahuje se | na stránce není formulář |
| 3.3.7 | Redundant Entry (nové) | A | Nevztahuje se | nic se nezadává |
| 3.3.8 | Accessible Authentication (Minimum) (nové) | AA | Nevztahuje se | na stránce není přihlašování |

### 4 Robust (robustnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 4.1.2 | Name, Role, Value | A | Splněno | jen nativní odkazy a sémantické prvky, žádné vlastní ovládací prvky |
| 4.1.3 | Status Messages | AA | Nevztahuje se | na stránce se nic nemění samo, žádné stavové zprávy |
