# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-12 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (76.5%) is 26.5% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.9%) is 2.9× the overall rate (2.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.6%) is 2.6× the overall rate (4.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 21.2% | 0.515 | 0.3 |       83 | 76.5% |  35.1% | 1.7× | 8.7% |   0.4458 |
|       OK |   44 |   37.0 | 11.4% | 0.439 | 0.1 |       43 | 50.0% |  33.3% | 3.6× | 5.4% |   0.1395 |
| DEGRADED |  119 |  120.0 | 5.9% | 0.388 | 0.1 |      118 | 50.0% |  13.0% | 2.6× | 3.2% |   0.1949 |
|      ALL |  248 |   68.5 | 12.1% | 0.441 | 0.1 |      244 | 66.7% |  27.3% | 2.5× | 5.1% |   0.2705 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 5.9% | 0.505 | 0.1 |       83 | 60.0% |  23.1% | 3.8× | 2.9% |   0.1566 |
|       OK |   44 |   37.0 | 0.0% | 0.383 | 0.0 |       43 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  119 |  120.0 | 0.0% | 0.344 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0424 |
|      ALL |  248 |   68.5 | 2.0% | 0.406 | 0.0 |      244 | 60.0% |  16.7% | 8.1× | 0.9% |   0.0738 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   85 |   12.8 | 10.6% | 0.597 | 0.1 |       83 | 11.1% |  20.0% | 1.8× | 10.3% |   0.0602 |
|       OK |   44 |   37.0 | 2.3% | 0.539 | 0.0 |       43 | 0.0% |      - |    - | 2.3% |   0.0000 |
| DEGRADED |  119 |  120.0 | 0.0% | 0.518 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0085 |
|      ALL |  248 |   68.5 | 4.0% | 0.549 | 0.0 |      244 | 10.0% |  16.7% | 4.1× | 3.8% |   0.0246 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 75.0% | 0.800 | 0.8 |        2 | 50.0% | 100.0% | 1.0× | 100.0% |   0.5000 |
|       OK |    2 |   35.2 | 100.0% | 0.862 | 1.0 |        1 | 100.0% | 100.0% | 1.0× |   - |   1.0000 |
| DEGRADED |   25 |  111.9 | 4.0% | 0.377 | 0.0 |       24 |    - |   0.0% |    - | 0.0% |   0.1250 |
|      ALL |   31 |   93.9 | 19.4% | 0.463 | 0.2 |       27 | 66.7% |  40.0% | 3.6× | 4.5% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 0.0% | 0.860 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.2 | 0.0% | 0.918 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  111.9 | 0.0% | 0.376 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.9 | 0.0% | 0.473 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    4 |   10.4 | 0.0% | 0.598 | 0.0 |        2 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.2 | 0.0% | 0.615 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   25 |  111.9 | 0.0% | 0.542 | 0.0 |       24 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   93.9 | 0.0% | 0.554 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available