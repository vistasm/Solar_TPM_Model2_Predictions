# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-04 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (12.1%) is 2.1× the overall rate (5.8%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.2 | 12.1% | 0.441 | 0.1 |       31 | 100.0% |  26.7% | 2.1× | 0.0% |   0.4839 |
|       OK |   20 |   36.6 | 5.0% | 0.394 | 0.1 |       20 | 100.0% |  33.3% | 6.7× | 0.0% |   0.1500 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.368 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.2188 |
|      ALL |   87 |   62.2 | 5.8% | 0.401 | 0.1 |       83 | 100.0% |  20.0% | 3.3× | 0.0% |   0.3012 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.2 | 0.0% | 0.424 | 0.0 |       31 |    - |   0.0% |    - | 0.0% |   0.1290 |
|       OK |   20 |   36.6 | 0.0% | 0.332 | 0.0 |       20 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.311 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0625 |
|      ALL |   87 |   62.2 | 0.0% | 0.359 | 0.0 |       83 |    - |   0.0% |    - | 0.0% |   0.0723 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   33 |   13.2 | 9.1% | 0.597 | 0.1 |       31 | 0.0% |   0.0% |    - | 6.9% |   0.0645 |
|       OK |   20 |   36.6 | 5.0% | 0.532 | 0.1 |       20 | 0.0% |      - |    - | 5.0% |   0.0000 |
| DEGRADED |   34 |  124.7 | 0.0% | 0.485 | 0.0 |       32 |    - |   0.0% |    - | 0.0% |   0.0312 |
|      ALL |   87 |   62.2 | 4.6% | 0.538 | 0.1 |       83 | 0.0% |   0.0% |    - | 3.8% |   0.0361 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.381 | 0.0 |        7 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |    8 |   37.4 | 0.0% | 0.365 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.391 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.3333 |
|      ALL |   31 |   52.7 | 0.0% | 0.382 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.1852 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 0.0% | 0.297 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.255 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.298 | 0.0 |       12 |    - |   0.0% |    - | 0.0% |   0.0833 |
|      ALL |   31 |   52.7 | 0.0% | 0.287 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0370 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |    9 |   14.8 | 11.1% | 0.579 | 0.1 |        7 |    - |      - |    - | 0.0% |   0.0000 |
|       OK |    8 |   37.4 | 0.0% | 0.546 | 0.0 |        8 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   14 |   85.8 | 0.0% | 0.565 | 0.0 |       12 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   52.7 | 3.2% | 0.564 | 0.0 |       27 |    - |      - |    - | 0.0% |   0.0000 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available