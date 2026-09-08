# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-09-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟢 **M+**: FRESH precision (78.6%) is 78.6% HIGHER than DEGRADED (0.0%) — fresher data is helping
🟡 **M5+**: FRESH alert rate (6.4%) is 2.3× the overall rate (2.7%) — score distribution shift detected
🟡 **X+**: FRESH alert rate (11.5%) is 2.1× the overall rate (5.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 19.2% | 0.515 | 0.3 |       75 | 78.6% |  31.4% | 1.7× | 7.5% |   0.4667 |
|       OK |   40 |   36.9 | 7.5% | 0.419 | 0.1 |       39 | 33.3% |  20.0% | 2.6× | 5.9% |   0.1282 |
| DEGRADED |   65 |  118.5 | 1.5% | 0.393 | 0.0 |       65 | 0.0% |   0.0% |    - | 2.0% |   0.2308 |
|      ALL |  183 |   55.6 | 10.4% | 0.450 | 0.1 |      179 | 66.7% |  21.8% | 2.2× | 4.8% |   0.3073 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 6.4% | 0.502 | 0.1 |       75 | 60.0% |  23.1% | 3.5× | 3.2% |   0.1733 |
|       OK |   40 |   36.9 | 0.0% | 0.360 | 0.0 |       39 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.338 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0462 |
|      ALL |  183 |   55.6 | 2.7% | 0.413 | 0.0 |      179 | 60.0% |  18.8% | 6.7× | 1.2% |   0.0894 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   78 |   12.7 | 11.5% | 0.601 | 0.1 |       75 | 11.1% |  20.0% | 1.7× | 11.4% |   0.0667 |
|       OK |   40 |   36.9 | 2.5% | 0.535 | 0.0 |       39 | 0.0% |      - |    - | 2.6% |   0.0000 |
| DEGRADED |   65 |  118.5 | 0.0% | 0.498 | 0.0 |       65 |    - |   0.0% |    - | 0.0% |   0.0154 |
|      ALL |  183 |   55.6 | 5.5% | 0.550 | 0.1 |      179 | 10.0% |  16.7% | 3.0× | 5.2% |   0.0335 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 18.8% | 0.553 | 0.2 |       13 | 50.0% |  16.7% | 1.1× | 14.3% |   0.4615 |
|       OK |    8 |   37.1 | 12.5% | 0.509 | 0.1 |        7 | 0.0% |   0.0% |    - | 16.7% |   0.1429 |
| DEGRADED |    7 |  119.7 | 0.0% | 0.368 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|      ALL |   31 |   43.5 | 12.9% | 0.500 | 0.2 |       27 | 33.3% |  12.5% | 1.1× | 10.5% |   0.2963 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.515 | 0.0 |       13 |    - |   0.0% |    - | 0.0% |   0.1538 |
|       OK |    8 |   37.1 | 0.0% | 0.485 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  119.7 | 0.0% | 0.310 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.5 | 0.0% | 0.461 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   16 |   13.4 | 0.0% | 0.571 | 0.0 |       13 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.1 | 0.0% | 0.569 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |    7 |  119.7 | 0.0% | 0.536 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   43.5 | 0.0% | 0.562 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available