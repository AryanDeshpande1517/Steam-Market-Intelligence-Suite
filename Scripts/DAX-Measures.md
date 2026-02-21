# 📊 DAX Measures Documentation

This document outlines the key DAX measures and calculated columns implemented in **Steam Market Intelligence Suite**.

The measures are grouped into:

- Core Marketplace Metrics  
- Platform Segmentation  
- Game Classification Logic  
- Display & Formatting Logic  

All calculations were implemented inside Power BI using DAX.

# 🎮 Core Marketplace Metrics

## Total Games

Counts total number of games in the dataset.

```DAX
Total Games =
COUNTROWS('games_march2025_cleaned')
```

## Total Reviews

Aggregates total review volume across all games.

```DAX
Total Reviews =
SUM('games_march2025_cleaned'[num_reviews_total])
```

## Avg Price

Calculates the average listed price of games.

```DAX
Avg Price =
AVERAGE('games_march2025_cleaned'[price])
```

# 🖥 Platform Segmentation

## Windows Games

Counts games that support Windows.

```DAX
Windows Games =
CALCULATE(
    [Total Games],
    'games_march2025_cleaned'[windows] = TRUE
)
```

## Mac Games

Counts games that support macOS.

```DAX
Mac Games =
CALCULATE(
    [Total Games],
    'games_march2025_cleaned'[mac] = TRUE
)
```

## Linux Games

Counts games that support Linux.

```DAX
Linux Games =
CALCULATE(
    [Total Games],
    'games_march2025_cleaned'[linux] = TRUE
)
```

# 🎯 Game Classification Logic

## Game Type

Classifies games as Free-to-Play or Premium based on price.

```DAX
Game Type =
IF(
    'games_march2025_cleaned'[price] = 0,
    "Free to Play",
    "Premium"
)
```

## Age Rating

Categorizes age requirement into display-friendly format.

```DAX
Age Rating =
IF(
    MAX('games_march2025_cleaned'[required_age]) = 0,
    "E",
    MAX('games_march2025_cleaned'[required_age]) & "+"
)
```

# 🖥 Display & Formatting Logic

## Supported Platforms

Creates a readable platform label for storefront display.

```DAX
Supported Platforms =
IF('games_march2025_cleaned'[windows] = TRUE, "Windows ", "") &
IF('games_march2025_cleaned'[mac] = TRUE, "macOS ", "") &
IF('games_march2025_cleaned'[linux] = TRUE, "Linux ", "")
```

# 📊 Modeling Notes

The data model follows a Star Schema design.

### Fact Table
- Games Dataset (pricing, reviews, platform support, metrics)

### Dimension Attributes
- Genre  
- Developer  
- Publisher  
- Platform  
- Release Year  
- Game Type  

The DAX layer enables:

- Platform distribution analysis  
- Pricing segmentation  
- Genre economics analysis  
- Developer benchmarking  
- Sentiment-driven performance insights  

# 📝 Summary

The DAX layer powers:

- Marketplace aggregation  
- Platform intelligence  
- Game classification  
- Interactive storefront analysis  
- Strategic gaming market insights  

This completes the analytical modeling layer of the Steam Market Intelligence Suite.