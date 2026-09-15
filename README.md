# projekt_powerbi_dat_acad_2026_slama_jan
Project for the ENGETO Data Academy by Jan Sláma
Superstore Sales Performance Dashboard
Power BI projekt vytvořený v rámci Datové akademie nad datasetem Superstore.
Cílem projektu bylo vytvořit přehledný a interaktivní report, který umožní rychle vyhodnotit celkové obchodní výsledky a zároveň se podívat detailněji na výkonnost jednotlivých produktových kategorií a produktů.

Náhled reportu

Executive Overview
První stránka slouží jako rychlý manažerský přehled. Obsahuje hlavní KPI, vývoj tržeb v čase, porovnání kategorií a rozdělení tržeb podle regionů.

Product & Profitability Analysis
Druhá stránka je zaměřená na detailnější pohled na produktové portfolio, tržby a ziskovost. Součástí je také hierarchie, kterou lze rozbalovat až na úroveň konkrétního produktu.

Co report obsahuje

Executive Overview

Na první stránce jsou zobrazeny hlavní ukazatele:

Total Sales

Total Profit

Total Orders

Profit Margin %

Dále jsou zde použity:

Line chart – vývoj tržeb v čase

Column chart – tržby podle produktové kategorie

Donut chart – tržby podle regionu

Slicery pro Year, Region, Segment a Category

Product & Profitability Analysis

Druhá stránka obsahuje:

Treemap – Sales by Category and Sub-Category

Bar chart – Top 10 Products by Sales

Matrix – Sales, Profit a Profit Margin podle produktové hierarchie

Slicery pro Year, Region, Segment a Category

Slicery jsou mezi stránkami synchronizované, takže vybraný filtr zůstává aktivní i při přechodu na jinou stránku.

Datový model

Report používá jednoduchý hvězdicový model složený ze čtyř tabulek:

Fact_Orders

Dim_Customers

Dim_Date

Dim_Products

Aktivní vazby:

Fact_Orders[Customer ID] → Dim_Customers[Customer ID]

Fact_Orders[Order Date] → Dim_Date[Date]

Fact_Orders[Product ID] → Dim_Products[Product ID]

Toto rozdělení umožňuje filtrovat data podle zákazníků, času i produktů bez nutnosti držet vše v jedné tabulce.

DAX measures

V reportu jsou použity vlastní DAX measures.

Total Sales

Total Sales = SUM(Fact_Orders[Sales])

Total Profit

Total Profit = SUM(Fact_Orders[Profit])

Total Orders

Total Orders = DISTINCTCOUNT(Fact_Orders[Order ID])

Profit Margin %

Profit Margin % = DIVIDE([Total Profit], [Total Sales])

Součástí modelu je také calculated column Delivery Days, která vyjadřuje dobu mezi vytvořením objednávky a jejím odesláním.

Produktová hierarchie

V tabulce Dim_Products byla vytvořena hierarchie:

Category
└── Sub-Category
    └── Product Name

Hierarchie je použita v Matrix vizuálu na stránce Product Analysis a umožňuje postupné rozbalování dat od celé kategorie až po konkrétní produkt.

Interaktivita

Report není pouze statický přehled. Obsahuje:

synchronizované slicery mezi stránkami,

cross-filtering mezi vizuály,

rozbalovací produktovou hierarchii,

Page Navigator pro přechod mezi stránkami,

dynamický přepočet KPI a grafů podle vybraných filtrů.

Použité typy vizuálů

V projektu je použito více než požadovaných pět různých typů vizuálů:

KPI Cards

Line Chart

Column Chart

Donut Chart

Treemap

Bar Chart

Matrix

Slicers

Page Navigator

Splnění zadání

Požadavek

Řešení

2–5 stran reportu

2 stránky

Min. 5 různých typů vizuálů

Ano, použito 7+ typů

Filtrování pomocí slicerů

Ano

Interaktivní prvky

Page Navigator, cross-filtering

Propojení 2+ tabulek

4 propojené tabulky

Hierarchie alespoň o 2 úrovních

Category → Sub-Category → Product Name

Alespoň 1 measure

Ano, vytvořeno více measures

Calculated column / table

Delivery Days

Vizuální úprava reportu

Ano

Použité technologie

Microsoft Power BI Desktop
Power Query
DAX
Microsoft Excel
Git / GitHub

Poznámka

Projekt vznikl jako závěrečný Power BI projekt v rámci Datové akademie. Zaměřuje se především na praktické využití datového modelu, DAX metrik a interaktivních vizualizací v jednom přehledném reportu.
