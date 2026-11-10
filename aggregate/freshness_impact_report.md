# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-11-10 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (75.0%) is 25.0% HIGHER than DEGRADED (50.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (5.9%) is 2.9× the overall rate (2.0%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (10.7%) is 2.6× the overall rate (4.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.8 | 21.4% | 0.514 | 0.3 |       82 | 75.0% |  33.3% | 1.7× | 8.7% |   0.4390 |
|       OK |   44 |   37.0 | 11.4% | 0.439 | 0.1 |       42 | 33.3% |  20.0% | 2.8× | 5.4% |   0.1190 |
| DEGRADED |  118 |  120.5 | 5.1% | 0.385 | 0.1 |      118 | 50.0% |  13.0% | 2.6× | 3.2% |   0.1949 |
|      ALL |  246 |   68.8 | 11.8% | 0.439 | 0.1 |      242 | 64.0% |  25.0% | 2.4× | 5.1% |   0.2645 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.8 | 5.9% | 0.502 | 0.1 |       82 | 60.0% |  23.1% | 3.8× | 2.9% |   0.1585 |
|       OK |   44 |   37.0 | 0.0% | 0.383 | 0.0 |       42 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.340 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0424 |
|      ALL |  246 |   68.8 | 2.0% | 0.403 | 0.0 |      242 | 60.0% |  16.7% | 8.1× | 0.9% |   0.0744 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   84 |   12.8 | 10.7% | 0.598 | 0.1 |       82 | 11.1% |  20.0% | 1.8× | 10.4% |   0.0610 |
|       OK |   44 |   37.0 | 2.3% | 0.539 | 0.0 |       42 | 0.0% |      - |    - | 2.4% |   0.0000 |
| DEGRADED |  118 |  120.5 | 0.0% | 0.517 | 0.0 |      118 |    - |   0.0% |    - | 0.0% |   0.0085 |
|      ALL |  246 |   68.8 | 4.1% | 0.548 | 0.0 |      242 | 10.0% |  16.7% | 4.0× | 3.8% |   0.0248 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.1 | 100.0% | 0.869 | 1.0 |        1 | 0.0% |      - |    - | 100.0% |   0.0000 |
|       OK |    2 |   35.2 | 100.0% | 0.862 | 1.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  112.7 | 7.7% | 0.399 | 0.1 |       26 | 0.0% |   0.0% |    - | 8.7% |   0.1154 |
|      ALL |   31 |   97.9 | 22.6% | 0.474 | 0.2 |       27 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.1 | 0.0% | 0.914 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.2 | 0.0% | 0.918 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  112.7 | 0.0% | 0.397 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   97.9 | 0.0% | 0.480 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    3 |   11.1 | 0.0% | 0.606 | 0.0 |        1 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    2 |   35.2 | 0.0% | 0.615 | 0.0 |        0 |    - |      - |    - |   - |        - |
| DEGRADED |   26 |  112.7 | 0.0% | 0.551 | 0.0 |       26 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   97.9 | 0.0% | 0.560 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available