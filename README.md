# Data Cleaning Project

---

## Table of Contents

- [Overview](#overview)
- ~[Project Structure](#project-structure)~
- ~[Contributing](#contributing)~
- ~[License](#license)~
- ~[Acknowledgments](#acknowledgments)~

---

## 1. Dataset Description
 
### 1.1 Origin and Background
 
The NYPL "What's on the Menu?" dataset originates from the New York Public Library's crowdsourced digitization project, launched in 2011. Volunteers transcribed text from scanned historical restaurant menus held in the Library's collection. The dataset captures over a century of American dining culture and culinary history, with menus spanning from the 1840s through the early 2000s. Because the data was produced through manual transcription of physical documents — many of which were handwritten, printed in ornate typefaces, or damaged with age — the dataset contains a wide range of data quality issues characteristic of crowdsourced, OCR-assisted digitization projects.
 
The dataset comprises four interrelated CSV files representing a relational model of menus, their physical pages, the dishes offered, and individual menu item entries. The combined dataset totals approximately 1.84 million rows across all four tables.
 
### 1.2 Relational Schema
 
| Table | Rows | Key Columns | Description |
|---|---|---|---|
| Menu.csv | 17,547 | id, date, location, sponsor, event, status | Top-level menu records. Each row is one physical menu from a restaurant, hotel, steamship, or event. |
| MenuPage.csv | 66,937 | id, menu_id, page_number, image_id | Individual pages within each menu. Links menus to scanned page images. |
| Dish.csv | 423,400 | id, name, menus_appeared, first_appeared, last_appeared, lowest_price, highest_price | Unique dish records aggregated across all menus. One row per distinct dish. |
| MenuItem.csv | 1,332,726 | id, menu_page_id, dish_id, price, high_price | Junction table linking dishes to specific menu pages, with price data at each appearance. |

### 1.3 Entity-Relationship Overview
 
The logical relationships between tables follow a clear hierarchy:
 
- A **Menu** has one or more **MenuPages** (one-to-many).
- A **MenuPage** has one or more **MenuItems** (one-to-many).
- A **MenuItem** references exactly one **Dish** (many-to-one).
- A **Dish** aggregates statistics (price range, first/last appearance) across all its MenuItem records.

### 1.4 Temporal and Spatial Extent
 
Temporally, the menus span from approximately 1840 to the early 2000s, with the bulk of records concentrated between 1890 and 1960. Spatially, the collection is predominantly American (especially New York City), but includes menus from European steamship lines, international hotels, and overseas restaurants, reflected in the presence of currencies such as Deutsche Marks, Francs, Shillings, Yen, and others.
 
### 1.5 Metadata Notes
 
- The `name` column in Menu.csv is almost entirely null (14,348 of 17,547 rows), as menus are identified by their sponsor and location rather than a formal title.
- The `keywords` and `language` columns are null in virtually all rows (17,545 of 17,547), suggesting these fields were never populated.
- The `currency` and `currency_symbol` columns are null in 11,089 of 17,547 menu records, likely because most prices were recorded directly in MenuItem.csv without explicit currency annotation at the menu level.
- The `status` field indicates whether a menu has been fully transcribed (`complete`) or is still under review, with 17,371 complete and 174 under review.

## 2. Use Cases

### 2.1 Target Use Case ($U_1$): Cleaning is Necessary and Sufficient

To be updated

### 2.2 Zero Data Cleaning Use Case ($U_0$): Good Enough as Is

To be updated

### 2.3 Never Enough Use Case ($U_2$): Insufficient Even with Cleaning

To be updated

## 3. Data Quality Problems

### 3.1 Identified Data Quality Problems ($P$)

To be updated

### 3.2 Evidence & Dirty Data Snippets

To be updated

## 4. Initial Data Cleaning Plan

### 4.1 Workflow Steps ($S_1$ to $S_5$)

To be updated

### 4.2 Proposed Toolset

To be updated

### 4.3 Tentative Task Assignment & Timeline

To be updated
