# Koncepce projektu Tipy pro Živou tabuli

> **Živá tabule nabízí nástroje. Tipy pro Živou tabuli ukazují, jak s nimi dobře učit.**

Tento dokument je společným zdrojem pravdy pro obsah, podobu a rozvoj webu [tipy.zivatabule.cz](https://tipy.zivatabule.cz). Zachycuje vědomá rozhodnutí, aby se neztratila mezi jednotlivými konverzacemi. Aktualizujeme ho při podstatných změnách koncepce.

## Poslání a cílová skupina

Web není jen technická nápověda, ale především **sbírka konkrétních pedagogických nápadů**. Učitel sem přichází pro něco, co může vyzkoušet třeba už v příští hodině, a zároveň nenásilně poznává pedagogické souvislosti.

Důležitou cílovou skupinou jsou začínající učitelé. Texty však nesmějí působit začátečnicky ani na zkušené kolegy.

**Hlavní princip: Nejdřív praxe, potom souvislosti.**

## Obsahové zásady

- Konkrétnost před obecnými pedagogickými frázemi. Každý nápad má obsahovat použitelnou otázku, postup nebo příklad.
- Stručný, přátelský a srozumitelný jazyk. Bez zbytečné akademické terminologie.
- Didaktický princip vysvětlujeme krátce, přímo u příslušného nápadu, označením **Proč to funguje?**; ne jako dlouhou teoretickou přednášku.
- Pedagogická vysvětlení mají být věcná a přiměřená: nepřisuzovat nástroji účinky, které nejsou prokázané. Například samotné hlasování neprokazuje porozumění.
- Užitečné je upozornit také na omezení, rizika a situace, kdy nápad nemusí fungovat.
- Návody musejí odpovídat skutečnému rozhraní aplikace; funkce a ovládání neodhadujeme.
- Sbírka inspirací může na stránce postupně růst; není nutné ji omezovat na pevný počet nápadů.

## Struktura webu

**Jeden nástroj = jedna stránka = jeden snadno upravitelný Markdown soubor.**

Doporučené pořadí obsahu stránky:

1. Název nástroje a krátký popis jeho přínosu.
2. Výrazné tlačítko **Otevřít Živou tabuli** hned pod úvodem.
3. **Jak na to** – opravdu stručný návod.
4. **Inspirace do výuky** – hlavní přidaná hodnota. Jednotlivé nápady jsou vizuálně oddělené; kde je to užitečné, doplněné o krátké **Proč to funguje?**
5. Volitelná sekce **Proč jsme to udělali takhle** – vysvětlení konkrétního návrhového rozhodnutí, pokud má pedagogický význam.

Názvy volitelných sekcí lze přizpůsobit nástroji; u Hlasování například **Proč právě Ano, Ne a Napůl?**

Úvodní stránka obsahuje krátký konkrétní tip na začátek a automatický katalog nástrojů, generovaný z Markdown souborů. Nový nástroj nemá vyžadovat ruční editaci seznamu.

## Vzorová stránka: Hlasování

Referenční stránka: `src/pages/hlasovani.md`.

Hlasování má záměrně pevné možnosti **Ano / Ne / Napůl**. Nejde o nedodělané nastavení, ale o rozhodnutí podporující jednoduchost a rychlé použití. **Napůl** může vyjádřit částečný souhlas či nejistotu; nejde o povinnost hádat, když žák neví.

Praktické inspirace: rychlá zpětná vazba, stejná otázka před výkladem a po něm, úvodní diskuse, orientační rozhodování třídy. Didaktické souvislosti vysvětlovat nenásilně u konkrétních nápadů.

## Vizuální styl a použitelnost

- Příbuznost se Živou tabulí: tmavě zelené a petrolejové akcenty, jemná zaoblení.
- **Světlé, lehce zelenošedé pozadí** pro pohodlné čtení, bílé karty, výrazný kontrast textu a odkazů.
- Úvodní katalog a delší stránky mohou mít rozdílné rozvržení, ale společnou vizuální identitu.
- Pedagogické nápady přehledně oddělovat; vysvětlení **Proč to funguje?** vizuálně zvýraznit střídmě.
- Nadpisy H2 a H3 jasně odlišovat: H2 výraznější s krátkou petrolejovou linkou, H3 menší; mezi jednotlivými nápady používat jemné oddělovací čáry.
- Používat jednotné decentní informační boxy pro **Proč to funguje?** a **Na co si dát pozor?**. Druhý typ upozorňuje na pedagogická omezení či rizika a nahrazuje samostatnou poznámku kurzívou.
- **Oba typy boxů zapisovat jednotně jako standardní Markdown blockquote**: řádek začíná znakem `>` a tučným označením, např. `> **Proč to funguje?** ...` nebo `> **Na co si dát pozor?** ...`. Vzhled určuje společné CSS pro `blockquote`, nikoli pozice odstavce. Technicky jde o citaci použitou jako poznámkový box; při případném přechodu na sémantické komponenty zachovat jednoduchost editace.
- Jednoduchost, čitelnost a přístupnost jsou důležitější než efektní grafika.
- Screenshoty používat jen tehdy, když skutečně pomohou.

## Propojení s blogem

- Blog Živé tabule vysvětluje souvislosti a důvody našich rozhodnutí, katalog tipů ukazuje konkrétní využití při výuce.
- Pokud existuje přímo související blogový článek, na konci příslušného tipu může být nenápadná sekce **Přečtěte si také**. Odkazování funguje i opačným směrem.
- Úvodní stránka nabízí vedle katalogu jednu stručnou konkrétní inspiraci; zatím bez kategorií, filtrů a složitějších funkcí.

## Technické řešení

- Zdrojový repozitář: [vmanena/zivatabule-tipy](https://github.com/vmanena/zivatabule-tipy).
- Statický web postavený na **Astro**.
- Obsah primárně v **Markdownu**, upravitelný přímo na GitHubu.
- Zápatí s výzvou k finanční podpoře a zpětné vazbě je společná komponenta `src/components/Footer.astro`, použitá na úvodní stránce i v šabloně článků. Text a odkazy se spravují na jediném místě; zpětná vazba odkazuje na hlavní Živou tabuli, kde je dostupná příslušná funkce.
- Hosting a automatické publikování přes **Cloudflare Pages**, produkční větev `main`.
- Veřejná adresa: [tipy.zivatabule.cz](https://tipy.zivatabule.cz).
- Bez databáze, přihlašování a zbytečné složitosti.
- Možnost pozdějšího rozšíření o Starlight není závazkem ani důvodem komplikovat současné řešení.

## Zásady společného vývoje

- Rozhodnutí vznikají postupným dialogem: nejdřív ujasnit smysl, potom řešení.
- Nepřidávat funkce ani složitost bez jasného užitku pro učitele.
- Při změně rozhraní či obsahu ověřit dopad na skutečné používání.
- Po důležitém rozhodnutí aktualizovat tento soubor.
- Tento dokument popisuje **dohodnutou koncepci**, nikoli neměnné dogma. Nové zkušenosti z výuky mohou vést k úpravám.

## Otevřené směry

- Postupně doplňovat stránky dalších nástrojů.
- U jednotlivých nápadů hledat konkrétní příklady napříč předměty.
- Případné obrázky, vyhledávání nebo složitější dokumentační systém přidávat až při prokázané potřebě.
