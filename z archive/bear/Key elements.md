# Key elements
Here are the tables I would want. I’m interested in you challenging the ideas here. But I think I feel strongly about them. 

Product
-ID
-Product identifiers
-Maker
-Store
-Category 
-Variant kind

Product Variant
-ID
-Product Identifiers
-Variant identifiers (dummy if none)
-Material
-Color
-Size
-Description 

Product Variant Paths
-ID
-Product Identifiers
-Path
-Scrape Data

Product Abstract Paths
-ID
-Product Identifiers
-Path
-Scrape Data

GS IDs
-ID
-Valid?
-Offers

Offers
-ID 
-GS ID
-Timestamp
-Product identifiers
-Variant identifiers 

Product Variant Matching
-Product Variant ID 1
-Product Variant ID 2
-Method: Google shopping, Query path, manual, lens

It does make sense to me, if our key strategic advantages is data, that we would need to “own” this down to the tables. 

Some key elements missing from our current structure:
-All Products become variants -> I think we match variants through logic today. Forcing all products to be variants, seems dominant to me, on intuition (all products deserve to be seen), and other reasons, ie right variant in search.
-Product Variant matching table -> solve variant logic issue, setup for manual + lens matching 
-Kind of variation in product -> sets up category specific filter experience
-Google offer time stamp -> better handle reconciliation
-Google shopping validity -> handle post ingestion manipulation w/o delete
-Flagging or separating QP / DP -> can play into use experience
-Naming identifiers, ie Product + Variant identifiers, type (path, MPN) -> clarifies and can advance future matching
-As much data as possible should exist in these tables. Having data “siloed” ie on our machines vs in our tables seems bad. 
