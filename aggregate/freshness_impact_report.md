# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-07-27 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.2%) is 2.3× the overall rate (3.6%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.8%) is 2.1× the overall rate (7.1%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 19.7% | 0.505 | 0.3 |       59 | 83.3% |  34.5% | 1.7× | 6.7% |   0.4915 |
|       OK |   29 |   37.4 | 3.5% | 0.384 | 0.0 |       28 | 100.0% |  25.0% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   50 |  117.7 | 2.0% | 0.396 | 0.0 |       49 | 0.0% |   0.0% |    - | 2.7% |   0.2449 |
|      ALL |  140 |   55.2 | 10.0% | 0.441 | 0.1 |      136 | 78.6% |  24.4% | 2.4× | 3.3% |   0.3309 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 8.2% | 0.497 | 0.1 |       59 | 60.0% |  27.3% | 3.2× | 4.2% |   0.1864 |
|       OK |   29 |   37.4 | 0.0% | 0.318 | 0.0 |       28 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.335 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0612 |
|      ALL |  140 |   55.2 | 3.6% | 0.402 | 0.0 |      136 | 60.0% |  21.4% | 5.8× | 1.6% |   0.1029 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   61 |   12.6 | 14.8% | 0.610 | 0.1 |       59 | 11.1% |  20.0% | 1.3× | 14.8% |   0.0847 |
|       OK |   29 |   37.4 | 3.5% | 0.535 | 0.0 |       28 | 0.0% |      - |    - | 3.6% |   0.0000 |
| DEGRADED |   50 |  117.7 | 0.0% | 0.486 | 0.0 |       49 |    - |   0.0% |    - | 0.0% |   0.0204 |
|      ALL |  140 |   55.2 | 7.1% | 0.550 | 0.1 |      136 | 10.0% |  16.7% | 2.3× | 6.9% |   0.0441 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 42.1% | 0.666 | 0.7 |       17 | 75.0% |  60.0% | 1.3× | 28.6% |   0.5882 |
|       OK |    4 |   37.4 | 0.0% | 0.353 | 0.0 |        3 |    - |   0.0% |    - | 0.0% |   0.3333 |
| DEGRADED |    8 |  116.2 | 12.5% | 0.446 | 0.1 |        7 | 0.0% |   0.0% |    - | 20.0% |   0.2857 |
|      ALL |   31 |   41.9 | 29.0% | 0.569 | 0.5 |       27 | 66.7% |  46.2% | 1.4× | 21.4% |   0.4815 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 26.3% | 0.655 | 0.3 |       17 | 60.0% |  60.0% | 2.0× | 16.7% |   0.2941 |
|       OK |    4 |   37.4 | 0.0% | 0.293 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  116.2 | 0.0% | 0.361 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   41.9 | 16.1% | 0.532 | 0.2 |       27 | 60.0% |  60.0% | 3.2× | 9.1% |   0.1852 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   19 |   11.5 | 31.6% | 0.660 | 0.3 |       17 | 16.7% |  50.0% | 1.4× | 33.3% |   0.1176 |
|       OK |    4 |   37.4 | 0.0% | 0.500 | 0.0 |        3 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    8 |  116.2 | 0.0% | 0.504 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   41.9 | 19.4% | 0.599 | 0.2 |       27 | 16.7% |  50.0% | 2.2× | 20.0% |   0.0741 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available