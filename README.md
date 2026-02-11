# 🎯 M4DI~UciH4 Trading Suite

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform: MT5](https://img.shields.io/badge/Platform-MetaTrader%205-blue.svg)](https://www.metatrader5.com/)
[![Language: MQL5](https://img.shields.io/badge/Language-MQL5-green.svg)](https://www.mql5.com/)
[![Status: Active](https://img.shields.io/badge/Status-Active-success.svg)]()

> **Professional-grade trading indicators suite for MetaTrader 5** - Advanced Market Structure Analysis & Smart Scalping System

---

## 📋 Table of Contents

- [Overview](#overview)
- [Indicators](#indicators)
  - [XAUUSD Observer V2](#1-xauusd-observer-v2)
  - [Scalping Suite](#2-scalping-suite)
- [Features](#features)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage Guide](#usage-guide)
- [Technical Details](#technical-details)
- [Screenshots](#screenshots)
- [Performance Tips](#performance-tips)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🌟 Overview

**M4DI~UciH4 Trading Suite** adalah koleksi indikator profesional untuk MetaTrader 5 yang dirancang khusus untuk analisis struktur pasar dan trading scalping dengan precision tinggi. Suite ini terdiri dari dua indikator utama yang saling melengkapi:

1. **XAUUSD Observer V2** - Advanced Market Structure & Supply/Demand Analysis
2. **Scalping Suite** - Smart Support/Resistance Detection with Entry System

### 🎖️ Key Highlights

- ✅ **Professional Grade** - Production-ready dengan algoritma teroptimasi
- ✅ **Multi-Timeframe Analysis** - HTF, MTF, LTF bias detection
- ✅ **Smart Zone Detection** - Supply/Demand, Order Blocks, FVG, Breakers
- ✅ **Automated Signals** - Entry points dengan confidence scoring
- ✅ **Risk Management** - Built-in lot calculation & risk controls
- ✅ **Real-time Dashboard** - Comprehensive market overview
- ✅ **Alert System** - Popup, Push notifications, Sound alerts
- ✅ **Customizable** - Extensive parameters untuk fine-tuning

---

## 📊 Indicators

## 1. XAUUSD Observer V2

### 🎯 Purpose
Indikator komprehensif untuk analisis struktur pasar dengan fokus pada XAUUSD (Gold). Mengidentifikasi market structure shifts, supply/demand zones, order blocks, fair value gaps, dan liquidity levels.

### 🔑 Core Features

#### Market Structure Detection (M15)
- **Swing Point Identification**: Higher High (HH), Higher Low (HL), Lower High (LH), Lower Low (LL)
- **Equal Highs/Lows (EQH/EQL)**: Deteksi level penting dengan tolerance kustom
- **Break of Structure (BOS)**: Bullish & Bearish struktur breaks
- **Change of Character (CHOCH)**: Market reversal signals
- **Multi-Structure Support**: Bullish, Bearish, Ranging, Transition states

#### Supply & Demand Zones (M5)
- **Base + Impulse Detection**: Identifikasi valid zones menggunakan base candle analysis
- **Zone Strength Classification**: Weak, Moderate, Strong, Extreme
- **Smart Mitigation**: Automatic zone invalidation saat termitigasi
- **Zone Retest Tracking**: Monitor touch count & retests
- **Fresh vs Tested**: Visual distinction untuk zone baru dan sudah disentuh

#### Order Blocks
- **Bullish OB**: Last down candle sebelum strong bullish move
- **Bearish OB**: Last up candle sebelum strong bearish move
- **Structure Confirmation**: OB dengan BOS requirement (opsional)
- **ATR-based Validation**: Minimum move requirement untuk valid OB

#### Fair Value Gaps (FVG)
- **Gap Detection**: 3-candle pattern dengan gap minimum size
- **Fill Tracking**: Monitor FVG fill percentage secara real-time
- **Auto-cleanup**: Remove filled FVG (opsional)
- **Size Filter**: Minimum gap size dalam points

#### Liquidity Detection
- **Swing High/Low Liquidity**: Equal highs/lows sebagai liquidity pools
- **Volume Validation**: High volume nodes di liquidity levels
- **Sweep Monitoring**: Track liquidity grabs

#### Multi-Timeframe Bias
- **HTF Bias (H4/D1)**: Higher timeframe market direction
- **MTF Bias (H1)**: Medium timeframe trend
- **LTF Bias (M15)**: Lower timeframe structure
- **Entry Bias (M5)**: Execution timeframe sentiment
- **Bias Strength**: 0-100 scoring system
- **Smart Recommendation**: Buy/Sell/Wait signals

#### Session Detection
- **Asian Session**: Customizable hours
- **London Session**: European market hours
- **New York Session**: US market hours
- **Session Highlighting**: Visual boxes untuk setiap sesi

### 📊 Visual Elements

- **Swing Lines**: Connect swing points dengan trend lines
- **Supply/Demand Rectangles**: Shaded zones dengan transparency
- **Order Block Boxes**: Highlighted bullish/bearish blocks
- **FVG Regions**: Semi-transparent gap areas
- **Liquidity Markers**: Horizontal lines di key levels
- **BOS/CHOCH Arrows**: Visual break indicators
- **Session Boxes**: Time-based session highlights
- **Interactive Dashboard**: Real-time market overview

### ⚙️ Configuration Parameters

```mql5
// SWING SETTINGS
Swing_Lookback = 3                  // Bars untuk swing detection
Swing_Lookback_Strict = 5           // Strict swing confirmation
MS_History_Bars = 500               // Historical analysis depth
EQH_EQL_Tolerance = 0.30            // Equal high/low tolerance (pips)

// SUPPLY/DEMAND SETTINGS
Max_Base_Candles = 4                // Maximum base candles
Min_Impulse_Body_Percent = 55.0     // Body % untuk valid impulse
Min_Impulse_ATR_Mult = 1.0          // ATR multiplier
Zone_Valid_Bars = 100               // Zone validity period
Max_Zones_Display = 15              // Maximum zones to show

// ORDER BLOCK SETTINGS
OB_Lookback = 50                    // Bars untuk OB detection
OB_Must_Break_Structure = true      // Require BOS for OB
OB_Min_Move_ATR = 1.5              // Minimum ATR move

// FVG SETTINGS
FVG_Min_Size_Points = 15           // Minimum gap size
Max_FVG_Display = 8                // Maximum FVG to show
FVG_Fill_Threshold = 50.0          // Fill % untuk auto-remove
```

---

## 2. Scalping Suite

### 🎯 Purpose
Sistem scalping komprehensif dengan deteksi Support/Resistance otomatis dan smart entry signals. Dirancang untuk timeframe rendah (M1-M15) dengan fokus pada high-probability setups.

### 🔑 Core Features

#### Support/Resistance Detection
- **Swing-based Levels**: Identifikasi S/R dari swing points
- **Cluster Analysis**: Group levels dalam proximity range
- **Touch Point Validation**: Minimum touches untuk level strength
- **Volume Confirmation**: High volume nodes validation
- **Fresh Area Detection**: Recent vs historical levels
- **Auto-expiry**: Remove expired/weak levels

#### Smart Entry System
- **Proximity Detection**: Price near S/R zones
- **RSI Confirmation**: Oversold/Overbought validation
- **Momentum Filter**: SMA-based trend confirmation
- **Retracement Analysis**: Entry pada pullback optimal
- **Confidence Scoring**: 0-100% signal strength
- **Multi-factor Validation**: Trend + Volatility + RSI

#### Signal Types
- **BUY Signals**: 
  - Price near Support
  - RSI oversold
  - Bullish momentum
  - Retracement completion
- **SELL Signals**:
  - Price near Resistance
  - RSI overbought
  - Bearish momentum
  - Retracement completion

#### Risk Management
- **Auto Lot Calculation**: Berdasarkan account risk %
- **Stop Loss Logic**: Area-based dengan buffer
- **Take Profit Levels**: TP1 (1:1.5) & TP2 (1:3.0)
- **Breakeven System**: Auto BE activation
- **Max Drawdown Protection**: Stop trading saat DD threshold
- **Trade Limiting**: Max trades per area
- **Cooldown System**: Delay setelah loss

#### Market Analysis
- **Trend Detection**: Bullish/Bearish/Neutral
- **Volatility Assessment**: Low/Medium/High (ATR-based)
- **Spread Monitoring**: Real-time spread tracking
- **Performance Tracking**: Win rate & P/L statistics

### 📊 Visual Elements

- **Buy/Sell Arrows**: Plotted pada chart
- **Support Levels**: Blue horizontal markers
- **Resistance Levels**: Red horizontal markers
- **Entry Lines**: Dashed line untuk entry price
- **Stop Loss Lines**: Red solid line
- **Take Profit Lines**: Green dotted lines (TP1 & TP2)
- **Zone Rectangles**: Shaded S/R areas
- **Dashboard Panel**: Real-time statistics & signals

### ⚙️ Configuration Parameters

```mql5
// DETECTION SETTINGS
InpLookbackBars = 20               // Swing lookback period
InpMinStrength = 3                 // Minimum touch points
InpFreshBars = 50                  // Fresh area lookback
InpClusterPips = 5.0              // Cluster range
InpVolMultiplier = 1.5            // Volume validation

// ENTRY SETTINGS
InpProximityPips = 3.0            // Area proximity
InpRSIPeriod = 7                  // RSI period
InpRSIOversold = 35               // RSI oversold level
InpRSIOverbought = 65             // RSI overbought level
InpRetracePercent = 30.0          // Entry retrace %

// RISK MANAGEMENT
InpRiskPercent = 1.0              // Risk per trade
InpMaxLot = 0.1                   // Maximum lot size
InpMinLot = 0.01                  // Minimum lot size
InpMaxTradesPerArea = 1           // Trades per area limit
InpCooldownBars = 3               // Cooldown period
InpMaxDrawdown = 5.0              // Max DD %
InpBreakevenPips = 10.0           // BE activation

// ALERTS
InpEnableAlerts = true            // Popup alerts
InpEnablePush = true              // Push notifications
InpEnableSound = true             // Sound alerts
```

---

## ✨ Features

### Combined Suite Benefits

| Feature | XAUUSD Observer V2 | Scalping Suite |
|---------|-------------------|----------------|
| Market Structure | ✅ Advanced | ✅ Basic |
| Supply/Demand Zones | ✅ Multi-level | ❌ |
| Support/Resistance | ❌ | ✅ Advanced |
| Order Blocks | ✅ Full | ❌ |
| Fair Value Gaps | ✅ Full | ❌ |
| Entry Signals | ⚠️ Manual | ✅ Automated |
| Risk Management | ❌ | ✅ Built-in |
| Multi-Timeframe | ✅ 4 TF | ⚠️ Single TF |
| Dashboard | ✅ Comprehensive | ✅ Statistics |
| Alerts | ✅ Basic | ✅ Advanced |
| Session Analysis | ✅ Full | ❌ |
| Logging | ❌ | ✅ CSV Export |

### 🎨 Customization Options

**XAUUSD Observer V2:**
- 50+ customizable parameters
- Full color scheme customization
- Modular design (enable/disable features)
- Dashboard positioning & transparency
- Visual element styling

**Scalping Suite:**
- 30+ configuration parameters
- Custom alert sounds
- Adjustable risk parameters
- Dashboard customization
- CSV logging options

---

## 📥 Installation

### Prerequisites
- MetaTrader 5 Terminal (Build 3640+)
- Windows, macOS, atau Linux
- Active trading account (demo/live)

### Installation Steps

1. **Download Files**
   ```bash
   git clone https://github.com/RizkyEvory/M4DI-UciH4-Trading-Suite.git
   cd M4DI-UciH4-Trading-Suite
   ```

2. **Copy to MT5 Directory**
   
   **Windows:**
   ```
   C:\Users\[YourName]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Indicators\
   ```
   
   **macOS:**
   ```
   ~/Library/Application Support/com.MetaQuotes.MetaTrader5/Bottles/metatrader5/drive_c/users/[user]/Application Data/MetaQuotes/Terminal/[TerminalID]/MQL5/Indicators/
   ```

3. **File Placement**
   ```
   MQL5/Indicators/
   ├── M4DI_UciH4_XAUUSD_Observer_V2.mq5
   └── M4DI_UciH4_ScalpingSuite.mq5
   ```

4. **Compile Indicators**
   - Open MetaEditor (F4 in MT5)
   - Open each .mq5 file
   - Click Compile (F7)
   - Check for errors in Toolbox

5. **Attach to Chart**
   - Open chart (XAUUSD recommended untuk Observer)
   - Navigator → Indicators → Custom
   - Double-click indicator name
   - Configure parameters
   - Click OK

### Verification
- Check chart for visual elements
- Verify dashboard appears
- Test by changing timeframes
- Monitor Experts tab untuk errors

---

## ⚙️ Configuration

### XAUUSD Observer V2 Setup

#### Recommended Settings for XAUUSD

**Conservative (Higher Timeframe):**
```mql5
Swing_Lookback = 5
Max_Base_Candles = 3
Min_Impulse_Body_Percent = 60.0
Zone_Valid_Bars = 200
```

**Aggressive (Lower Timeframe):**
```mql5
Swing_Lookback = 3
Max_Base_Candles = 5
Min_Impulse_Body_Percent = 50.0
Zone_Valid_Bars = 100
```

#### Module Configuration

Enable/disable features sesuai kebutuhan:
```mql5
Enable_MarketStructure = true      // Essential
Enable_SupplyDemand = true         // High priority
Enable_OrderBlocks = true          // Important
Enable_Liquidity = true            // Medium priority
Enable_FVG = true                  // Nice to have
Enable_Session = false             // Optional
Enable_Dashboard = true            // Recommended
```

### Scalping Suite Setup

#### Recommended Settings by Timeframe

**M1 Scalping:**
```mql5
InpLookbackBars = 10
InpProximityPips = 2.0
InpRiskPercent = 0.5
InpMaxTradesPerArea = 2
```

**M5 Scalping:**
```mql5
InpLookbackBars = 20
InpProximityPips = 3.0
InpRiskPercent = 1.0
InpMaxTradesPerArea = 1
```

**M15 Swing Scalping:**
```mql5
InpLookbackBars = 30
InpProximityPips = 5.0
InpRiskPercent = 1.5
InpMaxTradesPerArea = 1
```

#### Risk Management Settings

**Conservative:**
```mql5
InpRiskPercent = 0.5
InpMaxLot = 0.05
InpMaxDrawdown = 3.0
InpCooldownBars = 5
```

**Moderate:**
```mql5
InpRiskPercent = 1.0
InpMaxLot = 0.1
InpMaxDrawdown = 5.0
InpCooldownBars = 3
```

**Aggressive:**
```mql5
InpRiskPercent = 2.0
InpMaxLot = 0.2
InpMaxDrawdown = 8.0
InpCooldownBars = 1
```

---

## 📖 Usage Guide

### Getting Started

#### 1. XAUUSD Observer V2 Workflow

**Step 1: Higher Timeframe Analysis**
- Switch ke H4/D1 chart
- Check HTF Bias di dashboard
- Identify major supply/demand zones
- Note key liquidity levels

**Step 2: Structure Confirmation (M15)**
- Identify current market structure
- Look for BOS/CHOCH signals
- Mark swing points (HH, HL, LH, LL)
- Check for equal highs/lows

**Step 3: Zone Identification (M5)**
- Locate fresh supply/demand zones
- Verify zone strength (Strong/Extreme)
- Check order blocks alignment
- Identify FVG areas

**Step 4: Entry Timing**
- Wait for price to reach zone
- Confirm with lower TF structure
- Look for confluence with OB/FVG
- Execute with proper risk management

#### 2. Scalping Suite Workflow

**Step 1: Market Analysis**
- Check dashboard trend indicator
- Verify volatility level
- Monitor spread (should be < 2 pips)
- Check active signals

**Step 2: Signal Confirmation**
- Wait for Buy/Sell arrow
- Check confidence score (>70% ideal)
- Verify RSI alignment
- Confirm price near S/R

**Step 3: Trade Execution**
- Note entry price from signal
- Set stop loss as indicated
- Set TP1 and TP2 levels
- Calculate lot size (auto-calculated)

**Step 4: Trade Management**
- Monitor breakeven activation
- Partial close at TP1 (50%)
- Trail stop after TP1 hit
- Full exit at TP2 or reversal signal

### Trading Strategies

#### Strategy 1: Supply/Demand Scalping
```
Observer V2: Identify fresh demand zone
Scalping Suite: Wait for buy signal near zone
Entry: Signal confirmation with >75% confidence
SL: Below demand zone
TP1: 1.5R, TP2: 3R
```

#### Strategy 2: Structure Break Trading
```
Observer V2: Identify CHOCH or strong BOS
Scalping Suite: Wait for pullback signal
Entry: Retracement to 30-50% with signal
SL: Below/above structure
TP1: Previous swing, TP2: Extension
```

#### Strategy 3: Liquidity Grab
```
Observer V2: Mark equal highs/lows
Scalping Suite: Wait for sweep + reversal signal
Entry: After liquidity grab with signal
SL: Beyond liquidity level
TP1: Return to range, TP2: Opposite liquidity
```

### Best Practices

**Do's:**
- ✅ Use both indicators together for confluence
- ✅ Start with demo account
- ✅ Respect risk management rules
- ✅ Trade during liquid sessions
- ✅ Keep a trading journal
- ✅ Review dashboard before trading
- ✅ Wait for high-confidence signals
- ✅ Use proper lot sizing

**Don'ts:**
- ❌ Trade without signal confirmation
- ❌ Ignore stop loss levels
- ❌ Over-leverage your account
- ❌ Trade during low liquidity
- ❌ Chase missed entries
- ❌ Ignore market structure
- ❌ Trade counter to bias
- ❌ Use maximum lot size always

---

## 🔧 Technical Details

### System Requirements

**Minimum:**
- CPU: Dual Core 2.0 GHz
- RAM: 4 GB
- Disk: 500 MB free space
- Internet: 1 Mbps stable

**Recommended:**
- CPU: Quad Core 3.0 GHz+
- RAM: 8 GB+
- Disk: 1 GB free space (untuk logging)
- Internet: 5 Mbps+
- SSD untuk faster performance

### Performance Metrics

**XAUUSD Observer V2:**
- **Memory Usage**: ~15-25 MB
- **CPU Load**: 2-5% (on indicator calculation)
- **Calculation Time**: <100ms per bar
- **Max Bars Analyzed**: 500 (configurable)
- **Objects Created**: 50-200 (depends on features)

**Scalping Suite:**
- **Memory Usage**: ~8-15 MB
- **CPU Load**: 1-3%
- **Calculation Time**: <50ms per bar
- **Buffer Size**: 8 buffers
- **Signal Generation**: Real-time

### Architecture

**XAUUSD Observer V2:**
```
Core Components:
├── Market Structure Analyzer (M15)
├── Supply/Demand Zone Detector (M5)
├── Order Block Scanner
├── FVG Identifier
├── Liquidity Level Tracker
├── Multi-Timeframe Bias Engine
├── Session Analyzer
└── Dashboard Renderer
```

**Scalping Suite:**
```
Core Components:
├── S/R Detection Engine
├── Signal Generation System
├── Risk Calculator
├── Entry Logic Processor
├── Market Statistics Analyzer
├── Alert Manager
├── Dashboard System
└── CSV Logger
```

### Dependencies

**Built-in Functions:**
- iHigh, iLow, iClose, iOpen, iTime
- iRSI, iMA, iATR, iVolume (Scalping Suite)
- SymbolInfo functions
- Object management functions

**No External Libraries Required**

### Update Frequency

**XAUUSD Observer V2:**
- Market Structure: Every new bar (M15)
- Zones: Every new bar (M5)
- Dashboard: Every tick
- FVG: Real-time fill tracking

**Scalping Suite:**
- S/R Detection: Every new bar
- Signal Generation: Every tick
- Risk Calculation: On signal
- Dashboard: Every tick

---

## 📸 Screenshots

### XAUUSD Observer V2

**Full Chart View:**
```
[Market Structure + Supply/Demand Zones + Order Blocks]
• Swing points dengan connecting lines
• Supply zones (red boxes) & Demand zones (green boxes)
• Order blocks highlighted
• FVG areas shaded
• Dashboard dengan multi-TF bias
```

**Dashboard:**
```
┌─────────────────────────────────────┐
│  M4DI~UciH4 XAUUSD Observer V2     │
│─────────────────────────────────────│
│  HTF (H4): BULLISH ↑  [Strong]     │
│  MTF (H1): BULLISH ↑  [Moderate]   │
│  LTF (M15): RANGING ↔  [Weak]      │
│  Entry: BULLISH ↑  [75%]           │
│─────────────────────────────────────│
│  Recommendation: ⚡ BUY            │
│─────────────────────────────────────│
│  Supply Zones: 3  Demand Zones: 5  │
│  Order Blocks: 4  Liquidity: 8     │
│  FVG Active: 2                      │
│─────────────────────────────────────│
│  Updated: 14:23:45                  │
└─────────────────────────────────────┘
```

### Scalping Suite

**Chart with Signals:**
```
[S/R Levels + Entry Signals + Trade Management Lines]
• Support levels (blue)
• Resistance levels (red)
• Buy arrows (green) dengan confidence
• Sell arrows (red) dengan confidence
• Entry/SL/TP lines
```

**Dashboard:**
```
┌─────────────────────────────────────┐
│  M4DI Scalping Suite  [M5]         │
│─────────────────────────────────────│
│  Trend: BULLISH ↑                  │
│  Volatility: MEDIUM                 │
│  Spread: 1.8 pips                   │
│─────────────────────────────────────│
│  🟢 BUY SIGNAL ACTIVE               │
│  Entry: 2045.32                     │
│  SL: 2043.12  (-22 pips)           │
│  TP1: 2048.45  TP2: 2051.78        │
│  Confidence: 78%                    │
│─────────────────────────────────────│
│  Today P/L: +2.3%                  │
│  Win Rate: 68%                      │
│  Total Trades: 12  Wins: 8         │
│  Drawdown: 1.2%                     │
│─────────────────────────────────────│
│  Support Areas: 3                   │
│  Resistance Areas: 4                │
│  Updated: 14:23:45                  │
└─────────────────────────────────────┘
```

---

## 🚀 Performance Tips

### Optimization

**XAUUSD Observer V2:**

1. **Reduce History Bars**
   ```mql5
   MS_History_Bars = 300  // Instead of 500
   ```
   
2. **Limit Zone Display**
   ```mql5
   Max_Zones_Display = 10  // Instead of 15
   Max_FVG_Display = 5     // Instead of 8
   ```

3. **Disable Unused Features**
   ```mql5
   Enable_Session = false   // If not needed
   Enable_FVG = false      // On slower systems
   ```

4. **Minimize Dashboard Updates**
   ```mql5
   // Update only on new bar instead of every tick
   if(g_IsNewBar) UpdateDashboard();
   ```

**Scalping Suite:**

1. **Optimize Lookback Period**
   ```mql5
   InpLookbackBars = 15  // Instead of 20
   InpFreshBars = 30     // Instead of 50
   ```

2. **Reduce Alert Frequency**
   ```mql5
   // 60 second cooldown already implemented
   if(TimeCurrent() - g_LastAlertTime < 60) return;
   ```

3. **Limit Objects**
   ```mql5
   InpShowEntryLines = false  // If not needed
   ```

### Multi-Chart Setup

**Recommended Layout:**

```
┌────────────┬────────────┐
│   H4/D1    │     M15    │
│ (Structure)│  (Entry)   │
│  Observer  │  Observer  │
├────────────┼────────────┤
│     M5     │     M1     │
│  (Zones)   │ (Scalping) │
│  Observer  │   Suite    │
└────────────┴────────────┘
```

**Workflow:**
1. H4/D1: Identify bias & major zones
2. M15: Confirm structure & entry area
3. M5: Fine-tune zones & OB
4. M1: Execute with Scalping Suite

### Resource Management

**Memory:**
- Close unused charts
- Limit indicator instances
- Clear old logs regularly

**CPU:**
- Avoid running on all charts
- Use on active trading pairs only
- Disable alerts when not monitoring

---

## ❓ Troubleshooting

### Common Issues

#### 1. Indicator Not Loading

**Symptoms:**
- No visual elements on chart
- Empty dashboard

**Solutions:**
```mql5
// Check compilation errors
// Verify file placement
// Restart MT5 terminal
// Check Experts tab for errors
```

#### 2. Dashboard Not Showing

**Solutions:**
```mql5
Enable_Dashboard = true  // In inputs
Dashboard_Position = DASH_TOP_LEFT  // Try different position
Dashboard_Minimized = false
```

#### 3. No Signals Generated (Scalping Suite)

**Check:**
- Price near S/R levels?
- RSI within trigger range?
- Sufficient market volatility?
- Cooldown period active?

**Solutions:**
```mql5
InpProximityPips = 5.0  // Increase proximity
InpMinStrength = 2      // Lower touch requirement
```

#### 4. Too Many Zones/Objects

**Solutions:**
```mql5
Max_Zones_Display = 8
Max_FVG_Display = 4
Remove_Mitigated_Zones = true
Show_Filled_FVG = false
```

#### 5. Performance Issues

**Solutions:**
- Reduce history bars
- Disable unused features
- Limit chart instances
- Increase calculation delay
- Use SSD for MT5 installation

### Error Messages

| Error | Cause | Solution |
|-------|-------|----------|
| "Invalid symbol" | Wrong symbol | Use XAUUSD for Observer |
| "Array out of range" | Insufficient bars | Increase chart history |
| "Failed to create object" | Too many objects | Clean chart, restart MT5 |
| "Invalid lot size" | Lot parameters wrong | Check min/max lot settings |
| "No RSI handle" | Indicator init failed | Restart indicator |

### Support

**Before Reporting:**
1. Check MT5 version (minimum 3640)
2. Verify compilation successful
3. Review Experts tab logs
4. Test on demo account
5. Provide screenshots

**Report Issues:**
- Create GitHub issue
- Include: MT5 version, settings, screenshots
- Describe expected vs actual behavior

---

## 🤝 Contributing

Kontribusi sangat diterima! Berikut cara berkontribusi:

### Guidelines

1. **Fork Repository**
   ```bash
   git fork https://github.com/RizkyEvory/M4DI-UciH4-Trading-Suite.git
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```

3. **Commit Changes**
   ```bash
   git commit -m 'Add: AmazingFeature description'
   ```

4. **Push to Branch**
   ```bash
   git push origin feature/AmazingFeature
   ```

5. **Open Pull Request**
   - Describe changes clearly
   - Include test results
   - Update documentation if needed

### Contribution Areas

**Code:**
- Performance optimizations
- New features
- Bug fixes
- Code refactoring

**Documentation:**
- Improve README
- Add usage examples
- Translate to other languages
- Create video tutorials

**Testing:**
- Report bugs
- Suggest improvements
- Share successful strategies
- Provide feedback

### Code Style

```mql5
// Use meaningful variable names
int swingLookback = 3;  // Good
int x = 3;              // Bad

// Add comments for complex logic
// Calculate zone strength based on touches and volume
zoneStrength = CalculateStrength(touches, volume);

// Follow consistent formatting
if(condition)
{
    DoSomething();
}
```

---

## 📄 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2024 M4DI~UciH4

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

**Key Points:**
- ✅ Free to use, modify, distribute
- ✅ Commercial use allowed
- ✅ No warranty provided
- ✅ Credit appreciated but not required

---

## 📞 Contact

**Developer:** M4DI~UciH4  
**GitHub:** [@RizkyEvory](https://github.com/RizkyEvory)  
**Repository:** [M4DI-UciH4-Trading-Suite](https://github.com/RizkyEvory/M4DI-UciH4-Trading-Suite)

**Support Channels:**
- 🐛 Issues: [GitHub Issues](https://github.com/RizkyEvory/M4DI-UciH4-Trading-Suite/issues)
- 💬 Discussions: [GitHub Discussions](https://github.com/RizkyEvory/M4DI-UciH4-Trading-Suite/discussions)
- 📧 Email: [Create issue for private contact]

---

## 🙏 Acknowledgments

**Special Thanks:**
- MetaQuotes Software Corp. for MetaTrader 5 platform
- MQL5 Community for resources and support
- All contributors and testers
- Trading community for feedback

**Inspiration:**
- ICT (Inner Circle Trader) concepts
- Smart Money Concepts (SMC)
- Supply and Demand trading methodology
- Price Action analysis principles

---

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/RizkyEvory/M4DI-UciH4-Trading-Suite?style=social)
![GitHub forks](https://img.shields.io/github/forks/RizkyEvory/M4DI-UciH4-Trading-Suite?style=social)
![GitHub issues](https://img.shields.io/github/issues/RizkyEvory/M4DI-UciH4-Trading-Suite)
![GitHub pull requests](https://img.shields.io/github/issues-pr/RizkyEvory/M4DI-UciH4-Trading-Suite)
![GitHub last commit](https://img.shields.io/github/last-commit/RizkyEvory/M4DI-UciH4-Trading-Suite)

---

## ⚠️ Disclaimer

**IMPORTANT - READ CAREFULLY:**

**Trading Risk:**
- Trading involves substantial risk of loss
- Past performance does not guarantee future results
- These indicators are tools, not guarantees
- Always use proper risk management
- Never risk more than you can afford to lose

**Educational Purpose:**
- Indicators provided for educational purposes
- No financial advice given
- Users responsible for their own trading decisions
- Seek professional financial advice if needed

**No Warranty:**
- Software provided "as is"
- No guarantee of profitability
- Developer not liable for trading losses
- Use at your own risk

**Best Practices:**
- Start with demo account
- Understand the indicators fully
- Practice risk management
- Keep learning and improving

---

## 🔄 Version History

### v2.00 (Current)
- ✨ Complete rewrite with enhanced algorithms
- ✨ Multi-timeframe bias system
- ✨ Advanced zone strength calculation
- ✨ Smart entry signal generation
- ✨ Improved dashboard design
- ✨ Better performance optimization
- 🐛 Fixed memory leaks
- 🐛 Resolved object creation issues

### v1.00
- 🎉 Initial release
- ✅ Basic market structure detection
- ✅ Supply/Demand zones
- ✅ Simple dashboard

---

## 🗺️ Roadmap

### Planned Features

**XAUUSD Observer V2:**
- [ ] Divergence detection (RSI/Price)
- [ ] Volume profile integration
- [ ] Fibonacci auto-levels
- [ ] Trade management panel
- [ ] Multi-symbol support
- [ ] Historical backtest mode
- [ ] Strategy tester integration

**Scalping Suite:**
- [ ] ML-based signal filtering
- [ ] Auto-trading mode (EA conversion)
- [ ] Risk/Reward optimizer
- [ ] Trailing stop automation
- [ ] Multi-pair scanning
- [ ] Cloud sync for settings
- [ ] Mobile notifications

**Both:**
- [ ] Strategy templates library
- [ ] Performance analytics
- [ ] Educational materials
- [ ] Video tutorials
- [ ] Community strategies sharing

---

<div align="center">

### 🌟 Star this repository if you find it helpful!

**Made with ❤️ by M4DI~UciH4**

[⬆ Back to Top](#-madi~ucih4-trading-suite)

</div>

---

**Last Updated:** February 2026  
**Version:** 2.00  
**Status:** ✅ Active Development
