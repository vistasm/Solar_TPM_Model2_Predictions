# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-08-02 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (83.3%) is 83.3% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (8.1%) is 2.4× the overall rate (3.4%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (14.5%) is 2.1× the overall rate (6.9%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 19.4% | 0.505 | 0.3 |       61 | 83.3% |  34.5% | 1.8× | 6.2% |   0.4754 |
|       OK |   32 |   36.8 | 6.2% | 0.396 | 0.1 |       31 | 100.0% |  25.0% | 7.8× | 0.0% |   0.1290 |
| DEGRADED |   52 |  115.4 | 1.9% | 0.400 | 0.0 |       50 | 0.0% |   0.0% |    - | 2.7% |   0.2600 |
|      ALL |  146 |   54.5 | 10.3% | 0.444 | 0.1 |      142 | 78.6% |  23.9% | 2.4× | 3.1% |   0.3239 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 8.1% | 0.499 | 0.1 |       61 | 60.0% |  27.3% | 3.3× | 4.0% |   0.1803 |
|       OK |   32 |   36.8 | 0.0% | 0.329 | 0.0 |       31 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   52 |  115.4 | 0.0% | 0.343 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0600 |
|      ALL |  146 |   54.5 | 3.4% | 0.406 | 0.0 |      142 | 60.0% |  21.4% | 6.1× | 1.6% |   0.0986 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   62 |   12.6 | 14.5% | 0.608 | 0.1 |       61 | 11.1% |  20.0% | 1.4× | 14.3% |   0.0820 |
|       OK |   32 |   36.8 | 3.1% | 0.527 | 0.0 |       31 | 0.0% |      - |    - | 3.2% |   0.0000 |
| DEGRADED |   52 |  115.4 | 0.0% | 0.488 | 0.0 |       50 |    - |   0.0% |    - | 0.0% |   0.0200 |
|      ALL |  146 |   54.5 | 6.9% | 0.548 | 0.1 |      142 | 10.0% |  16.7% | 2.4× | 6.6% |   0.0423 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.7 | 35.3% | 0.624 | 0.7 |       16 | 66.7% |  57.1% | 1.5× | 22.2% |   0.4375 |
|       OK |    7 |   34.9 | 14.3% | 0.420 | 0.1 |        6 |    - |   0.0% |    - | 0.0% |   0.1667 |
| DEGRADED |    7 |   83.3 | 0.0% | 0.363 | 0.0 |        5 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   33.6 | 22.6% | 0.519 | 0.4 |       27 | 66.7% |  40.0% | 1.8× | 11.8% |   0.3704 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.7 | 23.5% | 0.615 | 0.2 |       16 | 75.0% | 100.0% | 4.0× | 7.7% |   0.1875 |
|       OK |    7 |   34.9 | 0.0% | 0.353 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   83.3 | 0.0% | 0.291 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.6 | 12.9% | 0.483 | 0.1 |       27 | 75.0% | 100.0% | 6.8× | 4.2% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   17 |   12.7 | 23.5% | 0.610 | 0.2 |       16 | 25.0% | 100.0% | 4.0× | 20.0% |   0.0625 |
|       OK |    7 |   34.9 | 0.0% | 0.479 | 0.0 |        6 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |   83.3 | 0.0% | 0.408 | 0.0 |        5 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   33.6 | 12.9% | 0.535 | 0.1 |       27 | 25.0% | 100.0% | 6.8× | 11.5% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available