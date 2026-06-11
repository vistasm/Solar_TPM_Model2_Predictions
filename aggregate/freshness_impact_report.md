# 🔬 Freshness Impact Report (C2 Monitoring)

**Generated:** 2026-06-11 UTC
**Purpose:** Monitor whether fresher DONKI Same_AR data helps or hurts prediction quality.
**Training regime:** 48h Same_AR lag (worst-case). Production: dynamic best-available.

**Lag Buckets:**
- **FRESH:** effective lag < 24h (stronger Same_AR signal than training assumed)
- **OK:** 24–48h lag (similar to training regime)
- **DEGRADED:** ≥48h lag (matches training worst-case)

---

## ⚠️ Decision Signals

🟡 **M+**: FRESH alert rate (10.8%) is 2.0× the overall rate (5.3%) — score distribution shift detected

## Cumulative

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.0 | 10.8% | 0.447 | 0.1 |       35 | 100.0% |  23.5% | 2.1× | 0.0% |   0.4857 |
|       OK |   22 |   37.0 | 4.5% | 0.396 | 0.1 |       21 | 100.0% |  33.3% | 7.0× | 0.0% |   0.1429 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.377 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.2647 |
|      ALL |   94 |   59.6 | 5.3% | 0.409 | 0.1 |       90 | 100.0% |  17.2% | 3.1× | 0.0% |   0.3222 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.0 | 0.0% | 0.442 | 0.0 |       35 |    - |   0.0% |    - | 0.0% |   0.1429 |
|       OK |   22 |   37.0 | 0.0% | 0.335 | 0.0 |       21 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.321 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0882 |
|      ALL |   94 |   59.6 | 0.0% | 0.372 | 0.0 |       90 |    - |   0.0% |    - | 0.0% |   0.0889 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   37 |   13.0 | 8.1% | 0.602 | 0.1 |       35 | 0.0% |   0.0% |    - | 9.4% |   0.0857 |
|       OK |   22 |   37.0 | 4.5% | 0.546 | 0.1 |       21 | 0.0% |      - |    - | 4.8% |   0.0000 |
| DEGRADED |   35 |  123.0 | 0.0% | 0.487 | 0.0 |       34 |    - |   0.0% |    - | 0.0% |   0.0294 |
|      ALL |   94 |   59.6 | 4.3% | 0.546 | 0.0 |       90 | 0.0% |   0.0% |    - | 4.7% |   0.0444 |

## Last 30 Days

### M+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.5 | 0.0% | 0.406 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.3333 |
|       OK |    8 |   39.3 | 0.0% | 0.407 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.440 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.3636 |
|      ALL |   31 |   49.6 | 0.0% | 0.420 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.2593 |

### M5+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.5 | 0.0% | 0.388 | 0.0 |        9 |    - |   0.0% |    - | 0.0% |   0.1111 |
|       OK |    8 |   39.3 | 0.0% | 0.294 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.335 | 0.0 |       11 |    - |   0.0% |    - | 0.0% |   0.0909 |
|      ALL |   31 |   49.6 | 0.0% | 0.343 | 0.0 |       27 |    - |   0.0% |    - | 0.0% |   0.0741 |

### X+

| Bucket | Days | Lag(h) | Alert% | MaxProb | AR/day | Verified | Prec | Recall | Lift | FAR | BaseRate |
|--------|------|--------|--------|---------|--------|----------|------|--------|------|-----|----------|
|    FRESH |   11 |   13.5 | 9.1% | 0.608 | 0.1 |        9 | 0.0% |   0.0% |    - | 12.5% |   0.1111 |
|       OK |    8 |   39.3 | 0.0% | 0.586 | 0.0 |        7 |    - |      - |    - | 0.0% |   0.0000 |
| DEGRADED |   12 |   89.5 | 0.0% | 0.570 | 0.0 |       11 |    - |      - |    - | 0.0% |   0.0000 |
|      ALL |   31 |   49.6 | 3.2% | 0.588 | 0.0 |       27 | 0.0% |   0.0% |    - | 3.9% |   0.0370 |

---

**How to read:** Compare FRESH vs DEGRADED. If FRESH has lower precision or much higher alert rate, fresher Same_AR may be causing calibration drift. If FRESH has equal/better precision, the dynamic best-available strategy is working.

**Action thresholds:**
- 🔴 FRESH precision >10pp below DEGRADED → consider enforcing 48h lag
- 🟡 FRESH alert rate >2× overall → score distribution shift, monitor closely
- 🟢 FRESH precision ≥ DEGRADED → fresher data is helping, keep best-available