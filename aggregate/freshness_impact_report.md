# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-05-13 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

✅ No anomalies detected. Insufficient data or metrics within normal range.

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 15.4% | 0.464 | 0.2 |       25 | 100.0% |  28.6% | 1.8× | 0.0% |   0.5600 |
|       OK |   15 |   36.0 | 6.7% | 0.409 | 0.1 |       14 | 100.0% |  33.3% | 4.7× | 0.0% |   0.2143 |
| DEGRADED |   24 |  137.3 | 0.0% | 0.350 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.2174 |
|      ALL |   65 |   64.1 | 7.7% | 0.409 | 0.1 |       62 | 100.0% |  22.7% | 2.8× | 0.0% |   0.3548 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 0.0% | 0.465 | 0.0 |       25 |    - |   0.0% |    - | 0.0% |   0.1600 |
|       OK |   15 |   36.0 | 0.0% | 0.364 | 0.0 |       14 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   24 |  137.3 | 0.0% | 0.311 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0870 |
|      ALL |   65 |   64.1 | 0.0% | 0.385 | 0.0 |       62 |    - |   0.0% |    - | 0.0% |   0.0968 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   26 |   12.7 | 7.7% | 0.600 | 0.1 |       25 | 0.0% |   0.0% |    - | 8.7% |   0.0800 |
|       OK |   15 |   36.0 | 6.7% | 0.527 | 0.1 |       14 | 0.0% |      - |    - | 7.1% |   0.0000 |
| DEGRADED |   24 |  137.3 | 0.0% | 0.450 | 0.0 |       23 |    - |   0.0% |    - | 0.0% |   0.0435 |
|      ALL |   65 |   64.1 | 4.6% | 0.528 | 0.1 |       62 | 0.0% |   0.0% |    - | 5.1% |   0.0484 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 40.0% | 0.658 | 0.5 |        9 | 100.0% |  66.7% | 1.5× | 0.0% |   0.6667 |
|       OK |    4 |   36.5 | 0.0% | 0.421 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.371 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.2500 |
|      ALL |   31 |   97.0 | 12.9% | 0.470 | 0.2 |       28 | 100.0% |  40.0% | 2.8× | 0.0% |   0.3571 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 0.0% | 0.609 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.2222 |
|       OK |    4 |   36.5 | 0.0% | 0.300 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.320 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   97.0 | 0.0% | 0.411 | 0.0 |       28 |    - |   0.0% |    - | 0.0% |   0.1429 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   11.2 | 20.0% | 0.711 | 0.2 |        9 | 0.0% |   0.0% |    - | 25.0% |   0.1111 |
|       OK |    4 |   36.5 | 0.0% | 0.542 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   17 |  161.6 | 0.0% | 0.451 | 0.0 |       16 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   31 |   97.0 | 6.5% | 0.547 | 0.1 |       28 | 0.0% |   0.0% |    - | 7.7% |   0.0714 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available