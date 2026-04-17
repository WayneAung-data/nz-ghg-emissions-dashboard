# NZ GHG Emissions Dashboard
This is an ongoing project analysing sector-level greenhouse gas emissions in New Zealand using Stats NZ data from 2010 to 2025.

## Project Overview
The project focuses on:
- building an interactive dashboard in Power BI to identify sectoral and regional patterns in greenhouse gas (GHG) emissions 
- transforming and cleaning GHG data using Power Query
- calculating year-on-year changes using DAX

## Current Scope
The current version includes:
- initial dashboard structure
- sector-level trend visualisation
- summary indicators for emissions levels and annual changes

## Planned Extensions
Future development will include:
- stronger sector- and regional-level analytical storytelling
- improved dashboard styling and usability
- further interpretation of structural emissions dynamics across sectors and regions

## Repository Structure
- `screenshots/` – progress + schema + visuals 
- `final-dashboard/` – final Power BI file later

# Data Cleaning and Modelling
## Data Sources
- GHG emissions by sector (quarterly, national) (Statistics New Zealand)
- GHG emissions by region and sector (annual) (Statistics New Zealand)

## Data Cleaning
- Standardised and trimmed text fields 
- Removed suppression codes and treated as nulls
- Filtering “Carbon dioxide equivalents” and “Actual” values
- Removed unnecessary metadata columns

## Data Structuring
- Resolved inconsistencies in ANZSIC sector hierarchy
- Selected 7 core sectors for consistency and interpretability
- Removed overlapping and aggregate categories to avoid double counting
- Converted quarterly data into yearly aggregates to align datasets
- Retained full time range (2007–2025) for flexibility

## Data Modelling
- Created two fact tables:
  - fact_ghg_sector_yearly (Year–Sector)
  - fact_ghg_region (Year–Region–Sector)
- Built dimension tables (Sector, Year, Region)
- Implemented a multi-fact star schema
- Established one-to-many relationships with single-direction filtering

## Design Decisions
- Prioritised consistency over maximum granularity
- Maintained structural clarity for DAX and dashboarding
- Preserved missing values instead of imputing to avoid bias

## Data Source
- Greenhouse gas emissions (industry and household): March 2010–December 2025 quarters
- Greenhouse gas emissions by region (industry and household): Year ended 2024

## Tools Used
- Power BI
- Power Query
- DAX

