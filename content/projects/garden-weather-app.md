+++
date = '2025-11-15T11:43:32-05:00'
draft = false
title = 'Garden-weather App'
+++

I was sitting in my office on a cold winter night - after clearing snow - dreaming
of warm spring days in the sun, when I decided to act on a personal project I have
had in the back of my mind for a while now.

When snow and cold give way to tree buds swelling and sunshine, I'm always over-eager
to plant the garden in anticipation for that first tomato-sandwich of the season. 

The problem is, I live in the Northeast where false Spring plays its siren song for
seasonally-depressed gardeners every year. But THIS year, this year will be different...

At least my tracking will be different. In addition to more typical weather data you'll
find in your phone app, Open-Meteo also provides soil temperature readings which are handy.

If you're a gardener who can't be bothered to set out rain gauges, measure soil temperature,
or manually track precipitation patterns, but still want to have that data...I see you.

With help from my friend Opus in Claude Code, I settled on below for now.

### APIs used
- **Weather data**: [Open-Meteo](https://open-meteo.com) - Free, no API key needed
- **ZIP code geocoding**: [Zippopotam.us](https://zippopotam.us) - Free, no API key needed
- **Moon phase**: [US Naval Observatory](https://aa.usno.navy.mil/data/api) - Free, no API key needed

### Python Dependencies
- requests>=2.31.0
- duckdb>=0.9.0
- rich>=13.7.0

### Sample terminal output with data backed sent to a DuckDB file
```
+==============================================================================+
|                     Moon Phase & Weather Dashboard                           |
|                Home, NJ - Sunday, January 25, 2026                    |
+==============================================================================+

+------------------------------- MOON PHASE -----------------------------------+
| Phase: Waxing Crescent (23% illuminated)                                     |
| Moonrise: 10:45 AM  |  Moonset: 11:32 PM                                     |
| Next Full Moon: 8 days                                                       |
| Next New Moon: 22 days                                                       |
+------------------------------------------------------------------------------+

+--------------------------- CURRENT CONDITIONS -------------------------------+
| Temperature: 38F  |  Humidity: 65%                                           |
| High: 45F  |  Low: 32F                                                       |
| Precipitation Today: 0.1" rain                                               |
+------------------------------------------------------------------------------+

+----------------------------- 7-DAY SUMMARY ----------------------------------+
| Avg High: 42F  |  Avg Low: 30F  |  Current vs Avg: -4F                       |
| Total Precip: 0.8"                                                           |
| Days Since Last Significant Rain (>0.25"): 2 days                            |
+------------------------------------------------------------------------------+

+----------------------------- 14-DAY SUMMARY ---------------------------------+
| Avg High: 44F  |  Avg Low: 32F                                               |
| Total Precip: 1.5"                                                           |
+------------------------------------------------------------------------------+

+---------------------- 28-DAY PRECIPITATION COMPARISON -----------------------+
| Most Recent 28 Days:    3.2"                                                 |
| Previous 28 Days:       2.8"  (Change: +0.4")                                |
| Two Periods Prior:      4.1"  (Change from previous: -1.3")                  |
+------------------------------------------------------------------------------+

+--------------------------- GARDENING GUIDANCE -------------------------------+
| Soil Temperature: 28°F @ 2.4" | 29°F @ 7"                                    |
| 7-Day Avg Soil Temp: 28°F - TOO COLD for planting (need >50°F)               |
| Moon Phase: Waxing - favorable for planting above-ground crops               |
| Watering Recommendation: Monitor - no significant rain in 2 days             |
| Weekly Total: 0.8" - Below typical weekly needs (1.0-1.5")                   |
| Two-Week Total: 1.5"                                                         |
+------------------------------------------------------------------------------+
```


