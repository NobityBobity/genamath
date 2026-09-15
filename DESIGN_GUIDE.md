# GenaMath - Design & Build Guide

## 🎨 Design Philosophy
**Classy, Professional, Minimal**
- Elegant dark theme with gold accents
- Clean typography and generous spacing
- Smooth transitions and intuitive navigation

---

## 🎨 Color Scheme

### Primary Colors
- **Background**: `#1a1a1a` (Deep Black)
- **Card Background**: `#2d2d2d` (Charcoal)
- **Accent**: `#d4af37` (Gold)
- **Text Primary**: `#ffffff` (White)
- **Text Secondary**: `#b0b0b0` (Light Gray)

### States
- **Active/Focused**: `#d4af37` (Gold)
- **Disabled**: `#555555` (Dark Gray)
- **Success**: `#4ade80` (Green)
- **Error**: `#ff6b6b` (Red)

---

## 📱 Screen Structure

### 1. **Home Screen (Main Menu)**
```
┌─────────────────────────┐
│      GenaMath           │
│    Financial Tools      │
├─────────────────────────┤
│                         │
│  [ Savings Calc ]       │
│                         │
│  [ Bonus Calc ]         │
│                         │
│  [ Currency Conv ]      │
│                         │
└─────────────────────────┘
```

**Components:**
- Title: "GenaMath" (24sp, Gold, Bold)
- Subtitle: "Financial Tools" (14sp, Light Gray)
- 3 Button Cards (each full width, padding, gold border on hover)
- Background: Dark theme with subtle gradient

---

### 2. **Savings Calculator Screen**
```
┌─────────────────────────┐
│  < GenaMath             │
│  SAVINGS CALCULATOR     │
├─────────────────────────┤
│                         │
│  Initial Amount ($):    │
│  [________] (Number)    │
│                         │
│  Monthly Contribution:  │
│  [________] (Number)    │
│                         │
│  Annual Interest (%):   │
│  [________] (Number)    │
│                         │
│  Time Period (Years):   │
│  [________] (Number)    │
│                         │
│  [ CALCULATE ]          │
│                         │
├─────────────────────────┤
│  Total Savings:         │
│  $ [RESULT]             │
│                         │
│  Total Interest Earned: │
│  $ [INTEREST]           │
└─────────────────────────┘
```

**Formula:**
```
A = P(1 + r/n)^(nt) + PMT × [((1 + r/n)^(nt) - 1) / (r/n)]
Where:
- P = Initial Amount
- PMT = Monthly Contribution
- r = Annual Interest Rate (as decimal)
- n = Compounding periods per year (12 for monthly)
- t = Time in years
```

---

### 3. **Bonus Calculator Screen**
```
┌─────────────────────────┐
│  < GenaMath             │
│  BONUS CALCULATOR       │
├─────────────────────────┤
│                         │
│  Base Amount ($):       │
│  [________] (Number)    │
│                         │
│  Bonus Percentage (%):  │
│  [________] (Number)    │
│                         │
│  [ CALCULATE ]          │
│                         │
├─────────────────────────┤
│  Bonus Amount:          │
│  $ [RESULT]             │
│                         │
│  Total (Base + Bonus):  │
│  $ [TOTAL]              │
└─────────────────────────┘
```

**Formula:**
```
Bonus = Base × (Percentage / 100)
Total = Base + Bonus
```

---

### 4. **Currency Converter Screen**
```
┌─────────────────────────┐
│  < GenaMath             │
│  CURRENCY CONVERTER     │
├─────────────────────────┤
│                         │
│  Amount:                │
│  [________] (Number)    │
│                         │
│  From Currency:         │
│  [USD ▼]  (Dropdown)    │
│                         │
│  To Currency:           │
│  [EUR ▼]  (Dropdown)    │
│                         │
│  [ CONVERT ]            │
│                         │
├─────────────────────────┤
│  Result:                │
│  [AMOUNT] [CURRENCY]    │
│                         │
│  Exchange Rate:         │
│  1 USD = [RATE] EUR     │
└─────────────────────────┘
```

**Supported Currencies:**
- USD, EUR, GBP, JPY, CAD, AUD, CHF, CNY, INR, MXN, SGD, HKD

---

## 🔧 UI Component Specifications

### Buttons
- **Background**: Gold (`#d4af37`) 
- **Text**: Black (`#1a1a1a`), 16sp, Bold
- **Padding**: 16dp vertical, 32dp horizontal
- **Border Radius**: 8dp
- **Width**: Full width with 16dp margins
- **Height**: 48dp
- **Font**: Sans Serif, Bold

### Text Inputs
- **Background**: `#2d2d2d`
- **Text Color**: White (`#ffffff`)
- **Border**: 1dp Gold (`#d4af37`)
- **Padding**: 12dp
- **Border Radius**: 6dp
- **Hint Color**: `#888888`
- **Font Size**: 14sp

### Labels
- **Color**: Light Gray (`#b0b0b0`)
- **Font Size**: 13sp
- **Font**: Sans Serif
- **Margin Bottom**: 8dp

### Result Cards
- **Background**: `#2d2d2d`
- **Border**: 2dp Gold (`#d4af37`)
- **Padding**: 16dp
- **Border Radius**: 8dp
- **Title**: 12sp, Light Gray
- **Value**: 18sp, Gold, Bold

### Back Button
- **Style**: Text Button
- **Color**: Gold (`#d4af37`)
- **Position**: Top Left
- **Symbol**: `<` or "← Back"

---

## 🏗️ MIT App Inventor Structure

### Screens
1. `ScreenHome` - Main menu
2. `ScreenSavings` - Savings calculator
3. `ScreenBonus` - Bonus calculator
4. `ScreenCurrency` - Currency converter

### Global Variables
```
Global_PrimaryColor = "#d4af37"      (Gold)
Global_BackgroundColor = "#1a1a1a"   (Black)
Global_CardColor = "#2d2d2d"         (Charcoal)
Global_TextPrimary = "#ffffff"       (White)
Global_TextSecondary = "#b0b0b0"     (Light Gray)
Global_CurrencyRates = {...}         (Exchange rates)
```

### Navigation Pattern
- Each calculator screen has a back button to return to home
- All screens share the same color theme
- Results display in dedicated result cards

---

## ✨ Polish Details

### Typography
- **Headers**: 24sp, Bold, Gold, Sans Serif
- **Screen Titles**: 18sp, Bold, White, Sans Serif
- **Labels**: 13sp, Regular, Light Gray, Sans Serif
- **Input/Results**: 16sp, Regular, White, Sans Serif
- **Result Values**: 18sp, Bold, Gold, Sans Serif

### Spacing
- **Screen Padding**: 16dp
- **Element Spacing**: 16dp
- **Input Group Spacing**: 12dp
- **Result Card Padding**: 16dp

### Animations
- **Button Press**: Slight scale (95-105%)
- **Screen Transition**: Fade effect (200ms)
- **Result Reveal**: Fade in (300ms)

---

## 🚀 Build Checklist

- [ ] Create 4 screens in MIT App Inventor
- [ ] Add background colors and styling
- [ ] Build Home screen with 3 navigation buttons
- [ ] Build Savings Calculator with inputs and formula
- [ ] Build Bonus Calculator with inputs and formula
- [ ] Build Currency Converter with dropdown currencies
- [ ] Add back navigation to all screens
- [ ] Test all calculations
- [ ] Verify color scheme consistency
- [ ] Test on device

---

**Ready to build!** 🎉
