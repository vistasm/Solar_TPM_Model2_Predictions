# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-08 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (11.4%) is 2.1× the overall rate (5.5%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.3 | 11.4% | 0.439 | 0.1 |       33 | 100.0% |  25.0% | 2.1× | 0.0% |   0.4848 |
|       OK |   22 |   37.0 | 4.5% | 0.396 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.368 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   91 |   60.7 | 5.5% | 0.402 | 0.1 |       87 | 100.0% |  17.9% | 3.1× | 0.0% |   0.3218 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.3 | 0.0% | 0.428 | 0.0 |       33 |    - |   0.0% |    - | 0.0% |   0.1515 |
|       OK |   22 |   37.0 | 0.0% | 0.335 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.311 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   91 |   60.7 | 0.0% | 0.362 | 0.0 |       87 |    - |   0.0% |    - | 0.0% |   0.0920 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   35 |   13.3 | 8.6% | 0.598 | 0.1 |       33 | 0.0% |   0.0% |    - | 10.0% |   0.0909 |
|       OK |   22 |   37.0 | 4.5% | 0.546 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.485 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   91 |   60.7 | 4.4% | 0.543 | 0.0 |       87 | 0.0% |   0.0% |    - | 4.8% |   0.0460 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.9 | 0.0% | 0.404 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.2500 |
|       OK |    9 |   39.2 | 0.0% | 0.384 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.4 | 0.0% | 0.417 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.4167 |
|      ALL |   31 |   50.8 | 0.0% | 0.403 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.9 | 0.0% | 0.347 | 0.0 |        8 |    - |   0.0% |    - | 0.0% |   0.1250 |
|       OK |    9 |   39.2 | 0.0% | 0.282 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.4 | 0.0% | 0.316 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.1667 |
|      ALL |   31 |   50.8 | 0.0% | 0.316 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1111 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   10 |   14.9 | 10.0% | 0.593 | 0.1 |        8 | 0.0% |   0.0% |    - | 14.3% |   0.1250 |
|       OK |    9 |   39.2 | 0.0% | 0.579 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.4 | 0.0% | 0.570 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   50.8 | 3.2% | 0.580 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available