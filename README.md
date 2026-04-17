# ICT AMD / Session-Based Liquidity Purge Indicator (XAUUSD)

Welcome! This document covers the `XAUUSD_Liquidity_Purge.pine` script designed specifically to track **Session-Based Liquidity Purges** and algorithmic footprints (Fair Value Gaps & Market Structure Shifts) on Gold.

## Core Strategy: The Power of 3 (PO3 / AMD Model)

As institutional algorithms trade vast quantities of capital, they build, manipulate, and distribute positions in clear, predictable phases based on the time of day. This indicator visually alerts you to this behavior on the **M5 (5-minute)** chart by breaking the day into three strict phases:

### Phase 1: Accumulation (Asian Range Build-Up)
**Time: 00:00 – 08:00 (CET)**
The Asian session establishes a consolidation range where equal highs (Buy Side Liquidity - BSL) and equal lows (Sell Side Liquidity - SSL) are formed. Retail traders view this as support and resistance. To algorithms, these are liquidity pools holding stop-loss orders.
- **Visuals:** The indicator draws a tinted blue box identifying the core Asian range and extends dashed BSL/SSL target lines into the future.

### Phase 2: Manipulation (The Judas Swing / Breakout Trap)
**Time: 09:00 – 10:30 (CET)**
This is the "Liar's Move." The algorithm engineers a sudden sweep outside the Asian Range to trap breakout traders and trigger tight stop-losses. This provides massive liquidity for Smart Money at a discount.
- **Visuals:** The indicator measures this sweep. If price pierces the BSL or SSL by an exact Pip/Point distance (configurable, default is $2.00 / 20 pips), it tags the chart with an unmissable **LIQUIDITY PURGE (Judas Up/Down)** trap label.

### Phase 3: Distribution (The Re-Pricing)
**Time: 10:30 – 17:00 (CET)**
The true intention of the algorithmic daily cycle is revealed. Price aggressively reclaims the range and forms new impulsive legs.
- **Visuals (Market Structure Shift):** The script watches the local swing highs/lows. If a bullish/bearish candle radically shifts this structure (its body representing 70%+ of the candle's entire wick-to-wick range—a true unbalanced push), an **MSS Line** is drawn.
- **Visuals (Fair Value Gap/Entry):** Upon triggering an MSS, the script automatically parses the exact fractal leg and perfectly shades in a green or red **FVG Box**. This is where the institutions left their footprint. This is your confirmed entry pointing toward the opposite side of the range.

---

## 💻 Installation on TradingView

1. Open the file `XAUUSD_Liquidity_Purge.pine` in any text editor.
2. Highlight all lines of code and copy (`Ctrl + C` or `Cmd + C`).
3. Open a Web Browser and go to [TradingView](https://www.tradingview.com/).
4. Open the **XAUUSD** chart and set your timeframe to **5 Minutes (M5)**.
5. At the bottom of the TradingView interface, click the **Pine Editor** tab.
6. Delete any placeholder code in the blank editor and paste (`Ctrl + V` or `Cmd + V`) the code you copied.
7. Important: Click **Save** and then click **Add to Chart**.

## ⚙️ Customizing Indicator Settings

Once the indicator is on your chart, click the **Gear Icon (Settings)** next to its name on the top-left of the chart:

- **Time Settings (Germany/CET):** The default periods map to the strict AMD model based in CET (UTC+2 DST). Ensure your time inputs align with your local broker if your provider operates on unique timezones.
- **Minimum Raid Size vs Range:** The required sweep distance for the Judas phase. Gold algos hunt deeply. A default of `$2.00` checks for 20-pip deep sweeps. You can increase this to wait for heavier stop hunts.
- **Unbalanced Candle Body %:** The aggressive momentum threshold for an MSS shift. A `0.70` (70%) value ensures you only take trades driven by high volume candles rather than weak consolidation wicks.

## Trading Gold in 2026: A Best Practice

Always stay vigilant for Dollar Index (DXY) inversions. If the DXY taps a major HTF Premium/Discount array exactly around 15:30 (NY Open), Gold will often execute an inverse reversal sweep. Trust the algorithm over retail patterns.
