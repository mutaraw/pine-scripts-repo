# **Pine Scripts Repo**

## **William's Buy & Sell Signals**

This repository contains Pine Script Indicators and Strategies for TradingView to generate buy and sell signals using:

### **Included Strategies**
1. **Relative Strength Index (RSI)**: To detect overbought and oversold market conditions.
2. **Bollinger Bands**: For volatility analysis and breakout detection.
3. **VWAP (Volume Weighted Average Price)**: For dynamic support/resistance levels and trend confirmation.

---

### **Logic and Flow**

#### **1. Alternate Resolution Inputs**
The script allows users to analyze data at custom resolutions (e.g., monthly, weekly, daily) using the `reso()` function.

**Rationale**: Traders often analyze multiple timeframes to confirm trends. This feature lets users adjust the strategy for higher or lower resolutions as needed.

---

#### **2. Smoothed Moving Averages (SMMA)**
The `f_smma` function calculates a Smoothed Moving Average for the open, high, low, and close prices.

**Purpose**: SMMA is less sensitive to short-term fluctuations compared to simple moving averages, providing smoother data for signal generation.

**Flow**:
- Calculate SMMA for key price points: open, high, low, and close.
- Use these values to determine price trends and crossovers.

---

#### **3. Price Channel and Breakout Strategies**
- **Price Channel Strategy**:
  - Tracks the highest high (hh) and lowest low (ll) over a set period.
  - Confirms trades when the close price breaks above or below these levels.

- **Channel Breakout Strategy**:
  - Identifies breakouts using volatility-adjusted price bounds (`upbound`, `downbound`).
  - Confirms long or short trades based on breakout direction.

**Rationale**: These strategies help detect and capitalize on major price movements.

---

#### **4. VWAP Bands**
The script includes multi-level VWAP bands with adjustable calculation modes (Standard Deviation or Percentage). Customizable features include:
- Anchoring VWAP to session, weekly, or monthly periods.
- Multiple band multipliers for finer volatility analysis.
- Option to hide VWAP on daily or higher timeframes.

---

#### **5. Momentum**
The script calculates momentum values (`mom0`, `mom1`) to gauge the strength of price movements.

**Logic**:
- Momentum = Current price - Price `n` periods ago.
- Positive momentum strengthens buy signals, while negative momentum strengthens sell signals.

**Rationale**: Momentum ensures trades align with strong directional moves.

---

### **How to Use**
1. Copy the script into TradingView's Pine Editor.
2. Adjust parameters such as RSI length, Bollinger Band settings, VWAP, and channel periods to suit your trading strategy.
3. Add the script to your chart as an indicator or strategy.
4. Use the alerts feature for real-time signal notifications.
5. (Optional) Use a Chrome Auto-Refresh Extension for consistent label updates.
