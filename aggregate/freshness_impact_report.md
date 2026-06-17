# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-17 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.3%) is 2.1× the overall rate (5.0%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 10.3% | 0.436 | 0.1 |       38 | 100.0% |  23.5% | 2.2× | 0.0% |   0.4474 |
|       OK |   24 |   37.5 | 4.2% | 0.375 | 0.0 |       23 | 100.0% |  33.3% | 7.7× | 0.0% |   0.1304 |
| DEGRADED |   37 |  120.5 | 0.0% | 0.371 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.2571 |
|      ALL |  100 |   58.8 | 5.0% | 0.397 | 0.1 |       96 | 100.0% |  17.2% | 3.3× | 0.0% |   0.3021 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 0.0% | 0.438 | 0.0 |       38 |    - |   0.0% |    - | 0.0% |   0.1316 |
|       OK |   24 |   37.5 | 0.0% | 0.321 | 0.0 |       23 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   37 |  120.5 | 0.0% | 0.323 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0857 |
|      ALL |  100 |   58.8 | 0.0% | 0.367 | 0.0 |       96 |    - |   0.0% |    - | 0.0% |   0.0833 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   39 |   13.3 | 7.7% | 0.596 | 0.1 |       38 | 0.0% |   0.0% |    - | 8.6% |   0.0789 |
|       OK |   24 |   37.5 | 4.2% | 0.536 | 0.0 |       23 | 0.0% |      - |    - | 4.3% |   0.0000 |
| DEGRADED |   37 |  120.5 | 0.0% | 0.480 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.0286 |
|      ALL |  100 |   58.8 | 4.0% | 0.539 | 0.0 |       96 | 0.0% |   0.0% |    - | 4.3% |   0.0417 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.379 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.2000 |
|       OK |    8 |   40.8 | 0.0% | 0.330 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.6 | 0.0% | 0.404 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.4000 |
|      ALL |   31 |   50.6 | 0.0% | 0.376 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 0.0% | 0.401 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|       OK |    8 |   40.8 | 0.0% | 0.259 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.6 | 0.0% | 0.345 | 0.0 |       10 |    - |   0.0% |    - | 0.0% |   0.1000 |
|      ALL |   31 |   50.6 | 0.0% | 0.343 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   15.2 | 9.1% | 0.596 | 0.1 |       10 | 0.0% |   0.0% |    - | 11.1% |   0.1000 |
|       OK |    8 |   40.8 | 0.0% | 0.551 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.6 | 0.0% | 0.534 | 0.0 |       10 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.6 | 3.2% | 0.560 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available