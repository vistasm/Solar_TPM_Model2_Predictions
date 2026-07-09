# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-09 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (100.0%) is 100.0% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (9.8%) is 2.4× the overall rate (4.1%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (17.6%) is 2.2× the overall rate (8.2%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   12.0 | 19.6% | 0.501 | 0.3 |       48 | 100.0% |  36.0% | 1.9× | 0.0% |   0.5208 |
|       OK |   26 |   36.9 | 3.9% | 0.398 | 0.0 |       25 | 100.0% |  33.3% | 8.3× | 0.0% |   0.1200 |
| DEGRADED |   45 |  120.4 | 2.2% | 0.405 | 0.0 |       45 | 0.0% |   0.0% |    - | 2.9% |   0.2444 |
|      ALL |  122 |   57.3 | 9.8% | 0.444 | 0.2 |      118 | 90.9% |  25.6% | 2.8× | 1.3% |   0.3305 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   12.0 | 9.8% | 0.491 | 0.1 |       48 | 75.0% |  27.3% | 3.3× | 2.7% |   0.2292 |
|       OK |   26 |   36.9 | 0.0% | 0.334 | 0.0 |       25 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.351 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0667 |
|      ALL |  122 |   57.3 | 4.1% | 0.406 | 0.0 |      118 | 75.0% |  21.4% | 6.3× | 1.0% |   0.1186 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   51 |   12.0 | 17.6% | 0.637 | 0.2 |       48 | 12.5% |  20.0% | 1.2× | 16.3% |   0.1042 |
|       OK |   26 |   36.9 | 3.9% | 0.545 | 0.0 |       25 | 0.0% |      - |    - | 4.0% |   0.0000 |
| DEGRADED |   45 |  120.4 | 0.0% | 0.500 | 0.0 |       45 |    - |   0.0% |    - | 0.0% |   0.0222 |
|      ALL |  122 |   57.3 | 8.2% | 0.567 | 0.1 |      118 | 11.1% |  16.7% | 2.2× | 7.1% |   0.0508 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.4 | 37.5% | 0.638 | 0.8 |       13 | 100.0% |  62.5% | 1.6× | 0.0% |   0.6154 |
|       OK |    4 |   36.1 | 0.0% | 0.406 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 9.1% | 0.522 | 0.1 |       11 | 0.0% |   0.0% |    - | 11.1% |   0.1818 |
|      ALL |   31 |   47.4 | 22.6% | 0.567 | 0.4 |       27 | 83.3% |  50.0% | 2.2× | 5.9% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.4 | 31.2% | 0.630 | 0.3 |       13 | 75.0% |  50.0% | 1.6× | 14.3% |   0.4615 |
|       OK |    4 |   36.1 | 0.0% | 0.331 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.474 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.4 | 16.1% | 0.536 | 0.2 |       27 | 75.0% |  50.0% | 3.4× | 4.8% |   0.2222 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |    9.4 | 37.5% | 0.721 | 0.4 |       13 | 20.0% |  50.0% | 1.3× | 36.4% |   0.1538 |
|       OK |    4 |   36.1 | 0.0% | 0.541 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   11 |  106.8 | 0.0% | 0.547 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   47.4 | 19.4% | 0.636 | 0.2 |       27 | 20.0% |  50.0% | 2.7× | 16.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available