# Redakční styl návodů Živé tabule

Tento dokument doplňuje [KONCEPCE.md](KONCEPCE.md). Při rozporu má přednost KONCEPCE.md.

## Jednotná struktura
- Jeden nástroj = jedna stránka v `src/pages/<nazev>.md`, s frontmatter `title`, `description`, `order`, `layout: ../layouts/TipLayout.astro`.
- Nadpis nástroje, krátký praktický úvod a odkaz/tlačítko **Otevřít Živou tabuli**.
- **Jak na to** – stručný a ověřený postup.
- **Inspirace do výuky** – konkrétní nápady, každý s nadpisem H3; případně poznámka `> **Proč to funguje?** ...` nebo `> **Na co si dát pozor?** ...`.
- Volitelně vysvětlení návrhového rozhodnutí.
- **💡 Tip na začátek** může být součástí návodu, pokud je vhodný; na úvodní stránce se tipy mohou střídat.

## Styl
- Emoji nepoužívat v názvech nástrojů ani u jednotlivých příkladů. Výjimka: **💡 Tip na začátek**.
- Stručný, přátelský a konkrétní jazyk; nejdřív použití ve výuce, pak didaktické souvislosti.
- Zachovat stejné názvy základních sekcí ve všech návodech.
- Nevymýšlet ovládací prvky nebo neověřené funkce; podle potřeby ověřit aktuální aplikaci.
- Nápady přehledně oddělovat; pedagogické poznámky psát jako standardní Markdown blockquote.
- Bez opakovaných reklamních sloganů; společnou patičku spravuje šablona.
