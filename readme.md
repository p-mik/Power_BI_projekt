<h1>Průvodní list k projektu</h1>
<h2>Zdroje dat:</h2>
<ul>
    <li>otazka1.csv - Vizuál 2</li>
    <li>otazka2.csv - Vizuál 3</li>
    <li>otazka3_1.csv - Nakonec nepoužito</li>
    <li>otazka3_3.csv - Vizuál 5</li>
    <li>otazka4.csv - Vizuál 4</li>
    <li>t_petr_mikulka_project_sql_primary_final.csv - Nakonec nepoužito</li>
    <li>t_petr_mikulka_project_sql_secondary_final.csv - Vizuál 1</li>
</ul>

<h2>Poznámka ke zdroji dat:</h2>
<p>
        Při započetí práce s daty jsem zjistil, že číselné hodnoty se načetly jako string a místo desetinné čárky využívají tečku.
        Ačkoliv jsem toto měl zřejmě „podchytit“ při přípravě dat, vrozhodl jsem se upravit data v PowerQuery – tečky jsem v daných
        sloupcích nahradil čárkou a převedl stringy na čísla. (POZN: bez nahrazení tečky čárkou převedení na číslo nefungovalo)
</p>

<h2>Popis vizuálů:</h2>

<h3>Vizuál 1 – Srovnání HDP na obyvatele</h3>
<p>Cílem je využít vizuál „Kartogram“ a na něm zvýraznit jednou barvou země, které mají vyšší HDP než ČR a jinou barvou země, které mají nižší HDP než ČR.</p>
<h4>Příprava Sloupců:</h4>
<ul>
    <li>Přidal jsem počítaný sloupec „GDP_per_Capita“, který vyjadřuje HDP na obyvatele.</li>
    <li>Přidal jsem počítaný sloupec „GDP_Capita_Comparison“, ve kterém jsem vytvořil 3 kategorie: Země s vyšším HDP než ČR, Země s nižším HDP než ČR, ČR.</li>
</ul>
<h4>Přidání sliceru:</h4>
<p>Pro ozvláštnění jsem přidal slicer pro filtrování jednotlivých roků. Bohužel, HDP na obyvatele není příliš dynamický parametr, takže při přepínání dlaždic není, krom roků 2012 a 2018, na mapě vidět žádná změna.</p>
<h4>Možné issue:</h4>
<p>Pro lepší vizuální dojem jsem dal slicer přes mapu. Přes to, že jsem nastavil, aby mapa byla v pozadí a slicer v popředí, slicer občas záhadně mizí.</p>

<h3>Vizuál 2 – Průměrná mzda v odvětví</h3>
<p>Cílem je vizualizovat odpověď na výzkumnou otázku č. 1 z SQL projektu akademie.</p>
<h4>Výzkumná otázka:</h4>
<p>„Rostou v průběhu let mzdy ve všech odvětvích, nebo v některých klesají?“</p>
<h4>Odpověď:</h4>
<p>Z vizualizace je patrné, že k meziročnímu poklesu mezd docházelo ve sledovaném období u všech odvětví.</p>
<h4>Poznámka k řešení:</h4>
<p>Pro pohyb hodnoty v čase se mi zdál vhodný Spojnicový graf. Opět jsem vytvořil slicer, který pomáhá zaměřit se na jednotlivé odvětví.</p>

<h3>Vizuál 3 – Dostupnost mléka a chleba</h3>
<p>Cílem je vizualizovat odpověď na výzkumnou otázku č. 2 z SQL projektu akademie.</p>
<h4>Výzkumná otázka:</h4>
<p>„Kolik je možné si koupit litrů mléka a kilogramů chleba za první a poslední srovnatelné období v dostupných datech cen a mezd?“</p>
<h4>Odpověď:</h4>
<ul>
    <li>V roce 2006 bylo možné za průměrnou mzdu pořídit 1176 kg chleba a 1313 l mléka.</li>
    <li>V roce 2018 bylo možné za průměrnou mzdu pořídit 1233 kg chleba a 1508 l mléka.</li>
</ul>
<h4>Poznámka k řešení:</h4>
<p>I přes to, že mám data pouze za roky 2006 a 2018, měl graf tendenci mi vykreslovat i další roky v tomto rozsahu. To jsem odstranil tím, že jsem pro roky 2006 a 2018 vytvořil skupiny.</p>

<h3>Vizuál 4 – Rozdíl v růstu mezd a cen</h3>
<p>Cílem je vizualizovat odpověď na výzkumnou otázku č. 4 z SQL projektu akademie.</p>
<h4>Výzkumná otázka:</h4>
<p>Existuje rok, ve kterém byl meziroční nárůst cen potravin výrazně vyšší než růst mezd (větší než 10 %)?</p>
<h4>Odpověď:</h4>
<p>Ano, roky, kdy rozdíl mezi růstem cen a růstem mezd byl vyšší než 10 % byly hned dva: 2013 a 2017.</p>
<h4>Poznámka k řešení:</h4>
<p>Pro hranici 10 %, která pomáhá vizuálně určit stěžejní data, jsem vytvořil nový sloupec. Měl jsem problém s tím, že se mi nedařilo mít na ose X zobrazené všechny roky (zobrazovaly se pouze sudé roky). Vyřešil jsem to změnou typu osy X na kategorie a následným seřazením osy.</p>

<h3>Vizuál 5 – Která potravina v daném roce zdražila nejméně</h3>
<p>Cílem je vizualizovat odpověď na výzkumnou otázku č. 3 z SQL projektu akademie.</p>
<h4>Výzkumná otázka:</h4>
<p>„Která kategorie potravin zdražuje nejpomaleji (je u ní nejnižší percentuální meziroční nárůst)?“</p>
<h4>Odpověď:</h4>
<p>V tabulce je za každý rok uvedena potravina, která v daný rok zdražila nejméně, resp. nejvíce zlevnila.</p>
<h4>Poznámka k řešení:</h4>
<p>Zvolil jsem zobrazení pomocí tabulky, neboť to je také forma vizuálu a pro tento případ pravděpodobně ta nejpřehlednější.</p>

