# India-Stocks-1981-2010-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1981 to 2010)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1981-2010-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1981 to 2010)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1981 | `RAMASTEEL` | Rama Steel Tubes Limited | `RAMASTEEL.NS` |
| 1982 | `RAMBHAJO` | Advit Jewels Limited | `RAMBHAJO.NS` |
| 1983 | `RAMCOIND` | Ramco Industries Limited | `RAMCOIND.NS` |
| 1984 | `RAMCOSYS` | Ramco Systems Limited | `RAMCOSYS.NS` |
| 1985 | `RAMKY` | Ramky Infrastructure Limited | `RAMKY.NS` |
| 1986 | `RAMRAT` | Ram Ratna Wires Limited | `RAMRAT.NS` |
| 1987 | `RANASUG` | Rana Sugars Limited | `RANASUG.NS` |
| 1988 | `RANEHOLDIN` | Rane Holdings Limited | `RANEHOLDIN.NS` |
| 1989 | `RATEGAIN` | Rategain Travel Technologies Limited | `RATEGAIN.NS` |
| 1990 | `RATNAMANI` | Ratnamani Metals & Tubes Limited | `RATNAMANI.NS` |
| 1991 | `RATNAVEER` | Ratnaveer Precision Engineering Limited | `RATNAVEER.NS` |
| 1992 | `RAYMOND` | Raymond Limited | `RAYMOND.NS` |
| 1993 | `RAYMONDLSL` | Raymond Lifestyle Limited | `RAYMONDLSL.NS` |
| 1994 | `RAYMONDREL` | Raymond Realty Limited | `RAYMONDREL.NS` |
| 1995 | `RBA` | Restaurant Brands Asia Limited | `RBA.NS` |
| 1996 | `RBZJEWEL` | RBZ Jewellers Limited | `RBZJEWEL.NS` |
| 1997 | `RCF` | Rashtriya Chemicals and Fertilizers Limited | `RCF.NS` |
| 1998 | `RCOM` | Reliance Communications Limited | `RCOM.NS` |
| 1999 | `REDTAPE` | Redtape Limited | `REDTAPE.NS` |
| 2000 | `REFEX` | Refex Industries Limited | `REFEX.NS` |
| 2001 | `REGAAL` | Regaal Resources Limited | `REGAAL.NS` |
| 2002 | `REGENCERAM` | Regency Ceramics Limited | `REGENCERAM.NS` |
| 2003 | `RELAXO` | Relaxo Footwears Limited | `RELAXO.NS` |
| 2004 | `RELCHEMQ` | Reliance Chemotex Industries Limited | `RELCHEMQ.NS` |
| 2005 | `RELIABLE` | Reliable Data Services Limited | `RELIABLE.NS` |
| 2006 | `RELIGARE` | Religare Enterprises Limited | `RELIGARE.NS` |
| 2007 | `RELINFRA` | Reliance Infrastructure Limited | `RELINFRA.NS` |
| 2008 | `RELTD` | Ravindra Energy Limited | `RELTD.NS` |
| 2009 | `REMSONSIND` | Remsons Industries Limited | `REMSONSIND.NS` |
| 2010 | `RENTOMOJO` | Rentomojo Limited | `RENTOMOJO.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream RAMASTEEL 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1981-2010-Historical-Data/main/RAMASTEEL/1m/2026/10/RAMASTEEL_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
